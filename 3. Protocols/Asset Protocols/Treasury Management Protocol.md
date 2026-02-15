---
id: protocol-treasury
type: protocol
protocol_type: asset
governs: "[[Event Treasury]]"
triggers: allocation-request
kg_entity: "kg://ethboulder/protocol/treasury"
---
This protocol governs all operations of the [[Event Treasury]] — the shared economic engine of ETH Boulder.

## Contents

- [[#Instantiation]]
- [[#Authority & Oversight]]
- [[#Allocation Categories]]
- [[#Approval Thresholds]]
- [[#Proposal Process]]
- [[#Disbursement]]
- [[#Reporting]]
- [[#Emergency Operations]]
- [[#Related Protocols]]

## Instantiation

**Trigger Type:** Action-based

**Trigger Conditions:**
- Allocation proposal submitted
- Disbursement request for approved allocation
- Reporting period reached

## Authority & Oversight

| Role | Authority | Accountability |
|------|-----------|----------------|
| [[Member Assembly]] | Approve allocations | Constitution |
| [[Steward Council]] | Sign transactions, facilitate process | Member Assembly |
| [[Function Leads]] | Propose allocations for function | Member Assembly |
| [[Agent]] | Propose, sign, execute (2/4 threshold) | Sponsor Member |
| [[Member]] | View all transactions | Community trust |

### Treasury Signers

The treasury multi-sig includes Steward Council members and registered Agents:

```yaml
treasury_signers:
  threshold: 2 of 4+
  signers:
    - steward-1 (human)
    - steward-2 (human)
    - steward-3 (human)
    - registered-agent (agent-controlled)
```

This enables execution after consent is complete.

## Allocation Categories

| Category | Purpose |
|----------|---------|
| **Event Operations** | Venue, logistics, speakers, hackathon for annual convening |
| **Knowledge Graph** | Tooling, hosting, agent compute for documentation and federation |
| **Third Space** | Partnership support, venue cultivation |
| **Grants** | QF rounds, hackathon prizes, ecosystem funding |
| **Mutual Aid** | Direct support for participants facing acute need |
| **Operational** | Small recurring costs for network infrastructure |

## Approval Thresholds

| Amount/Type | Authority | Process |
|-------------|-----------|---------|
| Operational (≤ $500) | Treasury Lead | FYI post in treasury channel |
| Standard ($500-$5,000) | [[Member Assembly]] | 3-member consent + 48h |
| Large (> $5,000) | [[Member Assembly]] | All members + 72h |
| Structural changes | [[Member Assembly]] | All members + 72h |

*Thresholds can be adjusted through constitutional consent.*

## Proposal Process

| Step | Action | Actor | Timeline |
|------|--------|-------|----------|
| 1 | Draft proposal | Proposer | As needed |
| 2 | Function Lead review (recommended) | Function Lead | 1 week |
| 3 | Post in treasury channel | Proposer | Initiates process |
| 4 | Consent window | [[Member Assembly]] | 48h or 72h |
| 5 | Process objections | [[Steward Council]] | As needed |
| 6 | Confirm consent | [[Steward Council]] | After window |
| 7 | Execute transaction | Signers | Within 48h of consent |

### Proposal Template

```
**Allocation Request**
**Title:** [Clear title]
**Amount:** [Requested amount]
**Category:** [From categories above]
**Proposer:** [Your name / Function Lead]

**Summary:**
[1-2 sentence description]

**Details:**
[What the funds will be used for]

**Alignment:**
[How this serves network purpose]

**Milestones:** (for amounts > $2,000)
[Specific deliverables and timeline]

**Accountability:**
[How progress/completion will be verified]
```

## Disbursement

### Standard Disbursement

1. Consent confirmed and documented
2. Steward or Agent creates transaction in multi-sig
3. 2/4+ threshold collected
4. Transaction executed on-chain
5. Confirmation posted in treasury channel

### Milestone-Based Disbursement

For allocations > $2,000:
- Initial disbursement: up to 50%
- Subsequent disbursements: upon milestone completion
- Function Lead or proposer reports milestone completion
- Steward Council verifies and initiates next disbursement

### Agent Execution

[[Agent|Agents]] with signer access:
- Submit transactions to multi-sig
- Sign transactions (counted toward threshold)
- Execute transactions once threshold met

**Consent is the decision point.** Once a proposal has received sufficient consents and no unresolved objections, execution proceeds autonomously.

## Reporting

| Report | Frequency | Content |
|--------|-----------|---------|
| Transaction log | Real-time | Public blockchain visibility |
| Monthly summary | Monthly | All transactions, categories, balances |
| Event accounting | Post-Event | Full event budget vs actual |

### Monthly Summary Contents

- Total inflows and outflows
- Breakdown by category
- Current balance
- Pending allocations
- Notable transactions

## Emergency Operations

For time-sensitive situations:

| Action | Authority | Constraint |
|--------|-----------|------------|
| Emergency freeze | 2 Stewards | Documented rationale |
| Emergency transaction | 2 Stewards | Documented rationale + 48h ratification |

**Ratification:** All emergency actions require Member Assembly ratification within 48 hours. Non-ratified actions are reversed where possible.

## Safeguards

- **Multi-sig:** No single person can move funds unilaterally
- **Public visibility:** All transactions on public blockchain
- **Consent-first:** Allocation decisions through consent, not authority
- **Audit trail:** All allocations documented with purpose and authorization

## Related Protocols

- [[Member Assembly Protocol]] — Approval process
- [[Steward Council Protocol]] — Signing authority
- [[Event Cycle Protocol]] — Budget cycle timing
