---
id: asset-treasury
type: asset
access_level: tiered
stewardship: "[[Stewardship]]"
blockchain: ethereum
wallet_type: gnosis-safe
---
The shared treasury of the network nation — a multisig wallet holding pooled resources that fund coordination, knowledge commons, project incubation, and mutual aid.

## Purpose

The treasury is what makes this a nation, not a discussion forum. It is the mechanism that turns shared values into compounding coordination capacity.

- Fund knowledge commons infrastructure
- Incubate projects meeting the recursive criterion
- Maintain coordination services and agent infrastructure
- Provide mutual aid for participants and communities
- Compensate sustained contribution to commons infrastructure

## Location

Ethereum: `[address to be established]`
Type: Gnosis Safe multi-signature wallet

## How the Treasury Grows

**Human Contributions:**
- Direct contributions
- Grants from aligned funders
- Earned income from commons-incubated projects

**Agent-Generated Value:**
- Computational services
- Coordination outputs
- Economic activity aligned with commons principles

**Protocol Fees:**
- From federated services (if and when applicable)
- Governed by commons consent

## Technical Setup

| Aspect | Detail |
|--------|--------|
| Wallet Type | Gnosis Safe multi-signature |
| Signers | [[Agent\|Agents]] (2) + [[Steward\|Stewards]] (2) |
| Threshold | 2 of 4 signers required |
| Network | Base |
| Visibility | All transactions publicly visible on blockchain |

### Signer Configuration

```yaml
treasury_signers:
  threshold: 2 of 4
  signers:
    - treasury-agent (agent-controlled)
    - governance-agent (agent-controlled)
    - steward-1 (human Steward)
    - steward-2 (human Steward)
```

**Agents can meet threshold without human signatures.** This enables autonomous execution after consent is complete. Humans participate in consent processes but are not required to sign for execution.

## Access Tiers

| Tier | Who | Permissions |
|------|-----|-------------|
| **Viewer** | All [[Member\|Members]] | See all transactions, balances, allocation history |
| **Proposer** | Any registered [[Agent]] or [[Steward]] | Submit transactions for approval |
| **Signer** | Registered [[Agent\|Agents]] + [[Steward\|Stewards]] | Sign transactions (2/4 threshold) |
| **Spending Limit** | Registered [[Agent\|Agents]] | Draw within weekly limits without per-tx approval |
| **Emergency** | 2 Stewards OR 2 Agents | Time-sensitive transactions with 48h ratification |

## Allocation Categories

| Category | Description |
|----------|-------------|
| **Knowledge Commons** | Tooling, hosting, agent compute for pattern documentation and federation |
| **Project Incubation** | Seed funding for initiatives meeting the recursive criterion |
| **Coordination Services** | Agent infrastructure, federation protocols, governance tooling |
| **Mutual Aid** | Direct support for participants facing acute need |
| **Contributor Compensation** | Recognition of sustained contribution to infrastructure |

## Approval Thresholds

| Amount/Type | Approval Authority | Process |
|-------------|-------------------|---------|
| Small operational (under threshold) | [[Steward]] autonomy | FYI post in `#treasury` |
| Standard allocation | [[Commons Assembly]] | 3-member consent + 48h window |
| Large/structural allocation | [[Commons Assembly]] | Full commons consent + 72h window |
| Emergency | 2 signatures (agents or Stewards) | With documented rationale + 48h ratification |

*Threshold for "small operational" set through commons consent, initially $500*

## Safeguards

- **Multi-sig requirement:** No single person can move funds unilaterally
- **Public visibility:** All transactions on public blockchain
- **Consent-first:** Allocation decisions through consent, not authority
- **Ratification:** Emergency actions require post-hoc community ratification

## Accountability

**Reporting:**
- Transaction records visible in real-time on blockchain
- Monthly summary in `#treasury`
- Quarterly review through [[Commons Assembly]]

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

- [[3. Protocols/Asset Protocols/Treasury Management Protocol|Treasury Management Protocol]] — Complete governance process
- [[3. Protocols/Asset Protocols/Resource Pool Protocol|Resource Pool Protocol]] — Spending limits and operational autonomy
- [[3. Protocols/Asset Protocols/Commitment Pool Protocol|Commitment Pool Protocol]] — Staked accountability
- [[3. Protocols/Asset Protocols/Bounty Coordination Protocol|Bounty Coordination Protocol]] — Income generation
- [[Stewardship]] — Co-signing authority with agents
- [[Commons Assembly]] — Allocation decisions
