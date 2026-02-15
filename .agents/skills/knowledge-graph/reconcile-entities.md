# Skill: Reconcile Entities

Merge duplicate entities in the knowledge graph while preserving relationships and history.

---

## Trigger

```yaml
trigger:
  type: multi
  conditions:
    - type: agent_detection
      pattern: duplicate_entity
    - type: human_request
      action: merge_entities
    - type: scheduled
      frequency: daily
      action: scan_duplicates
```

---

## Required Permissions

- Knowledge Graph reconcile access
- MCP connection to Bonfires KG
- Member-level or higher for execution

---

## Process

### Step 1: Detect Duplicates

```python
async def detect_duplicates():
    """
    Identify potential duplicate entities using fuzzy matching.
    """
    async with mcp_client("bonfires-kg") as client:
        # Query for potential duplicates
        candidates = await client.query("""
            MATCH (a), (b)
            WHERE a.type = b.type
              AND a.id < b.id
              AND (
                apoc.text.fuzzyMatch(a.name, b.name) > 0.8
                OR a.email = b.email
                OR a.wallet = b.wallet
              )
            RETURN a, b, apoc.text.fuzzyMatch(a.name, b.name) as similarity
        """)

        return [
            DuplicateCandidate(
                primary=c.a,
                secondary=c.b,
                confidence=c.similarity
            )
            for c in candidates
        ]
```

### Step 2: Flag for Review

```python
async def flag_for_review(candidates):
    """
    Flag high-confidence duplicates for human review.
    """
    for candidate in candidates:
        if candidate.confidence > 0.9:
            await create_review_request(
                type="entity_reconciliation",
                entities=[candidate.primary.id, candidate.secondary.id],
                confidence=candidate.confidence,
                auto_merge=False  # Human must approve
            )
```

### Step 3: Execute Merge

```python
async def execute_merge(primary_id, secondary_id, approved_by):
    """
    Merge secondary entity into primary, preserving all relationships.
    """
    async with mcp_client("bonfires-kg") as client:
        # Get all relationships from secondary
        secondary_rels = await client.query(f"""
            MATCH (s {{id: '{secondary_id}'}})-[r]->(t)
            RETURN type(r) as type, t.id as target
            UNION
            MATCH (s)-[r]-({{id: '{secondary_id}'}})
            RETURN type(r) as type, s.id as source
        """)

        # Transfer relationships to primary
        for rel in secondary_rels:
            await client.create_relationship(
                source=primary_id,
                target=rel.target or rel.source,
                type=rel.type
            )

        # Create redirect from old ID
        await client.update_entity(
            id=secondary_id,
            status="merged",
            merged_into=primary_id,
            merged_at=datetime.utcnow().isoformat(),
            merged_by=approved_by
        )

        return MergeResult(
            primary=primary_id,
            merged=secondary_id,
            relationships_transferred=len(secondary_rels)
        )
```

---

## Merge Rules

- Newer entity merged into older (preserve history)
- All relationships preserved
- Conflicting properties flagged for human decision
- Redirects maintained permanently
- Audit trail created for merge

---

## Outputs

```yaml
outputs:
  on_detection:
    - candidates: List of duplicate candidates
    - review_requests: Created review requests
  on_merge:
    - primary_id: Surviving entity ID
    - merged_id: Merged entity ID
    - relationships_transferred: Count of relationships moved
  on_failure:
    - error: Error message
    - conflicts: List of unresolvable conflicts
```

---

## Autonomous Execution

Detection runs autonomously. Merge requires Member approval for standard entities, Steward approval for protected entities.

---

## MCP Configuration

```yaml
mcp_config:
  server: "bonfires-kg"
  capability: "reconcile_entities"
  auth: "agent-registration-nft"
```

---

## Related Skills

- [[query-graph]] — Query entities for comparison
- [[create-entity]] — Create merged result if needed
- [[federate-sync]] — Propagate merges to federated graphs
