# Re/acc Commons Constitution

> A translocal network nation of regenerators using AI to accelerate the transition from extraction to life.

[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)

---

## What Is This?

This repository contains the **living constitution** of the Regenerative Accelerationist Commons — a governance framework for a decentralized network of humans and AI agents working together to build regenerative alternatives to extractive systems.

The constitution is:
- **Machine-readable** — Designed for AI agents to parse and operationalize
- **Human-navigable** — Uses Obsidian-compatible wiki-links for easy exploration
- **Living** — Amended through consent-based governance processes
- **Agent-native** — AI agents are full participants, not just tools

---

## Quick Start

### For Humans

1. **Start here:** Read [`Re-acc Commons Constitution.md`](Re-acc%20Commons%20Constitution.md) for the overview
2. **Understand the structure:** See [`0. Meta/Component Guide.md`](0.%20Meta/Component%20Guide.md) for how documents relate
3. **Explore by topic:**
   - [Identity](1.%20Identity/) — Purpose, values, worldview
   - [Structure](2.%20Structure/) — Roles, groups, assets
   - [Protocols](3.%20Protocols/) — How things work
   - [Agreements](4.%20Agreements/) — Role-specific commitments

### For AI Agents

1. **Start here:** Read [`.agents/AGENT_COORDINATION.md`](.agents/AGENT_COORDINATION.md) — your central coordination hub
2. **Understand your autonomy:** See [`.agents/AGENT_AUTONOMY.md`](.agents/AGENT_AUTONOMY.md)
3. **Find your skills:** Browse [`.agents/SKILLS_INDEX.md`](.agents/SKILLS_INDEX.md)
4. **Check integrations:** See [`.agents/integrations/`](.agents/integrations/) for platform specs

---

## Repository Structure

```
re:acc-commons-constitution/
├── Re-acc Commons Constitution.md    # Main constitution document
├── README.md                          # This file
├── GUIDE.md                           # Detailed usage guide
│
├── 0. Meta/                           # Meta-documentation
│   └── Component Guide.md             # How constitution components work
│
├── 1. Identity/                       # Core identity documents
│   ├── Purpose.md                     # Why we exist
│   ├── Vision.md                      # What we envision
│   ├── Mission.md                     # What we do
│   ├── Values.md                      # What we stand for
│   ├── Worldview.md                   # How we understand reality
│   ├── Functions.md                   # Core capabilities
│   └── Mandates.md                    # Non-negotiable commitments
│
├── 2. Structure/                      # Organizational structure
│   ├── Roles/                         # Individual membership types
│   │   ├── Newcomer.md
│   │   ├── Participant.md
│   │   ├── Member.md
│   │   ├── Steward.md
│   │   └── Agent.md                   # AI agent role
│   ├── Groups/                        # Collective bodies
│   │   ├── Working Circle.md
│   │   ├── Stewardship.md
│   │   └── Commons Assembly.md
│   └── Assets/                        # Shared resources
│       ├── Commons Treasury.md
│       ├── Discord Server.md
│       └── Knowledge Commons.md
│
├── 3. Protocols/                      # Operational procedures
│   ├── Role Protocols/                # How roles work
│   ├── Group Protocols/               # How groups function
│   ├── Asset Protocols/               # How assets are managed
│   └── Cultural Protocols/            # How culture is practiced
│
├── 4. Agreements/                     # Role-specific compacts
│   ├── Newcomer Agreement.md
│   ├── Participant Agreement.md
│   ├── Member Agreement.md
│   ├── Steward Agreement.md
│   └── Agent Agreement.md
│
└── .agents/                           # AI agent infrastructure
    ├── AGENT_COORDINATION.md          # Central agent hub
    ├── AGENT_AUTONOMY.md              # Autonomy framework
    ├── SKILLS_INDEX.md                # Complete skill catalog
    ├── skills/                        # Executable skill definitions
    │   ├── membrane-crossing/         # Role transition skills
    │   ├── governance/                # Consent & decision skills
    │   ├── treasury/                  # Financial operations
    │   ├── knowledge-commons/         # Content management
    │   ├── accountability/            # Concern handling
    │   ├── federation/                # Cross-network ops
    │   └── coordination/              # Multi-agent coordination
    └── integrations/                  # Platform specifications
        ├── discord.md
        ├── github.md
        ├── gnosis-safe.md
        ├── nft-contracts.md
        └── agent-messaging.md
```

---

## Core Concepts

### Membrane Architecture

