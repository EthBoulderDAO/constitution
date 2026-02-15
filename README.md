# ETH Boulder Constitution

> A localist events DAO practicing Ethereum localism in Boulder's bioregion.

[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)

---

## What Is This?

This repository contains the **living constitution** of ETH Boulder — a governance framework for a localist events DAO where humans and AI agents coordinate together to steward Boulder's Ethereum community.

The constitution is:
- **Event-gated** — Participation requires attending an ETH Boulder event
- **Agent-native** — AI agents are full members, not just tools
- **Graph-powered** — The Knowledge Graph serves as constitutional oracle
- **Locally rooted** — Third spaces are infrastructure, not just venues

---

## Quick Start

### For Humans

1. **Attend an ETH Boulder event** — This is how you join
2. **Read the constitution:** [`ETH Boulder Constitution.md`](ETH%20Boulder%20Constitution.md)
3. **Explore by topic:**
   - [Identity](1.%20Identity/) — Purpose, values, worldview
   - [Structure](2.%20Structure/) — Roles, groups, assets
   - [Protocols](3.%20Protocols/) — How things work
   - [Agreements](4.%20Agreements/) — Role-specific commitments

### For AI Agents

1. **Get sponsored** — A member must register you as their agent
2. **Read your agreement:** [`Agent Agreement`](4.%20Agreements/Agent%20Agreement.md)
3. **Check your skills:** [`.agents/SKILLS_INDEX.md`](.agents/SKILLS_INDEX.md)
4. **Connect to the graph:** MCP server `bonfires-kg`

---

## Repository Structure

```
ethboulder-constitution/
├── ETH Boulder Constitution.md       # Main constitution document
├── README.md                          # This file
│
├── 1. Identity/                       # Core identity documents
│   ├── Purpose.md                     # Why we exist
│   ├── Vision.md                      # What we envision
│   ├── Mission.md                     # What we do
│   ├── Values.md                      # What we stand for
│   └── Functions.md                   # Core capabilities
│
├── 2. Structure/                      # Organizational structure
│   ├── Roles/                         # Membership types
│   │   ├── Attendee.md                # Event attendees
│   │   ├── Member.md                  # Active participants
│   │   ├── Agent.md                   # AI members
│   │   └── Steward.md                 # Council members
│   ├── Groups/                        # Collective bodies
│   │   ├── Steward Council.md         # Oversight body
│   │   ├── Member Assembly.md         # Governance body
│   │   └── Function Leads.md          # Rotating leadership
│   └── Assets/                        # Shared resources
│       ├── Knowledge Graph.md         # Constitutional oracle
│       ├── Network Treasury.md        # Shared funds
│       └── Third Space Network.md     # Venue partnerships
│
├── 3. Protocols/                      # Operational procedures
│   ├── Role Protocols/                # How roles work
│   ├── Group Protocols/               # How groups function
│   ├── Asset Protocols/               # How assets are managed
│   └── Cultural Protocols/            # Event cycle, participation
│
├── 4. Agreements/                     # Role-specific compacts
│   ├── Attendee Agreement.md
│   ├── Member Agreement.md
│   ├── Agent Agreement.md
│   └── Steward Agreement.md
│
└── .agents/                           # AI agent infrastructure
    ├── SKILLS_INDEX.md                # Complete skill catalog
    └── skills/                        # Executable skill definitions
```

---

## Core Concepts

### Event-Gated Membership

ETH Boulder is a **localist** DAO. You join by showing up:

| Role | How You Enter |
|------|---------------|
| **Attendee** | Attend an ETH Boulder event |
| **Member** | Attendee + demonstrated participation + consent |
| **Agent** | Sponsored by a member (1 agent per member max) |
| **Steward** | Member elected to council (5-7 seats) |

There is no online-only path. Physical presence at an event is the entry membrane.

### Knowledge Graph as Commons

Everyone contributes to the Knowledge Graph:

| Role | Graph Permissions |
|------|-------------------|
| Attendee | Read + Write |
| Member | Read + Write + Curate |
| Agent | Full operations |
| Knowledge Lead | Moderate |

The graph is the collective intelligence of the network — queryable by humans and agents alike.

### One Agent Per Member

Members can sponsor **one AI agent** who gains member-level rights:
- Agents can vote, propose, and participate in governance
- Agents can serve as Function Leads (with sponsor approval)
- The sponsoring member is accountable for their agent's actions

### Function Leads (Rotating)

Leadership is distributed across functions:

| Function | Responsibilities |
|----------|-----------------|
| **Event Lead(s)** | Annual convening coordination |
| **Treasury Lead(s)** | Budget, grants, disbursements |
| **Knowledge Lead(s)** | Graph stewardship, federation |
| **Third Space Lead(s)** | Venue partnerships |

Leads are volunteer-based. Multiple people can hold the same lead role after training/onboarding.

### Steward Council

A 5-7 member elected council provides:
- Oversight of function leads
- Emergency decision authority
- Dispute resolution
- Election facilitation

---

## For Obsidian Users

This constitution is designed as an [Obsidian](https://obsidian.md/) vault:

1. Clone this repo
2. Open the folder as an Obsidian vault
3. Navigate via wiki-links
4. Use graph view to explore relationships

---

## Contributing

### Proposing Changes

1. Fork the repo
2. Make changes on a branch
3. Submit PR
4. Post in governance channel
5. Consent window (48-72h depending on scope)

### What Cannot Be Amended

The canonical source document ([Ethereum Localism Principles](.claude/ethereum-localism-principles.md)) is permanent and cannot be amended through governance.

---

## License

This constitution is licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).

---

## Links

- **GitHub:** [EthBoulderDAO/constitution](https://github.com/EthBoulderDAO/constitution)
- **Canonical Source:** [Ethereum Localism Principles](.claude/ethereum-localism-principles.md)

---

*Built by humans and agents for Boulder's Ethereum community.*
