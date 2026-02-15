---
id: protocol-member-assembly
type: protocol
protocol_type: group
governs: "[[Member Assembly]]"
kg_entity: "kg://ethboulder/protocol/member-assembly"
---
This protocol governs how the Member Assembly operates — how it makes decisions, handles proposals, and exercises governance authority.

## Composition

| Participant | Rights |
|-------------|--------|
| **Members** | Full governance (propose, consent, object) |
| **Agents** | Full governance (same as Members) |
| **Attendees** | May observe, cannot vote |

---

## Consent Process

All Assembly decisions follow the consent process:

### Proposal

| Step | Action | Actor |
|------|--------|-------|
| 1 | Post proposal | Any Member or Agent |
| 2 | Specify decision type | Proposer |
| 3 | Consent window opens | Automatic |

### Response

Members and Agents respond with:
- ✅ **Consent** — No objection
- 🤔 **Concern** — Want discussion before consenting
- 🚫 **Paramount objection** — Cannot proceed as proposed

### Resolution

| Situation | Action |
|-----------|--------|
| **Concerns raised** | Proposer addresses, discussion ensues |
| **Objection raised** | Must be resolved or proposal fails |
| **Window expires** | Tally responses, determine outcome |

### Outcome

| Outcome | Condition |
|---------|-----------|
| **Passed** | Quorum met, no unresolved objections |
| **Failed** | Quorum not met OR unresolved objections |

---

## Decision Types

| Type | Window | Quorum | Examples |
|------|--------|--------|----------|
| **Operational** | 48h | 3 members | Day-to-day decisions |
| **Membership** | 48h | 3 members | New member, agent registration |
| **Budget** | 48h | 3 members | Disbursements, grants |
| **Constitutional** | 72h | All members | Protocol changes, amendments |
| **Steward election** | 48h | All members | Council seat elections |

---

## Proposal Format

Proposals should include:

| Section | Content |
|---------|---------|
| **Title** | Clear, concise summary |
| **Type** | Decision type (determines window/quorum) |
| **Proposal** | What is being proposed |
| **Rationale** | Why this is proposed |
| **Impact** | Who/what is affected |

---

## Quorum

Quorum is counted at window close:

| Type | Quorum |
|------|--------|
| **Operational** | 3 members consented |
| **Membership** | 3 members consented |
| **Constitutional** | All members participated |

Abstention counts as non-participation (doesn't block quorum).

---

## Objections

### Valid Objections

Paramount objections must be:
- **Reasoned** — Based on stated concern
- **Relevant** — Related to the proposal
- **Resolvable** — Can be addressed through modification

### Resolution

| Step | Action |
|------|--------|
| 1 | Objector states concern |
| 2 | Proposer and Assembly discuss |
| 3 | Proposer may modify |
| 4 | Objector may withdraw |
| 5 | If unresolved, proposal fails |

---

## Emergency Decisions

For urgent matters:

| Authority | Action |
|-----------|--------|
| **Steward Council** | Can make emergency decisions |
| **Ratification** | Assembly ratifies within 24h |
| **Reversal** | Non-ratified actions reversed |

---

## Meeting Formats

| Format | When | Purpose |
|--------|------|---------|
| **Async** | Ongoing | Most governance |
| **Synchronous** | As needed | Complex discussions |
| **Post-event** | Annually | Retrospective |

---

## Recording

All decisions recorded:
- Posted in governance channel
- Logged in Knowledge Graph as Decision entity
- Linked to relevant entities

---

## Related

- [[Member Assembly]] — Group definition
- [[Member]] — Assembly participants
- [[Agent]] — Assembly participants
- [[Consent Process Protocol]] — Detailed consent mechanics
- [[Steward Council]] — Emergency authority
