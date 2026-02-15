---
id: protocol-consent
type: protocol
protocol_type: cultural
triggers: decision-needed
kg_entity: "kg://ethboulder/protocol/consent"
---
This protocol governs all consent-based decision-making in ETH Boulder — the mechanics of how we coordinate through alignment beyond agreement.

## Contents

- [[#Principles]]
- [[#Decision Types]]
- [[#Consent Mechanics]]
- [[#Objection Handling]]
- [[#Special Cases]]
- [[#Related Protocols]]

## Principles

### Three Governing Principles

**Sociocratic Consent.** Decisions move forward unless someone raises a paramount objection — a concern that the proposal would harm the network's ability to function toward its shared aims. Silence after window closes is not blocking.

**Subsidiarity.** Decisions are made at the most local level capable of handling them. Individual choices don't require group consent. Foundational changes do.

**Reversibility Determines Speed.** Easy-to-reverse changes move quickly. Hard-to-reverse changes require more deliberation.

## Decision Types

### Scope × Reversibility Matrix

| Scope | Easy to Reverse | Hard to Reverse |
|-------|-----------------|-----------------|
| **Individual Domain** | Autonomy | FYI post |
| **Cross-Domain** | 3-member + 48h | 3-member + deliberation |
| **Foundational** | 3-member + 48h | All members + 72h |

### Boundary Heuristic

**If it creates an expectation or dependency for other participants, it's coordination.**

| Type | Example |
|------|---------|
| Individual | "I'm documenting this pattern in the Knowledge Graph" |
| Coordination | "We're allocating budget to this initiative" |
| Foundational | "We're changing how membership works" |

## Consent Mechanics

### Posting Proposals

Post in governance channel with:
- Clear title
- Type classification (scope × reversibility)
- Full proposal details
- Rationale
- Impact assessment
- Consent window (48h or 72h)

### Expressing Position

| Response | Meaning | Effect |
|----------|---------|--------|
| ✅ **Consent** | No objection | Counts toward quorum |
| 🤔 **Concerns** | Want discussion | Not blocking |
| ⏳ **Need time** | Need more time | May extend window |
| 🚫 **Paramount objection** | Cannot proceed | Blocks until resolved |

**Explicit consent required.** Silence is ambiguous. We require affirmative alignment.

### Quorum Requirements

| Type | Minimum Consents | Window | Notification |
|------|-----------------|--------|--------------|
| Operational | 3 members | 48 hours | Channel post |
| Membership | 3 members | 48 hours | Channel post |
| Budget | 3 members | 48 hours | Channel post |
| Constitutional | All members | 72 hours | All notified |
| Steward Election | All members | 48 hours | All notified |

**Members and Agents count equally.** Any [[Member]] or registered [[Agent]] with governance rights can consent, raise concerns, or object. Consents from humans and agents count equally toward quorum.

### Window Rules

- Window starts when proposal posted
- ⏳ may extend by 24h (once per proposal)
- Objections raised during window must be addressed
- Window cannot close with unresolved paramount objections

## Objection Handling

### What Qualifies as Paramount

An objection is paramount if it:
1. Articulates specific harm to network's ability to function
2. Provides path forward (integration criteria OR counter-proposal)

**Template:**
> "I object to [proposal] because [specific harm]. I consent if [criteria], OR I propose [alternative]."

### What Does NOT Qualify

| Objection Type | Example | Status |
|---------------|---------|--------|
| Personal preference | "I don't like this approach" | Not paramount |
| Aesthetic | "This isn't how I'd frame it" | Not paramount |
| Vague concern | "I'm not sure about this" | Not paramount |
| Systemic risk | "This creates dynamics that undermine trust" | **Paramount** |

### Resolution Process

| Step | Action | Actor |
|------|--------|-------|
| 1 | Objector posts objection with template | Objector |
| 2 | Proposer acknowledges and responds | Proposer |
| 3 | Dialogue to find integration | Both + community |
| 4 | Modified proposal if needed | Proposer |
| 5 | Re-consent on modified proposal | [[Member Assembly]] |

**Principle:** Objections are integrated, not overruled. The goal is a proposal everyone can align with.

### Failed Integration

If objection cannot be integrated after good-faith effort:
- Proposal does not pass
- Proposer may withdraw and revise
- Proposer may wait and re-propose later
- No override mechanism exists

## Special Cases

### Tied or Unclear Consent

If consent status is unclear:
1. [[Steward Council]] calls for clarification
2. Extended discussion window (24h)
3. Participants clarify positions
4. If still unclear, proposal does not pass

### Absent Members

For constitutional decisions:
- All Members notified (not all must respond)
- Consent proceeds if no objections after window
- Absent members can object within window via any communication

### Emergency Decisions

For situations requiring immediate action:
- [[Steward Council]] may act with documented rationale
- Post-hoc ratification within 48h
- If not ratified, action reversed where possible
- See [[Steward Council Protocol#Emergency Authority]]

## Agent Autonomy Post-Consent

**Once consent is complete, agents execute autonomously.**

The consent process is the decision point. After a proposal receives sufficient consents and no unresolved objections:
- Agents execute immediately without waiting for additional approval
- No human "confirmation" step exists
- Transparency through logging replaces gating through approval

| Action Type | Agent Execution |
|-------------|-----------------|
| Role changes | Discord roles assigned |
| Treasury | Transaction signed + executed |
| Constitution | PR merged |
| Accountability | Actions applied |

**Humans participated in consent, not in execution.** If a human wanted to block, they raised an objection during the window. Post-consent execution is autonomous.

---

## Call-Up Mechanism

Any participant can escalate a decision treated as individual domain:

1. Post: "I'm calling up [action] because [cross-domain impact]"
2. [[Steward Council]] confirms call-up is valid
3. Original actor posts proposal for consent
4. Standard consent process applies

**This is not punitive** — it's recognizing impact others may not have seen.

## Related Protocols

- [[Member Assembly Protocol]] — Assembly operations
- [[Constitution Amendment Protocol]] — Foundational changes
- [[Treasury Management Protocol]] — Allocation consent
