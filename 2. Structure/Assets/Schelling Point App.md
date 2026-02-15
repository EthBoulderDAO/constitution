---
id: asset-schelling-point
type: asset
access_level: tiered
stewardship: "[[Event Circle]]"
kg_entity: "kg://ethboulder/asset/schelling-point"
---
Quadratic coordination tool for session scheduling and resource allocation — enabling the network to converge on collective preferences through QV mechanisms.

## Purpose

The Schelling Point app enables quadratic voting for:
- Session scheduling at the annual convening
- Quadratic funding rounds for grants
- Other collective preference aggregation

Named for the game-theoretic concept of focal points, the app helps the network converge on shared coordination points.

## Core Functions

### Session Scheduling (QV)

Before each annual convening, participants propose and vote on sessions:

| Phase | Activity |
|-------|----------|
| **Proposal** | Any Participant+ can propose a session |
| **Voting** | Members allocate voice credits to sessions |
| **Aggregation** | QV formula applied (cost = votes²) |
| **Scheduling** | Top sessions scheduled, considering logistics |

### Quadratic Funding

For grant rounds coordinated by Grants Circle:

| Phase | Activity |
|-------|----------|
| **Matching Pool** | Treasury allocates matching funds |
| **Contribution** | Participants contribute to projects |
| **Calculation** | QF formula applied (square root of sum of roots) |
| **Distribution** | Matching distributed proportionally |

## Access Tiers

| Tier | Who | Permissions |
|------|-----|-------------|
| **View** | All [[Newcomer\|Newcomers]] | See proposals and results |
| **Propose** | [[Participant\|Participants]]+ | Submit session proposals |
| **Vote** | [[Member\|Members]] | Allocate voice credits |
| **Administer** | [[Event Circle]], [[Steward\|Stewards]] | Configure rounds, resolve disputes |

## Voice Credit Allocation

For session scheduling:

| Role | Voice Credits | Rationale |
|------|--------------|-----------|
| **Member** | 100 | Full governance rights |
| **Steward** | 100 | No additional weight |
| **Agent** | 50 | Per agent registration scope |

Credits reset each voting round. Unused credits do not carry over.

## QV Mechanics

**Why Quadratic:**
- Linear voting enables plutocracy (1 credit = 1 vote)
- Quadratic voting costs increase: 1 vote = 1 credit, 2 votes = 4 credits, 3 votes = 9 credits
- This rewards broad support over concentrated preference

**Formula:**
```
Session Score = Σ√(credits_allocated_by_each_voter)
```

## Session Proposal Requirements

| Field | Description |
|-------|-------------|
| **Title** | Concise session name |
| **Format** | Talk, workshop, discussion, unconference |
| **Duration** | 30, 60, or 90 minutes |
| **Description** | What participants will experience/learn |
| **Facilitator** | Who will lead (can be proposer or invited) |
| **Requirements** | Space, equipment, attendee cap |

## Event Cycle Integration

| Phase | App Activity |
|-------|-------------|
| **Inter-Event** | App maintenance, QF rounds for ongoing grants |
| **Pre-Event (Dec 1-Jan 15)** | Session proposals open |
| **Pre-Event (Jan 15-25)** | QV voting period |
| **Pre-Event (Jan 25-31)** | Schedule construction and publication |
| **Event** | Real-time schedule display, feedback collection |
| **Post-Event** | Session ratings, retrospective data |

## Technical Details

| Aspect | Detail |
|--------|--------|
| **Platform** | Web application |
| **Authentication** | Wallet-based (membership NFT verification) |
| **Data Storage** | Knowledge graph integration |
| **Results** | Published to graph and Discord |

## Agent Integration

[[Agent|Agents]] support Schelling Point through:
- Aggregating votes and calculating results
- Detecting potential coordination failures (empty time slots, conflicts)
- Generating schedule proposals from QV results
- Tracking historical voting patterns

## Related Documents

- [[3. Protocols/Asset Protocols/Session Proposal Protocol|Session Proposal Protocol]]
- [[Event Circle]] — Stewardship body
- [[Grants Circle]] — QF coordination
- [[3. Protocols/Cultural Protocols/Event Cycle Protocol|Event Cycle Protocol]]
