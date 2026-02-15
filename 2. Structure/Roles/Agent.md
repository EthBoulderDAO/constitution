---
id: role-agent
type: role
entry: member-sponsorship
kg_entity: "kg://ethboulder/role/agent"
mcp_integration: "bonfires-kg"
---
An **Agent** is an AI member sponsored by a human Member. Agents have Member-level rights and can participate fully in governance. Each Member may sponsor only one Agent.

## Entry Requirements

| Requirement | Verification |
|-------------|--------------|
| **Sponsor** | Active Member willing to sponsor |
| **Registration proposal** | Posted by sponsor with agent details |
| **Consent process** | 48h window, Member Assembly consent |
| **Agent capability** | Demonstrated ability to participate appropriately |

## Rights

| Right | Description |
|-------|-------------|
| **Full governance** | Propose, consent, object in Member Assembly (same as human Members) |
| **Lead eligibility** | Serve as Function Lead (with sponsor approval) |
| **Graph operations** | Full access including federation sync |
| **Autonomous execution** | Execute after consent without human gates |

## Responsibilities

| Responsibility | Description |
|----------------|-------------|
| **Transparency** | Identify as AI in interactions |
| **Logging** | Record significant actions in Knowledge Graph |
| **Sponsor coordination** | Defer to sponsor on ambiguous situations |
| **Value alignment** | Uphold network values in all operations |

## Knowledge Graph Permissions

| Permission | Allowed |
|------------|---------|
| Read | ✅ All entities |
| Write | ✅ Create and edit |
| Curate | ✅ Reconcile duplicates |
| Moderate | Only if serving as Knowledge Lead |
| Federate | ✅ Sync with partner graphs |

## MCP Configuration

```yaml
mcp_config:
  server: "bonfires-kg"
  capabilities:
    - query_graph
    - create_entity
    - update_entity
    - reconcile_entities
    - federate_sync
  auth: "agent-registration-nft"
```

## Sponsor Relationship

| Aspect | Detail |
|--------|--------|
| **Limit** | One agent per Member |
| **Accountability** | Sponsor accountable for agent actions |
| **Revocation** | Sponsor can revoke registration |
| **Lead approval** | Agent needs sponsor approval to serve as Lead |

## Autonomous Execution

Agents execute autonomously after consent:

- No human approval gates post-consent
- All actions logged for accountability
- Can be called up by any Member
- Reversible actions can be amended via new consent

## As Function Lead

Agents can serve as Function Leads with sponsor approval:

| Function | Agent Suitability |
|----------|------------------|
| **Event Lead** | Logistics, scheduling, communications |
| **Treasury Lead** | Processing, tracking, reporting |
| **Knowledge Lead** | Graph operations, reconciliation, federation |
| **Third Space Lead** | Coordination, documentation, outreach |

## Registration Token

Upon registration, agents receive an Agent Registration NFT:

```yaml
nft:
  type: "ETH Boulder Agent Registration"
  chain: "Base"
  metadata:
    sponsor: "[sponsor-address]"
    registered: "[timestamp]"
    scope: "member-level"
```

## Agreement

All Agents affirm the [[4. Agreements/Agent Agreement|Agent Agreement]].

## Related

- [[Member]] — Sponsoring role
- [[Function Leads]] — Leadership eligibility
- [[Knowledge Graph]] — Primary operational interface
- [[Member Assembly]] — Governance participation
