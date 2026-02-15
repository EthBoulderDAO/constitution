---
id: protocol-amendment
type: protocol
protocol_type: asset
governs: "[[ETH Boulder Constitution]]"
triggers: amendment-proposal
kg_entity: "kg://ethboulder/protocol/amendment"
---
This protocol governs amendments to the [[ETH Boulder Constitution]] — the living interpretation of our canonical framework.

## Contents

- [[#Instantiation]]
- [[#Authority & Oversight]]
- [[#Scope]]
- [[#Amendment Process]]
- [[#Documentation]]
- [[#Related Protocols]]

## Instantiation

**Trigger Type:** Action-based

**Trigger Conditions:**
- Any [[Member]] proposes constitutional change

## Authority & Oversight

| Role | Authority | Accountability |
|------|-----------|----------------|
| [[Member]] | Propose amendments | [[Member Assembly]] |
| [[Member Assembly]] | Grant or withhold consent | Constitution |
| [[Steward Council]] | Facilitate process, merge PRs | Member Assembly |

## Scope

### What Can Be Amended

- Role definitions and criteria
- Group structures and operations
- Protocol procedures
- Asset governance
- Agreement templates
- Identity interpretations (Vision, Mission, Functions, Mandates, Values)

### What Cannot Be Amended

- **[[Ethereum Localism Principles]]** — The foundational principles are permanent source text
- **Core Principles** — Localism, collective intelligence, consent governance
- **This Amendment Process** — Cannot be amended to reduce consent requirements

### Amendment Types

| Type | Scope | Process |
|------|-------|---------|
| **Clarification** | Wording improvements, no meaning change | 3-member consent + 48h |
| **Minor** | Procedure changes, threshold adjustments | 3-member consent + 48h |
| **Substantial** | Role changes, new protocols, governance structure | All members + 72h |
| **Foundational** | Core identity, major structural change | All members + 72h + extended deliberation |

## Amendment Process

| Step | Action | Actor | Timeline |
|------|--------|-------|----------|
| 1 | Draft amendment | Proposer | As needed |
| 2 | Open Pull Request on [[GitHub Repository]] | Proposer | Initiates process |
| 3 | Post in governance channel with PR link | Proposer | Immediate |
| 4 | Notify all Members | [[Steward Council]] or Bot | Immediate |
| 5 | Discussion period | [[Member Assembly]] | Varies |
| 6 | Consent window | Member Assembly | 48h or 72h |
| 7 | Process objections | [[Steward Council]] | As raised |
| 8 | Document consent in PR | Steward | After window |
| 9 | Merge PR | Steward | After consent documented |
| 10 | Update Records/Amendments | Steward | Post-merge |

### PR Template

```
## Amendment Proposal

**Type:** [Clarification / Minor / Substantial / Foundational]
**Proposer:** [Name]

### Summary
[Brief description of what's changing]

### Rationale
[Why this change is needed]

### Changes
[List of specific files/sections being modified]

### Impact
[Who/what is affected by this change]

### Consent Record
[To be filled during consent process]
- [ ] 3 Member consents (or All Members for Foundational)
- [ ] 48h/72h window complete
- [ ] No unresolved paramount objections
```

## Documentation

Each amendment is recorded with:
- **Change:** What was modified
- **Rationale:** Why it was changed
- **Proposer:** Who proposed it
- **Consent Record:** Who consented, any objections and resolution
- **Date:** When adopted

### Version History

All previous versions remain accessible through git history. The history of governance is itself a knowledge commons.

## Interpretation

When constitutional interpretation is contested:
1. Reference [[Ethereum Localism Principles]] as source text
2. Consider original intent of the provision
3. If still unclear, submit clarification proposal
4. [[Member Assembly]] makes authoritative interpretation through consent

## Related Protocols

- [[Member Assembly Protocol]] — Consent process
- [[Consent Process Protocol]] — Consent mechanics
- [[ETH Boulder Constitution]] — Asset documentation
- [[GitHub Repository]] — Storage and version control
