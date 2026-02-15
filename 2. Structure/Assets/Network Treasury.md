---
id: asset-treasury
type: asset
access_level: tiered
stewardship: "[[Steward Council]]"
blockchain: ethereum
wallet_type: gnosis-safe
kg_entity: "kg://ethboulder/asset/treasury"
---
The shared treasury of ETH Boulder — a multisig wallet holding pooled resources that fund the knowledge graph, annual event, third space partnerships, grants, and coordination infrastructure.

## Purpose

The treasury is what makes this a network nation, not a discussion forum. It is the mechanism that turns shared values into compounding coordination capacity.

- Fund knowledge graph infrastructure and federation
- Coordinate the annual ETH Boulder convening
- Support third space partnerships and federation grants
- Fund local public goods through grants program
- Maintain coordination services and agent infrastructure
- Provide mutual aid for participants and communities

## Location

Ethereum: `[address to be established]`
Type: Gnosis Safe multi-signature wallet

## How the Treasury Grows

**Human Contributions:**
- Direct contributions
- Grants from aligned funders
- Earned income from network-incubated projects

**Agent-Generated Value:**
- Computational services
- Coordination outputs
- Economic activity aligned with network principles

**Protocol Fees:**
- From federated services (if and when applicable)
- Governed by network consent

## Technical Setup

| Aspect | Detail |
|--------|--------|
| Wallet Type | Gnosis Safe multi-signature |
| Signers | [[Steward Council]] members + registered [[Agent\|Agents]] |
| Threshold | 2 of 4+ signers required |
| Network | Base |
| Visibility | All transactions publicly visible on blockchain |

### Signer Configuration

```yaml
treasury_signers:
  threshold: 2 of 4+
  signers:
    - steward-1 (Steward Council member)
    - steward-2 (Steward Council member)
    - steward-3 (Steward Council member)
    - registered-agent (agent-controlled)
```

**Agents can meet threshold without human signatures.** This enables autonomous execution after consent is complete. Humans participate in consent processes but are not required to sign for execution.

## Access Tiers

| Tier | Who | Permissions |
|------|-----|-------------|
| **Viewer** | All [[Member\|Members]] | See all transactions, balances, allocation history |
| **Proposer** | Any [[Member]], [[Agent]], or [[Function Leads\|Function Lead]] | Submit transactions for approval |
| **Signer** | [[Steward Council]] + registered [[Agent\|Agents]] | Sign transactions (2/4+ threshold) |
| **Spending Limit** | Treasury Lead | Draw within weekly limits without per-tx approval |
| **Emergency** | 2 Stewards | Time-sensitive transactions with 48h ratification |

## Allocation Categories

| Category | Description |
|----------|-------------|
| **Event Operations** | Venue, speakers, hackathon prizes, logistics |
| **Knowledge Graph** | Bonfires hosting, agent compute, federation infrastructure |
| **Third Space Partnerships** | Federation grants, venue support |
| **Grants** | QF rounds, hackathon prizes, ecosystem funding |
| **Coordination Services** | Agent infrastructure, governance tooling |
| **Mutual Aid** | Direct support for participants facing acute need |

## Event Cycle Budgeting

| Phase | Budget Focus |
|-------|-------------|
| **Inter-Event (Mar-Nov)** | Ongoing operations, knowledge graph, grants |
| **Pre-Event (Dec-Jan)** | Event deposits, speaker travel, marketing |
| **Event (Feb)** | Real-time event expenses, prizes |
| **Post-Event (Mar)** | Vendor payments, retrospective costs |

Annual budget approved by Member Assembly before Pre-Event phase begins.

## Approval Thresholds

| Amount/Type | Approval Authority | Process |
|-------------|-------------------|---------|
| Small operational (≤ $500) | Treasury Lead | FYI post in treasury channel |
| Standard allocation ($500-$5,000) | [[Member Assembly]] | 3-member consent + 48h window |
| Large/structural allocation (> $5,000) | [[Member Assembly]] | All members + 72h window |
| Emergency | 2 Stewards | With documented rationale + 48h ratification |

## Safeguards

- **Multi-sig requirement:** No single person can move funds unilaterally
- **Public visibility:** All transactions on public blockchain
- **Consent-first:** Allocation decisions through consent, not authority
- **Ratification:** Emergency actions require post-hoc community ratification

## Accountability

**Reporting:**
- Transaction records visible in real-time on blockchain
- Monthly summary in treasury channel
- Quarterly review through [[Member Assembly]]

**Standards:**
- All allocations documented with purpose and authorization
- Milestone-based disbursement for larger projects
- Clear audit trail for all transactions

## Agent Economics

The treasury embodies human-AI symbiosis:
- Agent-generated value funds human regenerative work
- Human ecological wisdom guides agent activity
- Not extraction in either direction — symbiosis

## Related Documents

- [[Treasury Management Protocol]] — Complete governance process
- [[Function Leads]] — Treasury Lead responsibilities
- [[Steward Council]] — Co-signing authority with agents
- [[Member Assembly]] — Allocation decisions
