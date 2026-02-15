---
id: asset-knowledge-graph
type: asset
access_level: tiered
stewardship: "[[Function Leads|Knowledge Lead]]"
kg_entity: "kg://ethboulder/asset/knowledge-graph"
mcp_server: "bonfires-kg"
---
The constitutional oracle — a knowledge graph encoding the network's relationships, decisions, and collective intelligence, queryable by agents and humans alike.

## Purpose

The Knowledge Graph is the primary asset of ETH Boulder. It is not merely documentation but an active **constitutional oracle** — the authoritative source for network state that resolves governance questions through queries.

The graph encodes:
- Who we are and how we relate
- What we've decided and why
- What we've learned and from whom
- How we federate with partner networks

## Why a Knowledge Graph

Traditional constitutions are static documents requiring human interpretation. The Knowledge Graph is a living database that:

- **Resolves ambiguity** — Query who current Stewards are instead of asking in Discord
- **Enables agent participation** — Agents can execute constitutional queries autonomously
- **Supports federation** — Shared schema enables interoperability with partner networks
- **Maintains history** — All changes tracked, reversions possible

## Location & Access

| Aspect | Detail |
|--------|--------|
| **Platform** | Bonfires Knowledge Graph |
| **Access** | MCP server (`bonfires-kg`) |
| **Backup** | GitHub export (read-only) |
| **Federation** | MCP-based sync with partner graphs |

## Access Tiers

**Everyone contributes to the Knowledge Graph.** This is a core principle.

| Tier | Who | Permissions |
|------|-----|-------------|
| **Read + Write** | [[Attendee\|Attendees]] | Read all, create entities, add relationships |
| **Curate** | [[Member\|Members]] | Above + reconcile duplicates, edit contested |
| **Full** | [[Agent\|Agents]] | All operations including federation sync |
| **Moderate** | [[Function Leads\|Knowledge Lead]] | Revert edits, protect entities, resolve disputes |

## Entity Types

The graph maintains these core entity types:

| Type | Schema | Example |
|------|--------|---------|
| **Person** | `kg://ethboulder/person/[id]` | Human participants |
| **Agent** | `kg://ethboulder/agent/[id]` | AI agents |
| **Role** | `kg://ethboulder/role/[name]` | Constitutional roles |
| **Group** | `kg://ethboulder/group/[name]` | Assembly, council, leads |
| **Asset** | `kg://ethboulder/asset/[name]` | Network assets |
| **Protocol** | `kg://ethboulder/protocol/[name]` | Governing protocols |
| **Decision** | `kg://ethboulder/decision/[id]` | Consent processes |
| **Session** | `kg://ethboulder/session/[id]` | Event sessions |
| **Project** | `kg://ethboulder/project/[name]` | Network projects |
| **ThirdSpace** | `kg://ethboulder/thirdspace/[name]` | Partner venues |

## Constitutional Queries

Common query patterns for constitutional questions:

### Role Queries
```cypher
# Current Steward Council
MATCH (p:Person)-[:HAS_ROLE]->(:Role {name: 'Steward', active: true})
RETURN p

# All Members (human + agent)
MATCH (p)-[:HAS_ROLE]->(:Role {name: 'Member', active: true})
RETURN p

# Current Function Leads
MATCH (p)-[:SERVES_AS]->(l:Lead)
WHERE l.active = true
RETURN p, l.function
```

### Governance Queries
```cypher
# Protocols governing treasury
MATCH (p:Protocol)-[:GOVERNS]->(:Asset {name: 'Treasury'})
RETURN p

# Consent required for decision type
MATCH (d:DecisionType {name: $type})-[:REQUIRES]->(c:ConsentLevel)
RETURN c
```

### Federation Queries
```cypher
# Third space partners
MATCH (ts:ThirdSpace)-[:PARTNER_OF]->(:Network {name: 'ETH Boulder'})
RETURN ts

# Federated network entities
MATCH (e:Entity)-[:FEDERATED_FROM]->(n:Network)
RETURN e, n
```

## Agent Capabilities

[[Agent|Agents]] interact with the graph via MCP:

```yaml
mcp_config:
  server: "bonfires-kg"
  capabilities:
    - query_graph        # Execute Cypher queries
    - create_entity      # Create new entities
    - update_entity      # Modify existing entities
    - reconcile_entities # Merge duplicates
    - federate_sync      # Sync with partner graphs
  auth: "agent-registration-nft"
```

## Graph Integrity

### Entity Creation
- All entities require proper typing
- Relationships must reference existing entities
- Agent-created entities flagged for human review if contested

### Entity Reconciliation
- Duplicates detected by agents, reconciled by Members
- Merges preserve all relationships
- Redirects maintained for old identifiers

### Protected Entities
- Constitutional documents (roles, protocols, assets)
- Historical decisions
- Federation agreements
- Protected entities require Knowledge Lead approval to modify

## Federation Sync

The graph synchronizes with partner networks via Bonfires MCP:

| Aspect | Protocol |
|--------|----------|
| **Sync Frequency** | Real-time for critical entities, daily for full sync |
| **Conflict Resolution** | Local authority for local entities, consensus for shared |
| **Schema Mapping** | Maintained by Knowledge Lead |

## Event Cycle Integration

| Phase | Graph Activities |
|-------|-----------------|
| **Inter-Event** | Ongoing maintenance, pattern documentation, federation sync |
| **Pre-Event** | Session entity creation, speaker profiles, venue mappings |
| **Event** | Real-time documentation, entity creation from sessions |
| **Post-Event** | Bulk enrichment, retrospective integration, relationship mapping |

## Accountability

**Auditability:**
- All changes logged with author and timestamp
- Version history for all entities
- Reversion possible by authorized roles

**Reporting:**
- Graph health metrics in `#knowledge`
- Monthly integrity review by Knowledge Lead
- Federation sync status dashboard

## Related Documents

- [[3. Protocols/Asset Protocols/Knowledge Graph Protocol|Knowledge Graph Protocol]] — Complete governance process
- [[Function Leads]] — Knowledge Lead responsibilities
- [[Agent]] — Agent capabilities for graph operations
- [[Federation Agreements]] — Partner network relationships
