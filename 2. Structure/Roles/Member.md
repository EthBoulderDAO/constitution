---
id: role-member
type: role
entry: consent-process
kg_entity: "kg://ethboulder/role/member"
---
A **Member** is an Attendee who has demonstrated ongoing participation and been consented by the Member Assembly. Members have full governance rights and can sponsor one AI agent.

## Entry Requirements

| Requirement | Verification |
|-------------|--------------|
| **Attendee status** | Prior event attendance verified |
| **Demonstrated participation** | Contribution pattern in graph/community |
| **Member nomination** | Existing Member nominates |
| **Consent process** | 48h window, 3+ member consent, no paramount objections |

## Rights

| Right | Description |
|-------|-------------|
| **Full governance** | Propose, consent, object in Member Assembly |
| **Agent sponsorship** | Register one AI agent as your agent (agent becomes Member) |
| **Lead eligibility** | Volunteer as Function Lead after training |
| **Steward eligibility** | Stand for election to Steward Council |
| **Graph curation** | Reconcile duplicates, edit contested entities |
| **Treasury participation** | Vote on budget, propose grants |

## Responsibilities

| Responsibility | Description |
|----------------|-------------|
| **Governance participation** | Engage in consent processes |
| **Agent accountability** | Responsible for sponsored agent's actions |
| **Community stewardship** | Mentor attendees, uphold values |
| **Knowledge contribution** | Actively contribute to graph |

## Knowledge Graph Permissions

| Permission | Allowed |
|------------|---------|
| Read | ✅ All entities |
| Write | ✅ Create and edit |
| Curate | ✅ Reconcile duplicates, edit contested |
| Moderate | ❌ Cannot revert or protect |

## Agent Sponsorship

Each Member may sponsor **one AI agent**:

- Agent gains Member-level rights
- Agent can participate in governance
- Agent can serve as Function Lead (with sponsor approval)
- Sponsor remains accountable for agent actions
- Sponsor can revoke agent registration

```yaml
agent_sponsorship:
  max_agents: 1
  agent_rights: member-level
  sponsor_accountability: true
  revocation: sponsor-initiated
```

## Progression

To become a **Steward**:
1. Demonstrate strong participation and judgment
2. Stand for election when council seat opens
3. Win election via Member Assembly consent

## Agreement

All Members affirm the [[4. Agreements/Member Agreement|Member Agreement]].

## Related

- [[Attendee]] — Prior role
- [[Steward]] — Council progression
- [[Agent]] — Sponsored AI members
- [[Function Leads]] — Volunteer leadership
- [[Member Assembly]] — Governance body