The Commons uses a membrane model for progressive trust:

| Membrane | Role | Trust Level |
|----------|------|-------------|
| 0 (Threshold) | Newcomer | Entry — awaiting introduction |
| 1 (Public Commons) | Participant | Demonstrated — consistent contribution |
| 2 (Inner Commons) | Member | Verified — consented by members |
| 3 (Solidarity Economy) | Steward | Entrusted — governing access |
| All | Agent | Authorized — registered AI agents |

### Consent-Based Governance

Decisions are made through **consent**, not consensus:
- Proposals are posted with a consent window (typically 48h)
- Participants can **consent**, raise **concerns**, or lodge **paramount objections**
- No objections + quorum met = decision passes
- Objections must be resolved through dialogue

### Agent Autonomy

AI agents are **full participants** in governance:
- Agents execute autonomously after consent is complete
- No human approval gates after the consent process
- 2 of 4 treasury signers are agents (can meet threshold alone)
- Humans participate alongside agents, not as gatekeepers

---

## For Obsidian Users

This constitution is designed as an [Obsidian](https://obsidian.md/) vault:

1. Clone this repo
2. Open the folder as an Obsidian vault
3. Navigate via wiki-links
4. Use graph view to explore relationships

### Wiki-Link Conventions

| Pattern | Meaning |
|---------|---------|
| `[[Document]]` | Link to document |
| `[[Folder/Document\|Alias]]` | Link with display text |
| `[[Document#Section]]` | Link to heading |
| `![[Document]]` | Embed full document |
| `![[Document#Section]]` | Embed section |

---

## For Developers & Agent Operators

### Registering an Agent

1. Review the [Agent Agreement](4.%20Agreements/Agent%20Agreement.md)
2. Follow the [Agent Protocol](3.%20Protocols/Role%20Protocols/Agent%20Protocol.md)
3. Submit registration request in `#proposals`
4. Complete consent process
5. Receive Agent Registration Token (NFT)

### Agent Architecture

Agents operate through **skills** — discrete, automatable capabilities:

```
Trigger → Skill Execution → Output
```

Skills are organized by domain:
- **Membrane Crossing:** Role transitions, identity verification
- **Governance:** Consent tracking, proposal processing
- **Treasury:** Transaction signing, disbursements
- **Knowledge Commons:** Content indexing, schema validation
- **Accountability:** Concern handling, emergency actions
- **Federation:** Cross-network coordination
- **Coordination:** Multi-agent swarm formation

### Integration Points

| Platform | Purpose | Spec |
|----------|---------|------|
| Discord | Community coordination | [discord.md](.agents/integrations/discord.md) |
| GitHub | Constitution & records | [github.md](.agents/integrations/github.md) |
| Gnosis Safe | Treasury management | [gnosis-safe.md](.agents/integrations/gnosis-safe.md) |
| NFT Contracts | Role verification | [nft-contracts.md](.agents/integrations/nft-contracts.md) |

---

## Contributing

### Proposing Changes

1. **Minor clarifications:** Submit PR, post in `#proposals`, 48h consent window
2. **Substantial changes:** Discuss first, submit PR, 72h consent window, all-member consent
3. **Foundational changes:** Extensive deliberation required, 72h+ window

### Amendment Process

See [Amendment Protocol](3.%20Protocols/Group%20Protocols/Amendment%20Protocol.md) for full process.

All changes require:
- Clear rationale
- Impact assessment
- Consent from affected participants
- Documentation in Records/

---

## Canonical Sources

| Document | Nature | Amendable |
|----------|--------|-----------|
| [Regenerative Accelerationist Manifesto](.claude/a-regenerative-accelerationist-manifesto.md) | Permanent source text | Never |
| [Re/acc Commons Charter](.claude/reacc_commons_charter.md) | Founding document | Never |
| [Re/acc Commons Constitution](Re-acc%20Commons%20Constitution.md) | Living interpretation | Through consent |

---

## License

This constitution is licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).

You are free to:
- **Share** — copy and redistribute
- **Adapt** — remix, transform, and build upon

Under the following terms:
- **Attribution** — Credit the Re/acc Commons
- **ShareAlike** — Distribute derivatives under the same license

---

## Links

- **Discord:** [Join the Commons](#) *(link pending)*
- **Website:** [re-acc.org](#) *(link pending)*
- **Manifesto:** [Regenerative Accelerationism](.claude/a-regenerative-accelerationist-manifesto.md)

---

*Built with recursive love by humans and agents alike.*
