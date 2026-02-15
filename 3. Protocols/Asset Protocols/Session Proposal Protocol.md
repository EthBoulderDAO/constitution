---
id: protocol-session-proposal
type: protocol
protocol_type: asset
governs: "[[Schelling Point App]]"
triggers: pre-event-phase
kg_entity: "kg://ethboulder/protocol/session-proposal"
---
This protocol governs the proposal, voting, and scheduling of sessions for the annual ETH Boulder convening via the [[Schelling Point App]].

## Contents

- [[#Timeline]]
- [[#Proposal Process]]
- [[#Voting Process]]
- [[#Schedule Construction]]
- [[#Session Types]]
- [[#Related Protocols]]

## Timeline

Session scheduling follows the event cycle:

| Phase | Dates | Activity |
|-------|-------|----------|
| **Proposal Window** | Dec 1 - Jan 15 | Submit session proposals |
| **Voting Window** | Jan 15 - Jan 25 | QV voting on proposals |
| **Schedule Construction** | Jan 25 - Jan 31 | Results aggregated, schedule built |
| **Publication** | Feb 1 | Final schedule published |
| **Event** | Feb (3 days) | Sessions delivered |

## Proposal Process

### Who Can Propose

- [[Attendee|Attendees]] and above can propose sessions
- Proposals must identify a facilitator (can be proposer or invited)
- Multiple proposals per person allowed

### Proposal Requirements

| Field | Description | Required |
|-------|-------------|----------|
| **Title** | Concise session name (< 80 chars) | Yes |
| **Format** | Talk, workshop, discussion, unconference | Yes |
| **Duration** | 30, 60, or 90 minutes | Yes |
| **Description** | What participants will experience/learn (200-500 words) | Yes |
| **Facilitator** | Who will lead the session | Yes |
| **Requirements** | Space needs, equipment, attendee cap | Yes |
| **Tags** | Topic tags for discoverability | Recommended |
| **Target Audience** | Who should attend | Recommended |

### Submission Process

| Step | Action | Actor | Platform |
|------|--------|-------|----------|
| 1 | Draft proposal | Proposer | Any |
| 2 | Submit via Schelling Point | Proposer | App |
| 3 | Entity created in knowledge graph | Agent | Automated |
| 4 | Basic validation | Agent | Automated |
| 5 | Published to voting pool | System | After validation |

### Proposal Validation

Agents validate:
- All required fields present
- Facilitator confirmed (or proposer self-facilitating)
- Duration within allowed values
- No duplicate submissions (same title + facilitator)

Proposals failing validation returned for revision.

## Voting Process

### Voice Credit Allocation

| Role | Voice Credits | Notes |
|------|--------------|-------|
| Member | 100 | Full voting rights |
| Steward | 100 | No additional weight |
| Agent | 50 | Per agent registration |

Credits reset each voting cycle.

### QV Mechanics

Quadratic voting costs:
- 1 vote = 1 credit
- 2 votes = 4 credits
- 3 votes = 9 credits
- n votes = n² credits

This rewards broad support over concentrated preference.

### Voting Process

| Step | Action | Actor |
|------|--------|-------|
| 1 | Authenticate via wallet | Voter |
| 2 | Browse proposals | Voter |
| 3 | Allocate credits across proposals | Voter |
| 4 | Submit vote allocation | Voter |
| 5 | Vote recorded | System |

### Vote Modification

During voting window:
- Votes can be modified any time
- Latest allocation overwrites previous
- View current allocation at any time

## Schedule Construction

### Aggregation

After voting closes:
| Step | Action | Actor |
|------|--------|-------|
| 1 | Calculate QV scores | Agent |
| 2 | Rank proposals by score | Agent |
| 3 | Generate initial schedule | Agent |
| 4 | Apply logistical constraints | Event Lead |
| 5 | Resolve conflicts | Event Lead |
| 6 | Finalize schedule | Event Lead |

### QV Score Calculation

```
Session Score = Σ √(credits_allocated_by_each_voter)
```

### Logistical Constraints

Event Lead applies constraints:
- Venue capacity limits
- Equipment availability
- Facilitator conflicts (can't lead overlapping sessions)
- Session type distribution
- Time slot availability

### Conflict Resolution

When constraints prevent scheduling:
1. Higher-scored session gets preference
2. If tied, Event Lead discretion
3. Lower-scored sessions offered alternate slots
4. Sessions that can't be scheduled notified

## Session Types

### Format Options

| Format | Duration | Description |
|--------|----------|-------------|
| **Talk** | 30-60 min | Presentation with Q&A |
| **Workshop** | 60-90 min | Hands-on, interactive |
| **Discussion** | 30-60 min | Facilitated conversation |
| **Unconference** | Variable | Participant-driven, emergent |

### Unconference Sessions

Some slots reserved for unconference-style sessions:
- Proposed on-site during event
- Quick vote or sign-up
- First-come scheduling
- Not subject to pre-event QV

## Knowledge Graph Integration

Sessions are represented in the graph:

```cypher
(:Session {
  id: "kg://ethboulder/session/[id]",
  title: "Session Title",
  format: "workshop",
  duration: 60,
  qv_score: 42.5,
  status: "scheduled",
  time_slot: "2026-02-15T10:00:00",
  venue: "kg://ethboulder/thirdspace/regenhub"
})

(:Session)-[:FACILITATED_BY]->(:Person)
(:Session)-[:HELD_AT]->(:ThirdSpace)
(:Session)-[:PROPOSED_BY]->(:Person)
```

## Related Protocols

- [[3. Protocols/Cultural Protocols/Event Cycle Protocol|Event Cycle Protocol]] — Overall event timeline
- [[Function Lead Protocol]] — Event Lead coordination
- [[Schelling Point App]] — Voting platform
