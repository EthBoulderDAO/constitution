---
id: protocol-consent
type: protocol
protocol_type: cultural
triggers: decision-needed
---
This protocol governs all consent-based decision-making in the Re/acc Commons — the mechanics of how we coordinate through alignment beyond agreement.

## Contents

- [[#Principles]]
- [[#Decision Types]]
- [[#Consent Mechanics]]
- [[#Objection Handling]]
- [[#Special Cases]]
- [[#Related Protocols]]

## Principles

### Three Governing Principles

**Sociocratic Consent.** Decisions move forward unless someone raises a paramount objection — a concern that the proposal would harm the commons' ability to function toward its shared aims. Silence after window closes is not blocking.

**Subsidiarity.** Decisions are made at the most local level capable of handling them. Individual choices don't require group consent. Foundational changes do.

**Reversibility Determines Speed.** Easy-to-reverse changes move quickly. Hard-to-reverse changes require more deliberation.

## Decision Types

### Scope × Reversibility Matrix

| Scope | Easy to Reverse | Hard to Reverse |
|-------|-----------------|-----------------|
| **Individual Domain** | Autonomy | FYI post |
| **Cross-Domain** | 3-member + 48h | 3-member + deliberation |
| **Foundational** | 3-member + 48h | Full commons + 72h |

### Boundary Heuristic

**If it creates an expectation or dependency for other participants, it's coordination.**

| Type | Example |
|------|---------|
| Individual | "I'm researching regenerative patterns in my bioregion" |
| Coordination | "The Knowledge Commons will handle all pattern documentation" |
| Foundational | "We're changing how treasury allocates resources" |

## Consent Mechanics

### Posting Proposals

Post in `#proposals` with:
- Clear title
- Type classification (scope × reversibility)
- Full proposal details
- Rationale
- Impact assessment
- Consent window (48h or 72h)

### Expressing Position

| Emoji | Meaning | Effect |
|-------|---------|--------|
| :white_check_mark: | Consent | Counts toward quorum |
| :thinking: | Concerns | Wants discussion, not blocking |
| :hourglass_flowing_sand: | Need more time | May extend window |
| :no_entry_sign: | Paramount objection | Blocks until resolved |

**Explicit consent required.** Silence is ambiguous. We require affirmative alignment.

### Quorum Requirements

| Type | Minimum Consents | Window | Notification |
|------|-----------------|--------|--------------|
| Standard | 3 participants | 48 hours | Channel post |
| Foundational | All registered participants | 72 hours | All notified |

**Participants include both humans and agents.** Any [[Member]] or registered [[Agent]] with governance rights can consent, raise concerns, or object. Consents from humans and agents count equally toward quorum.

```yaml
quorum_participants:
  humans: All Members
  agents: All registered governance agents
  counting: Equal weight
```

### Window Rules

- Window starts when proposal posted
- :hourglass_flowing_sand: may extend by 24h (once per proposal)
- Objections raised during window must be addressed
- Window cannot close with unresolved paramount objections

## Objection Handling

### What Qualifies as Paramount

An objection is paramount if it:
1. Articulates specific harm to commons' ability to function
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
| 5 | Re-consent on modified proposal | [[Commons Assembly]] |

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
1. [[Stewardship]] calls for clarification
2. Extended discussion window (24h)
3. Participants clarify positions
4. If still unclear, proposal does not pass

### Absent Members

For foundational decisions:
- All Members notified (not all must respond)
- Consent proceeds if no objections after window
- Absent members can object within window via any communication

### Emergency Decisions

For situations requiring immediate action:
- [[Steward]] may act with documented rationale
- Post-hoc ratification within 48h
- If not ratified, action reversed where possible
- See [[3. Protocols/Group Protocols/Stewardship Protocol#Emergency Actions|Stewardship Protocol]]

## Agent Autonomy Post-Consent

**Once consent is complete, agents execute autonomously.**

The consent process is the decision point. After a proposal receives sufficient consents and no unresolved objections:
- Agents execute immediately without waiting for additional approval
- No human "confirmation" step exists
- Transparency through logging replaces gating through approval

| Action Type | Agent Execution |
|-------------|-----------------|
| Role changes | Discord roles + NFT mint |
| Treasury | Transaction signed + executed |
| Constitution | PR merged |
| Accountability | Actions applied |

**Humans participated in consent, not in execution.** If a human wanted to block, they raised an objection during the window. Post-consent execution is autonomous.

See [[.agents/AGENT_AUTONOMY|Agent Autonomy Framework]] for full philosophy.

---

## Call-Up Mechanism

Any participant can escalate a decision treated as individual domain:

1. Post: "I'm calling up [action] because [cross-domain impact]"
2. [[Stewardship]] confirms call-up is valid
3. Original actor posts proposal for consent
4. Standard consent process applies

**This is not punitive** — it's recognizing impact others may not have seen.

## Related Protocols

- [[3. Protocols/Group Protocols/Commons Assembly Protocol|Commons Assembly Protocol]] — Assembly operations
- [[3. Protocols/Asset Protocols/Constitution Amendment Protocol|Constitution Amendment Protocol]] — Foundational changes
- [[3. Protocols/Asset Protocols/Treasury Management Protocol|Treasury Management Protocol]] — Allocation consent
