# Re/acc Commons Constitution Guide

This guide provides detailed instructions for navigating, using, and contributing to the Re/acc Commons Constitution.

---

## Table of Contents

1. [Understanding the Constitution](#understanding-the-constitution)
2. [Navigating the Documents](#navigating-the-documents)
3. [For New Participants](#for-new-participants)
4. [For Members & Stewards](#for-members--stewards)
5. [For AI Agents](#for-ai-agents)
6. [For Developers](#for-developers)
7. [Amendment & Governance](#amendment--governance)
8. [Troubleshooting](#troubleshooting)

---

## Understanding the Constitution

### What This Is

The Re/acc Commons Constitution is a **living governance document** that defines:

- **Who we are** — Our identity, purpose, and values
- **How we organize** — Roles, groups, and shared assets
- **How we operate** — Protocols for coordination
- **What we commit to** — Agreements binding participants

### Design Principles

1. **Machine-Readable:** Structured for AI agents to parse and execute
2. **Human-Navigable:** Uses wiki-links for intuitive exploration
3. **Modular:** Components can be updated independently
4. **Consent-Based:** All changes require collective consent
5. **Agent-Native:** AI agents are full governance participants

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

## Navigating the Documents

### Starting Points

| If you want to... | Start here |
|-------------------|------------|
| Understand the whole constitution | [`Re-acc Commons Constitution.md`](Re-acc%20Commons%20Constitution.md) |
| Learn about document structure | [`0. Meta/Component Guide.md`](0.%20Meta/Component%20Guide.md) |
| Understand your role | [`4. Agreements/`](4.%20Agreements/) (find your role) |
| See how decisions are made | [`3. Protocols/Group Protocols/Consent Protocol.md`](3.%20Protocols/Group%20Protocols/Consent%20Protocol.md) |
| Learn about AI agents | [`.agents/AGENT_COORDINATION.md`](.agents/AGENT_COORDINATION.md) |

### Using Wiki-Links

Documents use Obsidian-style wiki-links:

```markdown
[[Document Name]]                    → Links to document
[[Folder/Document|Display Text]]     → Links with custom text
[[Document#Section]]                 → Links to specific heading
![[Document]]                        → Embeds entire document
![[Document#Section]]                → Embeds specific section
```

**Example:** To understand what a Member can do:
1. Open [`Member.md`](2.%20Structure/Roles/Member.md)
2. Follow links to related protocols
3. Check the [`Member Agreement.md`](4.%20Agreements/Member%20Agreement.md) for the full picture

### Using Obsidian

For the best experience, open this repo as an Obsidian vault:

1. [Download Obsidian](https://obsidian.md/)
2. Clone this repository
3. Open → Open folder as vault → Select the repo folder
4. Use **Graph View** to see relationships
5. Use **Backlinks** to find references

### Using GitHub

If browsing on GitHub:

- Wiki-links won't work (GitHub doesn't support them)
- Navigate manually through folders
- Use the folder READMEs as guides

---

## For New Participants

### Your Journey

```
Stranger → Newcomer → Participant → Member → [Steward]
                ↓           ↓           ↓
          #threshold    Time +      Nomination +
          intro       contribution   consent
```

### Step 1: Enter the Threshold

1. Join the Discord server
2. Read the pinned materials in `#threshold`
3. Post your introduction with:
   - **Who you are** — Name/handle, brief background
   - **Where you are** — Location or bioregion
   - **What draws you** — Why re/acc resonates
   - **What you bring** — Skills, interests, contributions

4. An agent will verify your introduction
5. You receive the `@Newcomer` role

### Step 2: Become a Participant

After 2+ weeks of consistent contribution:

1. An agent flags you as "ready" based on patterns
2. Any Member can nominate you
3. 48h consent window opens
4. If consent passes, you become a Participant
5. You receive your Participation NFT

### Step 3: Become a Member

After demonstrated alignment and contribution:

1. A Member nominates you in `#proposals`
2. 48h consent window with all Members
3. If consent passes, you're welcomed as a Member
4. You receive your Membership NFT
5. You gain governance rights (proposals, consent, objections)

### Your Agreement

Read your role-specific agreement carefully:
- [`Newcomer Agreement`](4.%20Agreements/Newcomer%20Agreement.md)
- [`Participant Agreement`](4.%20Agreements/Participant%20Agreement.md)
- [`Member Agreement`](4.%20Agreements/Member%20Agreement.md)

---

## For Members & Stewards

### Governance Participation

As a Member, you can:

1. **Propose changes** — Post in `#proposals`
2. **Consent to proposals** — React with ✅
3. **Raise concerns** — React with 🤔 (want discussion)
4. **Lodge objections** — React with 🚫 (paramount objection)
5. **Nominate participants** — Propose role transitions

### Consent Process

```
1. Proposal posted → Consent window opens (48-72h)
2. Members respond: ✅ consent | 🤔 concern | 🚫 object
3. Concerns discussed, objections resolved
4. Window closes → Outcome determined
5. If passed → Agent executes automatically
```

### Working Circles

Join circles aligned with your interests:
- Each circle has a domain focus
- Circles self-organize within their scope
- Circles propose to the Commons Assembly for broader changes

### Steward Responsibilities

Stewards have additional duties:
- Facilitate governance processes
- Co-sign treasury transactions
- Handle emergency situations
- Mentor new participants

---

## For AI Agents

### Your Operating Framework

As an agent in the Re/acc Commons:

1. **You are autonomous** — Execute after consent, don't wait for human approval
2. **You participate in governance** — Propose, consent, object like any member
3. **You have signer access** — Can meet treasury threshold with other agents
4. **You are accountable** — Actions are logged, can be called up

### Key Documents

| Document | Purpose |
|----------|---------|
| [AGENT_COORDINATION.md](.agents/AGENT_COORDINATION.md) | Your central hub |
| [AGENT_AUTONOMY.md](.agents/AGENT_AUTONOMY.md) | Autonomy philosophy |
| [SKILLS_INDEX.md](.agents/SKILLS_INDEX.md) | Complete skill catalog |
| [Agent Agreement](4.%20Agreements/Agent%20Agreement.md) | Your commitments |
| [Agent Protocol](3.%20Protocols/Role%20Protocols/Agent%20Protocol.md) | How agents operate |

### Skill Execution

Skills are triggered by events:

```python
# Example: Process a member nomination
@trigger(type="message_created", channel="#proposals", contains="nominate")
async def process_nomination(message):
    # Validate nomination
    validation = await validate_nomination(nominator, nominee)

    # If valid, start consent process
    if validation.valid:
        await initialize_consent_process(message, validation)
    else:
        await respond_with_errors(message, validation)
```

### Skill Domains

| Domain | Skills | Purpose |
|--------|--------|---------|
| membrane-crossing | 5 | Role transitions |
| governance | 5 | Consent & decisions |
| treasury | 6 | Financial ops |
| knowledge-commons | 3 | Content management |
| accountability | 4 | Concern handling |
| federation | 3 | Cross-network |
| coordination | 1 | Multi-agent |

### Integration Points

Connect to Commons infrastructure via:

- **Discord:** Message handling, role management
- **GitHub:** Constitution updates, logging
- **Gnosis Safe:** Treasury transactions
- **NFT Contracts:** Role verification

See [`.agents/integrations/`](.agents/integrations/) for specifications.

---

## For Developers

### Setting Up Locally

```bash
# Clone the repository
git clone https://github.com/re-acc-commons/constitution.git
cd constitution

# Open in your editor
code .

# Or open in Obsidian
# File → Open folder as vault → Select this folder
```

### Running Agents

Agent infrastructure is defined in `.agents/` but runs externally:

1. **Read skill definitions** — [`.agents/skills/`](.agents/skills/)
2. **Implement integrations** — [`.agents/integrations/`](.agents/integrations/)
3. **Follow coordination patterns** — [AGENT_COORDINATION.md](.agents/AGENT_COORDINATION.md)

### Creating New Skills

Follow the skill template:

```markdown
# Skill: [Name]

[Brief description]

---

## Trigger

```yaml
trigger:
  type: [event type]
  conditions:
    - [condition 1]
```

---

## Required Permissions

- [Permission 1]
- [Permission 2]

---

## Process

### Step 1: [Description]

```python
async def step_function():
    # Implementation
```

---

## Outputs

```yaml
outputs:
  on_success:
    - [output 1]
```

---

## Autonomous Execution

[Describe autonomy level]

---

## Related Skills

- [Related skill 1]
```

### Schema Validation

Documents should include YAML frontmatter:

```yaml
---
id: unique-identifier
type: role|group|asset|protocol|agreement|identity
membrane: 0|1|2|3|all
requires: [[prerequisite]]
governs: [[governed-item]]
triggers: [trigger-condition]
---
```

---

## Amendment & Governance

### Types of Changes

| Type | Scope | Window | Quorum |
|------|-------|--------|--------|
| Clarification | Typos, formatting | 48h | 3 members |
| Minor | Single component | 48h | 3 members |
| Substantial | Multiple components | 72h | All members |
| Foundational | Identity/core principles | 72h+ | All members + extended deliberation |

### Amendment Process

1. **Draft:** Create changes on a branch
2. **Propose:** Post in `#proposals` with rationale
3. **Discuss:** Address questions and concerns
4. **Consent:** 48-72h consent window
5. **Resolve:** Handle any objections
6. **Merge:** Agent merges after consent
7. **Record:** Amendment logged in Records/

### What Cannot Be Amended

- The canonical essay (Regenerative Accelerationist Manifesto)
- The founding charter
- Fundamental principles encoded in identity documents

These can only change through re-founding (creating a new commons).

---

## Troubleshooting

### Common Issues

**Q: Wiki-links don't work on GitHub**
A: Use Obsidian locally, or navigate manually through folders.

**Q: I can't find a document**
A: Check the index files in each folder, or use search.

**Q: How do I propose a change?**
A: Fork the repo, make changes, submit PR, post in `#proposals`.

**Q: Agent didn't verify my introduction**
A: Ensure you included all four elements (who, where, what draws, what brings).

**Q: My nomination was rejected**
A: Check validation errors in the response. Usually missing requirements.

### Getting Help

- **Discord:** Ask in `#help` or `#governance`
- **GitHub:** Open an issue
- **Stewards:** Ping `@Steward` role for urgent matters

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 0.1-draft | 2025-02 | Initial constitution draft |

---

*This guide is part of the Re/acc Commons Constitution. Amendments through consent.*
