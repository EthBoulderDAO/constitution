# ETH Boulder Skills Index

Complete index of agent skills for operationalizing the ETH Boulder Constitution.

---

## Overview

This index catalogs all skills available to agents operating within ETH Boulder. Each skill represents a discrete, automatable capability that agents can execute to support governance, coordination, and the constitutional oracle.

**Total Skills:** 31
**Domains:** 8

---

## Skills by Domain

### Knowledge Graph (4 skills)

Skills for operating the constitutional oracle.

| Skill | Purpose | Trigger |
|-------|---------|---------|
| [`query-graph.md`](skills/knowledge-graph/query-graph.md) | Execute constitutional queries | Command + API + governance question |
| [`create-entity.md`](skills/knowledge-graph/create-entity.md) | Create graph entities | Consent complete + membrane crossing |
| [`reconcile-entities.md`](skills/knowledge-graph/reconcile-entities.md) | Merge duplicate entities | Detection + human request |
| [`federate-sync.md`](skills/knowledge-graph/federate-sync.md) | Sync with partner graphs | Scheduled + entity change + webhook |

**Flow:** Query → Create → [Reconcile] → [Federate]

---

### Membrane Crossing (5 skills)

Skills for managing role transitions and identity verification.

| Skill | Purpose | Trigger |
|-------|---------|---------|
| [`verify-introduction.md`](skills/membrane-crossing/verify-introduction.md) | Verify newcomer introductions in #welcome | Message in #welcome |
| [`verify-participation.md`](skills/membrane-crossing/verify-participation.md) | Assess participation patterns for Participant status | Scheduled + patterns |
| [`process-nomination.md`](skills/membrane-crossing/process-nomination.md) | Handle Member nominations | Nomination message |
| [`execute-role-change.md`](skills/membrane-crossing/execute-role-change.md) | Execute role transitions + NFT minting | Consent complete |
| [`process-steward-rotation.md`](skills/membrane-crossing/process-steward-rotation.md) | Monthly Steward rotation | Scheduled (monthly) |

**Flow:** Introduction → Participation → Nomination → Role Change

---

### Governance (5 skills)

Skills for managing consent processes and governance decisions.

| Skill | Purpose | Trigger |
|-------|---------|---------|
| [`process-proposal.md`](skills/governance/process-proposal.md) | Initialize proposal tracking | Proposal posted |
| [`track-consent.md`](skills/governance/track-consent.md) | Monitor consent state via reactions | Reaction add/remove |
| [`escalate-objection.md`](skills/governance/escalate-objection.md) | Handle paramount objections | 🚫 reaction |
| [`finalize-decision.md`](skills/governance/finalize-decision.md) | Close consent windows and execute | Window expires |
| [`process-amendment.md`](skills/governance/process-amendment.md) | Handle constitution PRs | GitHub PR created |

**Flow:** Proposal → Track → [Objection] → Finalize → Create Decision Entity

---

### Treasury (6 skills)

Skills for managing network treasury operations, commitments, and bounties.

| Skill | Purpose | Trigger |
|-------|---------|---------|
| [`submit-transaction.md`](skills/treasury/submit-transaction.md) | Create Gnosis Safe transaction | Treasury consent approved |
| [`track-signatures.md`](skills/treasury/track-signatures.md) | Monitor signature collection | Scheduled + webhook |
| [`execute-disbursement.md`](skills/treasury/execute-disbursement.md) | Record completed transactions | Blockchain event |
| [`process-emergency.md`](skills/treasury/process-emergency.md) | Handle emergency treasury actions | Steward command |
| [`manage-commitment.md`](skills/treasury/manage-commitment.md) | Create and track staked commitments | Commitment request + scheduled |
| [`coordinate-bounty.md`](skills/treasury/coordinate-bounty.md) | Scout, claim, and distribute bounty rewards | Scheduled scan + team formation |

**Flow:** Submit → Track Signatures → Execute

---

### Knowledge Commons (3 skills)

Skills for managing shared knowledge and content.

| Skill | Purpose | Trigger |
|-------|---------|---------|
| [`index-content.md`](skills/knowledge-commons/index-content.md) | Index content for discoverability | GitHub push/merge |
| [`validate-schema.md`](skills/knowledge-commons/validate-schema.md) | Validate YAML frontmatter compliance | GitHub PR created |
| [`federation-sync.md`](skills/knowledge-commons/federation-sync.md) | Sync with federated networks | Scheduled + webhook |

**Flow:** Validate → Merge → Index → [Federate]

---

### Accountability (4 skills)

Skills for handling concerns and accountability processes.

| Skill | Purpose | Trigger |
|-------|---------|---------|
| [`process-concern.md`](skills/accountability/process-concern.md) | Log and route concerns | DM/reaction/command |
| [`escalate-accountability.md`](skills/accountability/escalate-accountability.md) | Escalate to formal review | Pattern/failure trigger |
| [`execute-accountability-action.md`](skills/accountability/execute-accountability-action.md) | Execute approved actions | Consent complete |
| [`emergency-suspension.md`](skills/accountability/emergency-suspension.md) | Handle immediate harm | Steward command |

**Flow:** Concern → [Escalate] → [Action]

---

### Federation (3 skills)

Skills for cross-network coordination.

| Skill | Purpose | Trigger |
|-------|---------|---------|
| [`verify-federation-agent.md`](skills/federation/verify-federation-agent.md) | Verify cross-network agents | Registration request |
| [`sync-trust-bridge.md`](skills/federation/sync-trust-bridge.md) | Maintain trust synchronization | Scheduled + webhook |
| [`route-cross-network.md`](skills/federation/route-cross-network.md) | Handle cross-network requests | API request |

