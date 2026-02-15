---
id: protocol-knowledge-graph
type: protocol
protocol_type: asset
governs: "[[Knowledge Graph]]"
triggers: entity-operation
kg_entity: "kg://ethboulder/protocol/knowledge-graph"
---
This protocol governs the stewardship, operation, and federation of the [[Knowledge Graph]] — the constitutional oracle that encodes the network's relationships, decisions, and collective intelligence.

## Contents

- [[#Principles]]
- [[#Entity Operations]]
- [[#Query Patterns]]
- [[#Access Control]]
- [[#Reconciliation]]
- [[#Federation Sync]]
- [[#Related Protocols]]

## Principles

**Constitutional authority.** The knowledge graph is the authoritative source for network state. When the graph and other sources conflict, the graph is correct (assuming integrity verification passes).

**Query-first governance.** Constitutional questions are answered by queries, not interpretation. "Who are current Stewards?" is a database query, not a discussion.

**Transparent history.** All changes are logged with author and timestamp. The graph maintains version history for all entities.

**Federation-ready.** Schema design enables interoperability with partner network graphs via MCP.

## Entity Operations

### Creating Entities

| Step | Action | Actor | Notes |
|------|--------|-------|-------|
| 1 | Identify entity type | Contributor | Must match defined schema |
| 2 | Construct entity with required fields | Contributor | Per schema below |
| 3 | Establish relationships | Contributor | Reference existing entities |
| 4 | Submit entity | Contributor | Via MCP or UI |
| 5 | Validate schema | Agent | Automated |
| 6 | Flag for review if contested | Agent | If conflicts detected |

### Entity Schema

All entities require:

```yaml
entity:
  id: "kg://ethboulder/[type]/[identifier]"
  type: [Person|Agent|Role|Group|Asset|Protocol|Decision|Session|Project|ThirdSpace]
  created_at: [ISO-8601 timestamp]
  created_by: [creator entity ID]
  status: [active|archived|pending]
```

Type-specific fields vary by entity type. See [[Knowledge Graph]] for complete schema.

### Who Can Create

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

### Updating Entities

| Permission Level | Can Update | Process |
|-----------------|------------|---------|
| Participants | Entities they created | Direct |
| Members | Any non-protected entity | Direct |
| Stewards | Protected entities | With rationale |
| Agents | Within authorized scope | Logged |

### Protected Entities

The following entities are protected and require Steward approval to modify:

- All Role entities
- All Protocol entities
- All Asset entities (except status)
- Historical Decision entities
- Federation Agreement entities

## Query Patterns

### Standard Queries

The graph maintains a library of constitutional query patterns:

| Query | Cypher Pattern | Purpose |
|-------|---------------|---------|
| `current-stewards` | `MATCH (p:Person)-[:HAS_ROLE]->(:Role {name: 'Steward', active: true})` | Who are current Stewards? |
| `eligible-members` | `MATCH (p:Person)-[:HAS_ROLE]->(:Role {name: 'Participant'}) WHERE p.active_weeks >= 2` | Who is eligible for membership? |
| `treasury-protocols` | `MATCH (p:Protocol)-[:GOVERNS]->(:Asset {name: 'Treasury'})` | What protocols govern treasury? |
| `consent-required` | `MATCH (d:DecisionType {name: $type})-[:REQUIRES]->(c:ConsentLevel)` | What consent for decision X? |
| `role-requirements` | `MATCH (r:Role {name: $role})-[:REQUIRES]->(req)` | What are requirements for role Y? |

### Creating New Query Patterns

| Step | Action | Actor |
|------|--------|-------|
| 1 | Identify recurring constitutional question | Any participant |
| 2 | Draft Cypher query | Knowledge Circle |
| 3 | Test against graph | Agent |
| 4 | Document in query library | Knowledge Circle |
| 5 | Submit to pattern library | Knowledge Circle |

## Access Control

### Tiered Access

| Tier | Who | Permissions |
|------|-----|-------------|
| **Read** | Newcomers | View public entities |
| **Write** | Participants+ | Create/edit entities |
| **Curate** | Members | Reconcile entities, approve contested edits |
| **Moderate** | Stewards | Revert edits, protect entities, resolve disputes |
| **Full** | Authorized Agents | All operations including federation sync |

### MCP Access

Agents access the graph via Bonfires MCP:

```yaml
mcp_capabilities:
  query_graph: [all authorized agents]
  create_entity: [authorized agents, per entity type]
  update_entity: [authorized agents, per entity type]
  reconcile_entities: [agents with reconcile scope]
  federate_sync: [federation agents only]
```

## Reconciliation

### Detecting Duplicates

Agents automatically flag potential duplicates based on:
- Name similarity (fuzzy matching)
- Overlapping relationships
- Conflicting identifiers

### Reconciliation Process

| Step | Action | Actor |
|------|--------|-------|
| 1 | Agent flags potential duplicate | Agent |
| 2 | Human review of flagged entities | Member |
| 3 | Decide: merge, keep separate, or defer | Member |
| 4 | If merge: execute reconciliation | Agent |
| 5 | Maintain redirect from old ID | Agent |

### Merge Rules

- Newer entity merged into older (preserve history)
- All relationships preserved
- Conflicting properties flagged for human decision
- Redirects maintained permanently

## Federation Sync

### Sync Protocol

Federated networks synchronize via MCP:

| Aspect | Protocol |
|--------|----------|
| **Frequency** | Real-time for critical entities, daily for full sync |
| **Direction** | Bidirectional with conflict detection |
| **Mapping** | Schema mappings maintained by Knowledge Circle |

### Sync Process

| Step | Action |
|------|--------|
| 1 | Federation agent initiates sync |
| 2 | Compare checksums for changed entities |
| 3 | Pull changed entities from partner |
| 4 | Apply schema mapping |
| 5 | Detect conflicts |
| 6 | Auto-resolve where possible, flag otherwise |
| 7 | Log sync completion |

### Conflict Resolution

| Conflict Type | Resolution |
|---------------|------------|
| Local-only entity | Accept (local authority) |
| Remote-only entity | Import with federation tag |
| Different values | Flag for human review |
| Relationship conflict | Flag for human review |

## Integrity Verification

### Automated Checks

Agents run regular integrity checks:
- Schema validation (all required fields present)
- Relationship integrity (all references valid)
- Duplicate detection
- Orphan detection (entities with no relationships)

### Audit Trail

All changes logged with:
- Timestamp
- Actor (human or agent)
- Previous value
- New value
- Rationale (if provided)

## Related Protocols

- [[Knowledge Circle]] — Stewardship body
- [[3. Protocols/Asset Protocols/Federation Protocol|Federation Protocol]] — Cross-network coordination
- [[3. Protocols/Role Protocols/Agent Protocol|Agent Protocol]] — Agent graph operations
