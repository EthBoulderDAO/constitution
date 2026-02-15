# Skill: Federate Sync

Synchronize entities with partner network knowledge graphs via Bonfires MCP.

---

## Trigger

```yaml
trigger:
  type: multi
  conditions:
    - type: scheduled
      frequency: daily
      action: full_sync
    - type: entity_change
      action: immediate_sync
    - type: webhook
      source: federation_partner
    - type: command
      pattern: "!sync-federation *"
```

---

## Required Permissions

- Knowledge Graph federate access
- MCP connection to Bonfires KG
- Federation agreement with partner network
- Agent-level authorization

---

## Process

### Step 1: Identify Sync Scope

```python
async def identify_sync_scope(trigger_context):
    """
    Determine what needs to be synchronized.
    """
    if trigger_context.type == "full_sync":
        # Get all entities changed since last sync
        return await get_changed_entities(since=last_sync_timestamp)

    elif trigger_context.type == "entity_change":
        # Sync specific entity
        return [trigger_context.entity]

    elif trigger_context.type == "webhook":
        # Process incoming sync from partner
        return parse_incoming_sync(trigger_context.payload)
```

### Step 2: Apply Schema Mapping

```python
async def apply_schema_mapping(entities, partner_network):
    """
    Map local schema to partner network schema.
    """
    mapping = await get_schema_mapping(partner_network)

    mapped_entities = []
    for entity in entities:
        mapped = {
            mapping.get(k, k): v
            for k, v in entity.items()
        }
        mapped["source_network"] = "ethboulder"
        mapped["source_id"] = entity["id"]
        mapped_entities.append(mapped)

    return mapped_entities
```

### Step 3: Execute Sync

```python
async def execute_sync(entities, partner_network, direction):
    """
    Sync entities with partner graph.
    """
    async with mcp_client("bonfires-kg") as client:
        results = []

        for entity in entities:
            if direction == "push":
                result = await client.federate_push(
                    partner=partner_network,
                    entity=entity
                )
            elif direction == "pull":
                result = await client.federate_pull(
                    partner=partner_network,
                    entity_id=entity["id"]
                )

            results.append(result)

        return SyncResult(
            entities_synced=len(results),
            successes=[r for r in results if r.success],
            failures=[r for r in results if not r.success]
        )
```

### Step 4: Handle Conflicts

```python
async def handle_conflicts(conflicts):
    """
    Resolve sync conflicts.
    """
    for conflict in conflicts:
        if conflict.type == "local_newer":
            # Local wins, push to partner
            await execute_sync([conflict.local_entity], conflict.partner, "push")

        elif conflict.type == "remote_newer":
            # Remote wins, pull from partner
            await execute_sync([conflict.remote_entity], conflict.partner, "pull")

        elif conflict.type == "divergent":
            # Flag for human review
            await create_conflict_review(conflict)
```

---

## Federation Partners

| Partner | Sync Frequency | Entity Types |
|---------|----------------|--------------|
| *To be configured* | Daily | Person, Project, Session |

---

## Sync Rules

- Real-time for critical entities (decisions, role changes)
- Daily for full sync
- Local authority for local entities
- Consensus for shared entities
- Conflicts flagged for human review

---

## Outputs

```yaml
outputs:
  on_success:
    - entities_synced: Count of synced entities
    - push_count: Entities pushed to partner
    - pull_count: Entities pulled from partner
  on_conflict:
    - conflicts: List of conflicts requiring review
  on_failure:
    - error: Error message
    - failed_entities: List of entities that failed to sync
```

---

## Autonomous Execution

Full autonomous execution for non-conflicting syncs. Conflicts requiring merge decisions flagged for human review.

---

## MCP Configuration

```yaml
mcp_config:
  server: "bonfires-kg"
  capability: "federate_sync"
  auth: "agent-registration-nft"
  partners:
    - network: "[partner-network]"
      endpoint: "[partner-mcp-endpoint]"
      auth_method: "mutual_tls"
```

---

## Related Skills

- [[query-graph]] — Query entities before sync
- [[create-entity]] — Create entities from incoming sync
- [[reconcile-entities]] — Resolve sync duplicates