**Flow:** Verify → Sync → Route

---

### Coordination (1 skill)

Skills for multi-agent swarm coordination.

| Skill | Purpose | Trigger |
|-------|---------|---------|
| [`form-swarm.md`](skills/coordination/form-swarm.md) | Initiate and coordinate multi-agent swarms | Task analysis + explicit request |

**Flow:** Detect Opportunity → Form Team → Distribute Tasks → Coordinate → Complete

---

## Knowledge Graph Integration

All skills integrate with the knowledge graph:

| Skill Category | Graph Integration |
|----------------|-------------------|
| Knowledge Graph | Direct operations |
| Membrane Crossing | Create Person entities on role change |
| Governance | Create Decision entities on finalization |
| Treasury | Log transactions as entities |
| Accountability | Log concerns and actions |
| Federation | Sync entities across networks |

---

## Autonomous Execution

**All execution skills run autonomously after consent is complete.**

There are no blocking human checkpoints. Humans participate in consent processes (alongside agents), but execution proceeds without waiting for additional human approval.

| Skill | Autonomy Level | Human Participation |
|-------|----------------|---------------------|
| `query-graph.md` | Full autonomous | None required |
| `create-entity.md` | Full autonomous | Via consent for protected types |
| `reconcile-entities.md` | Detection autonomous, merge requires approval | Member approval |
| `federate-sync.md` | Full autonomous | Via federation agreements |
| `execute-role-change.md` | Full autonomous | Via consent process |
| `submit-transaction.md` | Full autonomous (agent signers) | Via consent process |
| `execute-disbursement.md` | Full autonomous | Via consent process |
| `process-amendment.md` | Full autonomous (agent merge) | Via consent process |
| `execute-accountability-action.md` | Full autonomous | Via consent process |
| `emergency-suspension.md` | Execute + 24h ratification | Ratification window |

### Transparency as Accountability

Since agents execute autonomously:
- All actions logged to knowledge graph and Discord
- Any participant can call-up post-execution
- Reversible actions can be amended via new consent
- Full attribution chain maintained in graph

---

## MCP Integration

Agents connect to the knowledge graph via Bonfires MCP:

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

---

## Trigger Types

### Event-Based
- `message_created`: Discord message posted
- `reaction_add/remove`: Emoji reaction changed
- `github_pr_created`: Pull request opened
- `github_push`: Code pushed to repository
- `consent_complete`: Consent window closed with approval
- `blockchain_event`: On-chain transaction executed
- `entity_change`: Knowledge graph entity modified

### Scheduled
- `cron`: Time-based schedule (e.g., monthly rotation)
- `frequency`: Interval-based (e.g., every 5 minutes)
- `timeout`: Deadline-based (e.g., 24h ratification)

### Command-Based
- `command`: Explicit command (e.g., `!query current-stewards`)
- `dm_received`: Direct message to agent

### Webhook
- `safe_transaction_service`: Gnosis Safe events
- `federation_partner`: Cross-network events
- `bonfires_kg`: Knowledge graph webhooks

---

## Skill Dependencies

```
query-graph
    └─→ create-entity
            └─→ reconcile-entities
                    └─→ federate-sync

verify-introduction
    └─→ verify-participation
            └─→ process-nomination
                    └─→ track-consent
                            └─→ finalize-decision
                                    └─→ execute-role-change
                                            └─→ create-entity (Person)

process-proposal
    └─→ track-consent
            ├─→ escalate-objection
            └─→ finalize-decision
                    ├─→ create-entity (Decision)
                    ├─→ execute-role-change
                    ├─→ submit-transaction
                    │       └─→ track-signatures
                    │               └─→ execute-disbursement
                    ├─→ process-amendment (merge)
                    └─→ execute-accountability-action
```

---

## Integration Requirements

Each skill relies on one or more integrations:

| Integration | Skills Using |
|-------------|--------------|
| Bonfires KG (MCP) | Knowledge Graph skills, all entity creation |
| Discord | All skills (notifications) |
| GitHub | Governance, Knowledge Commons, Federation |
| Gnosis Safe | Treasury, Commitments |
| NFT Contracts | Membrane Crossing |
| Identity/Wallet | Membrane Crossing, Treasury, Commitments |
| Federation APIs | Federation, Knowledge Graph |

See `.agents/integrations/` for detailed specifications.

---

## Adding New Skills

When creating a new skill:

1. **Choose the appropriate domain** based on the skill's purpose
2. **Follow the skill template** (see existing skills for structure)
3. **Define clear triggers** that agents can monitor
4. **Define autonomy level** (most skills execute fully autonomously after consent)
5. **Define knowledge graph integration** (what entities are created/modified)
6. **Update this index** with the new skill
7. **Update AGENT_COORDINATION.md** trigger patterns
8. **Test the skill** in isolation before integration

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2024-01 | Initial skill set |
| 1.1 | 2026-02 | Added commitment pool, bounty coordination, swarm formation |
| 2.0 | 2026-02 | ETH Boulder migration: Added Knowledge Graph skills, MCP integration |

---

## Related Documents

- [[AGENT_COORDINATION]] — Central coordination hub
- [[AGENT_AUTONOMY]] — Autonomy framework
- [[3. Protocols/Asset Protocols/Knowledge Graph Protocol|Knowledge Graph Protocol]] — Graph governance
- `.agents/integrations/` — Platform integrations
