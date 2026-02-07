---
id: protocol-amendment
type: protocol
protocol_type: asset
governs: "[[Commons Constitution]]"
triggers: amendment-proposal
---
This protocol governs amendments to the [[Commons Constitution]] — the living interpretation of our canonical framework.

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
- Any [[Member]] or [[Working Circle]] proposes constitutional change

## Authority & Oversight

| Role | Authority | Accountability |
|------|-----------|----------------|
| [[Member]] / [[Working Circle]] | Propose amendments | [[Commons Assembly]] |
| [[Commons Assembly]] | Grant or withhold consent | Constitution |
| [[Stewardship]] | Facilitate process, merge PRs | Commons Assembly |

## Scope

### What Can Be Amended

- Role definitions and criteria
- Group structures and operations
- Protocol procedures
- Asset governance
- Agreement templates
- Identity interpretations (Vision, Mission, Functions, Mandates, Values)

### What Cannot Be Amended

- **[[Canonical Essay]]** — The manifesto is permanent source text
- **Core Principles** — Life-affirming acceleration, recursive criterion, consent governance
- **This Amendment Process** — Cannot be amended to reduce consent requirements

### Amendment Types

| Type | Scope | Process |
|------|-------|---------|
| **Clarification** | Wording improvements, no meaning change | 3-member consent + 48h |
| **Minor** | Procedure changes, threshold adjustments | 3-member consent + 48h |
| **Substantial** | Role changes, new protocols, governance structure | Full commons consent + 72h |
| **Foundational** | Core identity, major structural change | Full commons consent + 72h + extended deliberation |

## Amendment Process

| Step | Action | Actor | Timeline |
|------|--------|-------|----------|
| 1 | Draft amendment | Proposer | As needed |
| 2 | Open Pull Request on [[GitHub Repository]] | Proposer | Initiates process |
| 3 | Post in `#proposals` with PR link | Proposer | Immediate |
| 4 | Notify all Members | [[Steward]] or Bot | Immediate |
| 5 | Discussion period | [[Commons Assembly]] | Varies |
| 6 | Consent window | Commons Assembly | 48h or 72h |
| 7 | Process objections | [[Stewardship]] | As raised |
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
1. Reference [[Canonical Essay]] as source text
2. Consider original intent of the provision
3. If still unclear, submit clarification proposal
4. [[Commons Assembly]] makes authoritative interpretation through consent

## Related Protocols

- [[3. Protocols/Group Protocols/Commons Assembly Protocol|Commons Assembly Protocol]] — Consent process
- [[3. Protocols/Cultural Protocols/Consent Process Protocol|Consent Process Protocol]] — Consent mechanics
- [[2. Structure/Assets/Commons Constitution|Commons Constitution]] — Asset documentation
- [[2. Structure/Assets/GitHub Repository|GitHub Repository]] — Storage and version control
