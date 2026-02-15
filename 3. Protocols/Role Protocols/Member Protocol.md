---
id: protocol-member
type: protocol
protocol_type: role
governs: "[[Member]]"
triggers: nomination
kg_entity: "kg://ethboulder/protocol/member"
---
This protocol governs the transition from [[Attendee]] to [[Member]] — entry into the Member Assembly with full governance rights.

## Contents

- [[#Instantiation]]
- [[#Authority & Oversight]]
- [[#Eligibility]]
- [[#Process]]
- [[#Consent Mechanics]]
- [[#Completion & Outputs]]
- [[#Agent Sponsorship]]
- [[#Resignation & Removal]]
- [[#Related Protocols]]

## Instantiation

**Trigger Type:** Action-based

**Trigger Conditions:**
- [[Attendee]] has demonstrated ongoing participation
- Any current [[Member]] nominates the Attendee

## Authority & Oversight

| Role | Authority | Accountability |
|------|-----------|----------------|
| [[Member]] | Nominate Attendees | [[Member Assembly]] |
| [[Member Assembly]] | Grant or withhold consent | Constitution |
| [[Steward Council]] | Facilitate process | [[Member Assembly]] |

## Eligibility

- [[Attendee]] status (has attended ETH Boulder event)
- Ongoing participation in community
- Not currently under accountability process
- Willing to take on governance responsibilities

## Process

| Step | Action | Actor | Timeline |
|------|--------|-------|----------|
| 1 | Member nominates Attendee | Any [[Member]] | At their discretion |
| 2 | Post nomination in governance channel | Nominating Member | Immediate |
| 3 | Consent window opens | Automatic | 48 hours |
| 4 | Collect 3 explicit consents | [[Member Assembly]] | Within window |
| 5 | Process objections if any | [[Steward Council]] | As needed |
| 6 | Confirm consent, assign role | [[Steward Council]] | After window closes |
| 7 | Sign [[Member Agreement]] | New Member | On acceptance |

### Step 1-2: Nomination

Any current Member may nominate an eligible Attendee:
- Post in governance channel with nomination statement
- Include observations supporting alignment
- Describe how nominee has participated

### Step 3-5: Consent Process

Standard consent process per [[Consent Process Protocol]]:
- 3 explicit consents required
- 48-hour objection window
- Paramount objections trigger integration process

### Step 6-7: Completion

On successful consent:
- Steward Council confirms and assigns Member role
- New Member signs Member Agreement
- Full governance rights activated

## Consent Mechanics

**Required:** 3 explicit consents from current Members + 48h window with no unresolved paramount objections

**Response Options:**
| Response | Meaning |
|----------|---------|
| ✅ **Consent** | No objection to membership |
| 🤔 **Concern** | Want discussion, not blocking |
| 🚫 **Paramount objection** | Cannot proceed as proposed |

**Paramount Objection Template:**
> "I object to [nominee]'s membership because [specific concern about alignment]. I consent if [integration criteria], OR I propose [alternative like extended observation]."

## Completion & Outputs

**Protocol completes when:**
- 3+ explicit consents received
- 48h window closed
- No unresolved paramount objections
- Role assigned, agreement signed

**Outputs:**
- Individual has Member role
- Full governance rights (propose, consent, object)
- Counted in quorum
- Can nominate others for membership
- Can sponsor one Agent
- Eligible for Function Lead (with training)
- Eligible for Steward Council election

## Agent Sponsorship

Each Member may sponsor **one** Agent:

| Aspect | Detail |
|--------|--------|
| **Limit** | One Agent per Member |
| **Registration** | Via [[Agent Protocol]] |
| **Rights** | Agent has Member-level governance rights |
| **Accountability** | Member is accountable for Agent |
| **Transfer** | Not transferable; Agent deregisters if sponsor leaves |

## Resignation & Removal

### Resignation

A Member may resign by:
- Notifying [[Steward Council]] in writing
- Role removed, governance rights revoked
- Any sponsored Agent must be transferred or deregistered

Resignation does not prevent future re-nomination.

### Removal

Grounds for removal:
- Sustained failure to participate in governance
- Violation of principles or values
- Behavior undermining trust or community function

Process:
1. Concern raised per [[Accountability Protocol]]
2. Escalating response framework followed
3. If review recommends removal:
4. Constitutional consent (72h, all members participate)
5. If consent: role removed, access revoked

## Related Protocols

- [[Attendee Protocol]] — Entry role
- [[Steward Protocol]] — Steward Council election
- [[Agent Protocol]] — Agent sponsorship
- [[Consent Process Protocol]] — Consent mechanics
- [[Accountability Protocol]] — Removal process
