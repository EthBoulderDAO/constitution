# Skill: Create Entity

Create new entities in the knowledge graph with proper typing and relationships.

---

## Trigger

```yaml
trigger:
  type: multi
  conditions:
    - type: consent_complete
      entity_type: any
    - type: membrane_crossing
      action: role_change
    - type: event
      action: session_created
    - type: api_request
      endpoint: "/graph/entity"
```

---

## Required Permissions

- Knowledge Graph write access
- MCP connection to Bonfires KG
- Entity type specific permissions

---

## Process

### Step 1: Validate Entity Type

```python
async def validate_entity_type(entity_data):
    """
    Ensure entity type is valid and user has permission.
    """
    valid_types = [
        "Person", "Agent", "Role", "Group", "Asset",
        "Protocol", "Decision", "Session", "Project", "ThirdSpace"
    ]

    if entity_data.type not in valid_types:
        raise InvalidEntityType(entity_data.type)

    await check_creation_permissions(entity_data.type, entity_data.creator)
```

### Step 2: Construct Entity

```python
async def construct_entity(entity_data):
    """
    Build entity with required fields and relationships.
    """
    entity = {
        "id": f"kg://ethboulder/{entity_data.type.lower()}/{generate_id()}",
        "type": entity_data.type,
        "created_at": datetime.utcnow().isoformat(),
        "created_by": entity_data.creator,
        "status": "active",
        **entity_data.fields
    }

    relationships = construct_relationships(entity_data.relationships)

    return entity, relationships
```

### Step 3: Create via MCP

```python
async def create_via_mcp(entity, relationships):
    """
    Create entity and relationships in graph.
    """
    async with mcp_client("bonfires-kg") as client:
        # Create entity node
        entity_result = await client.create_entity(entity)

        # Create relationships
        for rel in relationships:
            await client.create_relationship(
                source=entity.id,
                target=rel.target,
                type=rel.type
            )

        return entity_result
```

### Step 4: Log and Notify

```python
async def log_and_notify(entity_result, context):
    """
    Log creation and notify relevant parties.
    """
    await log_entity_creation(entity_result)

    if entity_result.type in ["Decision", "Session"]:
        await notify_circle(entity_result)
```

---

## Entity Creation Permissions

| Entity Type | Who Can Create | Review Required |
|-------------|----------------|-----------------|
| Person | Agents (on membrane crossing) | No |
| Agent | Stewards | Network consent |
| Role | Network Assembly | Full consent |
| Group | Network Assembly | Standard consent |
| Asset | Network Assembly | Standard consent |
| Protocol | Network Assembly | Full consent |
| Decision | Agents (on consent completion) | No |
| Session | Participants+ | Pre-Event only |
| Project | Participants+ | Circle review |
| ThirdSpace | Third Space Circle | Standard consent |

---

## Outputs

```yaml
outputs:
  on_success:
    - entity_id: Created entity ID
    - entity: Full entity data
    - relationships: Created relationships
  on_failure:
    - error: Error message
    - validation_errors: Specific field errors if applicable
```

---

## Autonomous Execution

Full autonomous execution for authorized entity types. Protected types require prior consent.

---

## MCP Configuration

```yaml
mcp_config:
  server: "bonfires-kg"
  capability: "create_entity"
  auth: "agent-registration-nft"
```

---

## Related Skills

- [[query-graph]] — Query existing entities
- [[reconcile-entities]] — Merge duplicate entities
- [[federate-sync]] — Sync created entities with partners
