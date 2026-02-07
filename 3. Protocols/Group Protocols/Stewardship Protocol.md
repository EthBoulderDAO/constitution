---
id: protocol-stewardship
type: protocol
protocol_type: group
governs: "[[Stewardship]]"
triggers: coordination
---
This protocol governs the operations of [[Stewardship]] — the rotating curator council that facilitates commons governance and executes decisions.

## Contents

- [[#Instantiation]]
- [[#Authority & Oversight]]
- [[#Core Functions]]
- [[#Decision Authority]]
- [[#Coordination Practices]]
- [[#Handoff Protocol]]
- [[#Emergency Actions]]
- [[#Related Protocols]]

## Instantiation

**Trigger Type:** Continuous operation

**Trigger Conditions:**
- Stewardship is always active when the commons has seated Stewards
- Specific actions triggered by governance events, accountability needs, or treasury operations

## Authority & Oversight

| Role | Authority | Accountability |
|------|-----------|----------------|
| [[Stewardship]] | Facilitation, execution | [[Commons Assembly]] |
| Individual [[Steward]] | Emergency action (with ratification) | [[Stewardship]] |
| [[Commons Assembly]] | All governance decisions | Constitution |

**Critical:** Stewardship facilitates and executes. It does not govern. The moment stewardship becomes governance, it has failed.

## Core Functions

### Facilitation

| Function | Description |
|----------|-------------|
| **Process Facilitation** | Ensure consent processes followed correctly |
| **Clarification** | Call for clarification when proposals are ambiguous |
| **Escalation** | Call for escalation when consent is contested |
| **Documentation** | Maintain `#stewardship` channel with transparent records |

### Execution

| Function | Description |
|----------|-------------|
| **Constitution** | Merge governance PRs after consent documented |
| **Treasury** | Sign multisig transactions after proper approval |
| **Roles** | Execute role changes after consent processes complete |
| **Accountability** | Facilitate (not decide) accountability processes |

### What Stewardship Does NOT Do

- Make tiebreaker decisions
- Veto community decisions
- Have final say on content or direction
- Have greater weight in consent processes
- Initiate treasury allocations
- Judge alignment (only facilitate processes)

## Decision Authority

| Decision Type | Authority | Process |
|--------------|-----------|---------|
| Internal coordination | Stewardship | Consensus among Stewards |
| Facilitation questions | Stewardship | Coordination call |
| Governance decisions | [[Commons Assembly]] | Stewardship facilitates only |
| Emergency actions | Individual Steward | With 48h ratification |

## Coordination Practices

### Communication

- Stewards coordinate through `#stewardship` channel and direct communication
- Async coordination preferred, sync calls as needed
- Weekly check-in recommended (not required)

### Workload Distribution

- Divide ongoing responsibilities among active Stewards
- Cover for each other during unavailability
- Document task assignments in `#stewardship`

### Decision-Making

For internal Stewardship decisions:
- Seek consensus among current Stewards
- If blocked, defer to community input via `#proposals`
- Document decisions and rationale

## Handoff Protocol

Monthly rotation requires structured handoff:

| Step | Action | Timeline |
|------|--------|----------|
| 1 | Outgoing Steward documents active items | Before rotation |
| 2 | Overlap period begins | 2-3 days |
| 3 | Walkthrough of active processes | Day 1 of overlap |
| 4 | Multi-sig access updated | Day 1-2 |
| 5 | Discord admin transferred | Day 1-2 |
| 6 | Introduction in `#stewardship` | Day 2-3 |
| 7 | Outgoing access revoked | End of overlap |

### Handoff Documentation

Outgoing Steward documents:
- Active governance processes
- Pending accountability matters
- Treasury operations in progress
- Upcoming consent windows
- Any context new Steward needs

## Emergency Actions

For actions posing immediate harm:

| Situation | Authority | Constraint |
|-----------|-----------|------------|
| Doxxing | Any Steward | Immediate suspension |
| Harassment | Any Steward | Immediate suspension |
| Treasury threat | Any Steward | Freeze pending actions |

**Ratification requirement:** All emergency actions require Stewardship ratification within 48 hours. Actions not ratified are automatically reversed.

**Documentation:** All emergency actions documented with:
- Triggering incident
- Action taken
- Rationale
- Ratification outcome

## Transparency

All Stewardship activity is transparent:
- `#stewardship` channel visible to all [[Member|Members]]
- Decision rationale documented
- No private decision-making on commons matters

## Related Protocols

- [[3. Protocols/Role Protocols/Steward Protocol|Steward Protocol]] — Individual Steward lifecycle
- [[3. Protocols/Asset Protocols/Treasury Management Protocol|Treasury Management Protocol]] — Signing operations
- [[3. Protocols/Cultural Protocols/Accountability Protocol|Accountability Protocol]] — Process facilitation
- [[3. Protocols/Group Protocols/Commons Assembly Protocol|Commons Assembly Protocol]] — What Stewardship facilitates
