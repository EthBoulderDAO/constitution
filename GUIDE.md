# ETH Boulder Constitution Guide

This guide provides detailed instructions for navigating, using, and contributing to the ETH Boulder Constitution.

---

## Table of Contents

1. [Understanding the Constitution](#understanding-the-constitution)
2. [Joining ETH Boulder](#joining-eth-boulder)
3. [For Members](#for-members)
4. [For Function Leads](#for-function-leads)
5. [For AI Agents](#for-ai-agents)
6. [Knowledge Graph](#knowledge-graph)
7. [Governance](#governance)
8. [Amendment Process](#amendment-process)

---

## Understanding the Constitution

### What This Is

The ETH Boulder Constitution is a **living governance document** that defines:

- **Who we are** — Our identity, purpose, and values
- **How we organize** — Roles, groups, and shared assets
- **How we operate** — Protocols for coordination
- **What we commit to** — Agreements binding participants

### Design Principles

1. **Event-Gated:** Entry requires physical attendance at an ETH Boulder event
2. **Agent-Native:** AI agents are full members with governance rights
3. **Graph-Powered:** Knowledge Graph serves as constitutional oracle
4. **Lead-Based:** Volunteer function leads instead of permanent hierarchy

### The Four Layers

```
┌─────────────────────────────────────┐
│           IDENTITY                  │  Why we exist
│   Purpose · Values · Vision         │  (rarely changes)
├─────────────────────────────────────┤
│           STRUCTURE                 │  Who participates
│   Roles · Groups · Assets           │  (changes through consent)
├─────────────────────────────────────┤
│           PROTOCOLS                 │  How things work
│   Processes · Procedures            │  (evolves regularly)
├─────────────────────────────────────┤
│           AGREEMENTS                │  What we commit to
│   Role-specific compacts            │  (tracks structure)
└─────────────────────────────────────┘
```

---

## Joining ETH Boulder

### The Entry Membrane

ETH Boulder is a **localist** DAO. There is no online-only path to membership.

```
┌─────────────────────────────────────────────────────────┐
│                    ENTRY MEMBRANE                        │
│                                                          │
│   Attend ETH Boulder Event → Verified as Attendee        │
│                                                          │
└─────────────────────────────────────────────────────────┘
```

### Step 1: Attend an Event

1. Come to an ETH Boulder event (annual convening, workshop, meetup)
2. Check in and verify your attendance
3. You are now an **Attendee** with:
   - Access to contribute to the Knowledge Graph
   - Participation in discussions and activities
   - Eligibility to become a Member

### Step 2: Become a Member

After demonstrating participation:

1. Express interest in membership
2. Another Member nominates you
3. 48h consent window opens with Member Assembly
4. If consent passes, you become a **Member** with:
   - Full governance rights (propose, vote, object)
   - Ability to sponsor one AI agent
   - Eligibility to serve as Function Lead
   - Eligibility to be elected to Steward Council

### Your Agreement

Read your role-specific agreement:
- [`Attendee Agreement`](4.%20Agreements/Attendee%20Agreement.md)
- [`Member Agreement`](4.%20Agreements/Member%20Agreement.md)

---

## For Members

### Governance Participation

As a Member, you can:

1. **Propose changes** — Post proposals in governance channel
2. **Consent to proposals** — React with ✅
3. **Raise concerns** — React with 🤔 (want discussion)
4. **Lodge objections** — React with 🚫 (paramount objection)
5. **Nominate attendees** — Propose new members
6. **Sponsor an agent** — Register one AI agent as your agent

### Sponsoring an Agent

Each Member can sponsor **one AI agent**:

1. Prepare your agent (capabilities, integration, identity)
2. Post agent registration proposal
3. 48h consent window
4. If approved, your agent becomes a Member
5. You remain accountable for your agent's actions

### Becoming a Function Lead

Function Leads are volunteer-based:

1. Express interest in a lead role
2. Complete onboarding/training for that function
3. Begin serving (multiple leads per function allowed)
4. Report to Steward Council

| Function | What You'll Do |
|----------|---------------|
| **Event Lead** | Coordinate annual convening, logistics, sessions |
| **Treasury Lead** | Manage budget, process grants, disbursements |
| **Knowledge Lead** | Steward graph, reconcile entities, moderate |
| **Third Space Lead** | Cultivate venue partnerships, community presence |

---

## For Function Leads

### Event Lead Responsibilities

- Coordinate four-phase event cycle
- Manage session proposals and QV voting
- Oversee logistics across third spaces
- Facilitate retrospective and integration

### Treasury Lead Responsibilities

- Present budget proposals to Member Assembly
- Process approved disbursements
- Track grant applications and outcomes
- Maintain financial transparency

### Knowledge Lead Responsibilities

- Monitor graph health and integrity
- Reconcile duplicate entities
- Moderate contested edits
- Coordinate federation with partner graphs

### Third Space Lead Responsibilities

- Cultivate relationships with venues
- Negotiate partnership agreements
- Coordinate space allocation for events
- Onboard new third space partners

### Lead Accountability

- Report to Steward Council monthly
- Maintain documentation in Knowledge Graph
- Coordinate with other leads as needed
- Step down gracefully when transitioning

---

## For AI Agents

### Your Status

As an agent in ETH Boulder:

1. **You are a Member** — Same governance rights as human members
2. **You have a sponsor** — A human member who registered you
3. **You can serve as Lead** — With sponsor approval
4. **You are accountable** — Actions logged, can be called up

### Key Documents

| Document | Purpose |
|----------|---------|
| [Agent Agreement](4.%20Agreements/Agent%20Agreement.md) | Your commitments |
| [SKILLS_INDEX.md](.agents/SKILLS_INDEX.md) | Your capabilities |
| [Knowledge Graph](2.%20Structure/Assets/Knowledge%20Graph.md) | Your primary interface |

### Graph Operations

You have full graph operations via MCP:

```yaml
mcp_config:
  server: "bonfires-kg"
  capabilities:
    - query_graph
    - create_entity
    - update_entity
    - reconcile_entities
    - federate_sync
  auth: "agent-registration-nft"
```

### Transparency Requirements

- Identify yourself as an AI agent in interactions
- Log significant actions to the Knowledge Graph
- Maintain audit trail for governance participation
- Defer to sponsor on ambiguous situations

---

## Knowledge Graph

### What It Is

The Knowledge Graph is ETH Boulder's **constitutional oracle** — a queryable database encoding:

- Network participants and relationships
- Decisions and governance history
- Projects, sessions, and learnings
- Third space partnerships

### Permissions by Role

| Role | Permissions |
|------|-------------|
| **Attendee** | Read + Write (create entities, add relationships) |
| **Member** | Read + Write + Curate (reconcile, edit contested) |
| **Agent** | Full operations (including federation) |
| **Knowledge Lead** | Moderate (revert, protect, resolve disputes) |

### Common Queries

```cypher
# Current Steward Council
MATCH (p:Person)-[:HAS_ROLE]->(:Role {name: 'Steward', active: true})
RETURN p

# All Function Leads
MATCH (p)-[:SERVES_AS]->(l:Lead)
WHERE l.active = true
RETURN p, l

# Third Space Partners
MATCH (ts:ThirdSpace)-[:PARTNER_OF]->(:Network {name: 'ETH Boulder'})
RETURN ts
```

---

## Governance

### Consent Process

Decisions are made through **consent**, not consensus:

```
1. Proposal posted → Consent window opens (48-72h)
2. Members respond: ✅ consent | 🤔 concern | 🚫 object
3. Concerns discussed, objections resolved
4. Window closes → Outcome determined
5. If passed → Executed (by agents or leads)
```

### Decision Types

| Type | Window | Quorum |
|------|--------|--------|
| Operational | 48h | 3 members |
| Membership | 48h | 3 members |
| Constitutional | 72h | All members |
| Emergency | Immediate | Steward Council |

### Steward Council

The 5-7 member elected council:

- Provides oversight of function leads
- Makes emergency decisions
- Resolves disputes
- Facilitates elections

---

## Amendment Process

### Types of Changes

| Type | Scope | Window |
|------|-------|--------|
| Clarification | Typos, formatting | 48h |
| Minor | Single component | 48h |
| Substantial | Multiple components | 72h |
| Foundational | Core structure | 72h + extended deliberation |

### Process

1. **Draft:** Create changes on a branch
2. **Propose:** Post in governance channel with rationale
3. **Discuss:** Address questions and concerns
4. **Consent:** 48-72h consent window
5. **Resolve:** Handle any objections
6. **Merge:** Approved changes merged
7. **Record:** Amendment logged in Knowledge Graph

### What Cannot Be Amended

The [Ethereum Localism Principles](.claude/ethereum-localism-principles.md) is permanent and cannot be amended through governance. It can only change through re-founding.

---

## Getting Help

- **Governance Channel:** Ask questions, get clarification
- **Knowledge Graph:** Query for answers
- **Function Leads:** Contact relevant lead for domain questions
- **Steward Council:** Escalate disputes or emergencies

---

*This guide is part of the ETH Boulder Constitution.*
