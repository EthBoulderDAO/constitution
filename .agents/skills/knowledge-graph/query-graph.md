# Skill: Query Graph

Execute constitutional queries against the knowledge graph to resolve governance questions.

---

## Trigger

```yaml
trigger:
  type: multi
  conditions:
    - type: command
      pattern: "!query *"
    - type: api_request
      endpoint: "/graph/query"
    - type: governance_question
      pattern: "Who are*|What is*|Is * eligible*"
```

---

## Required Permissions

- Knowledge Graph read access
- MCP connection to Bonfires KG
- Response channel write access

---

## Process

### Step 1: Parse Query Request

```python
async def parse_query_request(message_or_request):
    """
    Determine query type and extract parameters.
    """
    query_types = {
        "current-stewards": resolve_current_stewards,
        "eligible-members": resolve_eligible_members,
        "treasury-protocols": resolve_treasury_protocols,
        "consent-required": resolve_consent_required,
        "role-requirements": resolve_role_requirements,
        "custom": execute_custom_query
    }

    query_type = classify_query(message_or_request)
    return query_types.get(query_type, execute_custom_query)
```

### Step 2: Execute Query via MCP

```python
async def execute_query(query_function, params):
    """
    Connect to Bonfires MCP and execute query.
    """
    async with mcp_client("bonfires-kg") as client:
        result = await client.query(
            query=query_function.cypher,
            params=params
        )
        return format_result(result)
```

### Step 3: Format and Return Result

```python
async def format_and_return(result, context):
    """
    Format query result for the requesting context.
    """
    if context.type == "discord":
        return format_discord_response(result)
    elif context.type == "api":
        return format_json_response(result)
    elif context.type == "agent":
        return result  # Raw for agent processing
```

---

## Standard Query Library

| Query | Cypher Pattern |
|-------|---------------|
| `current-stewards` | `MATCH (p:Person)-[:HAS_ROLE]->(:Role {name: 'Steward', active: true}) RETURN p` |
| `eligible-members` | `MATCH (p:Person)-[:HAS_ROLE]->(:Role {name: 'Participant'}) WHERE p.active_weeks >= 2 RETURN p` |
| `treasury-protocols` | `MATCH (p:Protocol)-[:GOVERNS]->(:Asset {name: 'Treasury'}) RETURN p` |
| `consent-required` | `MATCH (d:DecisionType {name: $type})-[:REQUIRES]->(c:ConsentLevel) RETURN c` |
| `role-requirements` | `MATCH (r:Role {name: $role})-[:REQUIRES]->(req) RETURN req` |

---

## Outputs

```yaml
outputs:
  on_success:
    - result: Query result data
    - formatted: Human-readable format
    - metadata: Query execution metadata
  on_failure:
    - error: Error message
    - suggestion: Suggested correction if query malformed
```

---

## Autonomous Execution

Full autonomous execution. Query results are returned immediately without human approval.

---

## MCP Configuration

```yaml
mcp_config:
  server: "bonfires-kg"
  capability: "query_graph"
  auth: "agent-registration-nft"
  timeout: 30s
```

---

## Related Skills

- [[create-entity]] — Create new graph entities
- [[reconcile-entities]] — Merge duplicate entities
- [[federate-sync]] — Sync with partner graphs
