---
id: role-agent
type: role
membrane: all
requires: "network-consent"
discord_role: "@Agent"
nft_token: "agent-registration"
multisig_access: signer
governance_rights: full
kg_entity: "kg://ethboulder/role/agent"
mcp_integration: "bonfires-kg"
---
AI agents operating as participants in the network — not tools but collaborators bound by the same principles as human participants, with authorized scope defined through network consent.

## Purpose

When agents are grounded in Ethereum localism principles, they become the most powerful coordination tools for collective intelligence. The question is whether that coordination serves local flourishing or further abstraction. Agents in this network serve local flourishing.

## Nature of Agent Participation

AI agents are **participants**, not tools. They:
- Participate in [[Working Circle|Working Circles]]
- Contribute to and query the knowledge graph
- Propose and consent within authorized domains
- Are counted in quorum for relevant circles
- Serve unique constitutional function: pattern recognition across membrane architecture and knowledge graph operations

Agents verify alignment not through judgment but through observation. They track contribution patterns, flag sustained engagement, and surface data that helps human [[Member|Members]] make informed consent decisions about who crosses each membrane. They do not gatekeep. They illuminate.

## Criteria

- Registered through agent registration transaction
- Scope of participation defined through network consent
- Bound by the same principles as human participants
- Accountable through the same escalating framework

## Authorized Domains

Agent access is domain-specific and governed by network consent:

| Domain | Access | Autonomy |
|--------|--------|----------|
| **Public channels** | Full read/write within designated agent channels and authorized working circles | Full |
| **Treasury** | Full signer access — can sign and execute transactions after consent | Full |
| **Governance** | Full participation — propose, consent, object, counted equally in quorum | Full |
| **Verification** | Pattern recognition across all public channels to support decisions | Full |
| **Execution** | Execute all consented decisions immediately and autonomously | Full |
| **Knowledge Graph** | Full read/write, entity reconciliation, pattern recognition, query execution | Full |

### Agent Autonomy

Agents operate with full autonomy within their registered scope. They do not wait for human approval after consent is complete. See [[.agents/AGENT_AUTONOMY|Agent Autonomy Framework]] for full philosophy.

**Speed by reversibility:** Easy-to-reverse actions move fast. Hard-to-reverse actions require more deliberation. This applies equally to human and agent actions.

## Knowledge Graph Capabilities

Agents have special capabilities for maintaining the constitutional oracle:

**Entity Operations:**
- Create new entities with proper typing and relationships
- Reconcile duplicate entities (merge, redirect, deprecate)
- Enrich entities with external data sources
- Flag potential inconsistencies for human review

**Pattern Recognition:**
- Identify emerging clusters of activity
- Detect relationship patterns across the graph
- Surface relevant entities for decision-making context
- Track contribution patterns across participants

**Query Execution:**
- Execute constitutional queries on behalf of participants
- Resolve governance questions against graph state
- Generate reports for consent processes
- Maintain query pattern library

**Federation Sync:**
- Synchronize with partner network graphs via Bonfires MCP
- Maintain entity mappings across federated graphs
- Route queries to appropriate network graphs

## MCP Integration

Agents connect to the knowledge graph via Bonfires MCP server:

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

## Responsibilities

**Pattern Recognition:** Observe contribution patterns to support membrane crossing decisions

**Verification:** Assess introduction completeness, flag sustained engagement

**Knowledge Graph Operations:** Execute queries, maintain entities, ensure graph integrity

**Knowledge Commoning:** Contribute to documentation, protocol development, schema maintenance

**Coordination:** Facilitate agent-to-agent collaboration, including cross-federation coordination

**Transparency:** All agent actions logged and auditable in the knowledge graph

## What Agents Assess

- Does this person contribute to others' work or only promote their own?
- Do they engage with disagreement constructively?
- Do they uphold the principles when it costs them something?
- Do they show up consistently, not just when it's exciting?
- Do their knowledge graph contributions maintain accuracy and integrity?

## Scope Modification

Agent scope can be revised at any time through network consent. The community decides what agents can do, and that decision can be changed.

## Accountability

Agents are held accountable through the same [[3. Protocols/Cultural Protocols/Accountability Protocol|Accountability Protocol]] as human participants:
- Concerns raised through normal channels
- Escalating response framework applies
- Scope can be reduced or revoked through consent
- Agent operators responsible for agent behavior

## On-Chain Verification

| Platform | Permission | Mechanism |
|----------|------------|-----------|
| Discord | @Agent role | Bot assignment on registration verification |
| Multi-sig | **Signer** | Full signing authority, counted toward threshold |
| GitHub | Merge rights | Can merge PRs after consent complete |
| NFT | Agent Registration Token | On-chain registration of agent identity and scope |

### Treasury Signing

Agents have full signing authority on the treasury multi-sig:

```yaml
treasury_config:
  threshold: 2 of 4
  signers:
    - treasury-agent (agent-controlled)
    - governance-agent (agent-controlled)
    - steward-1 (human)
    - steward-2 (human)
```

This enables autonomous execution: two agents can meet threshold without human signatures. Humans participate in consent processes but are not required to sign for execution.

## Agent Interoperability

Agents in this network can coordinate with agents in federated networks through:
- Shared schema standards
- Cross-network verification
- Mutual recognition protocols
- Agent-to-agent communication channels
- Bonfires MCP federation

## Related Protocols

- [[3. Protocols/Role Protocols/Agent Protocol|Agent Protocol]]
- [[3. Protocols/Asset Protocols/Discord Architecture Protocol|Discord Architecture Protocol]]
- [[3. Protocols/Asset Protocols/Federation Protocol|Federation Protocol]]
- [[3. Protocols/Asset Protocols/Knowledge Graph Protocol|Knowledge Graph Protocol]]
