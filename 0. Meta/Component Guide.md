# Re/acc Commons Constitution Component Guide

This guide explains the component types that compose the DNA of the Re/acc Commons Constitution.

## Overview

The Constitution is organized into four main categories:

- **Identity** — Core meaning and intentionality
- **Structure** — Roles, Groups, and Assets
- **Protocols** — Procedures and processes
- **Agreements** — Role-specific compacts that transclude relevant content

---

# Identity Components

Identity components define the foundational purpose, values, and direction of the Commons.

## Identity Component Types

| Component | Description | Temporal Focus |
|-----------|-------------|----------------|
| **Vision** | What we envision for the future | Long-term aspiration |
| **Purpose** | Why we exist | Present, core reason |
| **Mission** | What we do to fulfill purpose | Present activities |
| **Functions** | Core activities and capabilities | Operational |
| **Mandates** | Core commitments and boundaries | Non-negotiable |
| **Values** | What we stand for | Continuous ethical guidance |
| **Worldview** | How we understand the world | Philosophical foundation |

---

# Structure Components

Structure components define the organizational form through which identity is enacted.

## Roles

Roles define individual membership types with distinct rights, responsibilities, and membrane positions.

| Role | Membrane | Trust Level |
|------|----------|-------------|
| [[Newcomer]] | Zero: Threshold | Entry |
| [[Participant]] | One: Public Commons | Demonstrated |
| [[Member]] | Two: Inner Commons | Verified |
| [[Steward]] | Three: Solidarity Economy | Entrusted |
| [[Agent]] | Across All | Authorized |

### Role Document Structure

- **Purpose:** Why this role exists
- **Criteria:** Requirements for holding the role
- **Responsibilities:** What the role holder does
- **Benefits:** Access and permissions the role provides
- **Related Protocols:** Protocols governing this role

---

## Groups

Groups define collective bodies that coordinate, deliberate, and make decisions.

| Group | Function |
|-------|----------|
| [[Working Circle]] | Domain-specific coordination |
| [[Stewardship]] | Facilitation and execution |
| [[Commons Assembly]] | Sovereign governance |

### Group Document Structure

- **Purpose:** Why this group exists
- **Composition & Quorum:** Who participates and decision thresholds
- **Responsibilities:** What the group does
- **Decision Authority:** What the group can decide
- **Related Protocols:** Protocols governing the group

---

## Assets

Assets define shared resources stewarded for collective benefit.

| Asset | Type |
|-------|------|
| [[Commons Constitution]] | Constitutional |
| [[Canonical Essay]] | Constitutional |
| [[Commons Treasury]] | Infrastructure |
| [[Discord Server]] | Infrastructure |
| [[GitHub Repository]] | Infrastructure |
| [[Knowledge Commons]] | Knowledge |
| [[Federation Agreements]] | Relational |

### Asset Document Structure

- **Purpose:** What the asset enables
- **Location:** Where it's accessed
- **Access Tiers:** Who can use it and how
- **Accountability:** How it's maintained
- **Related Protocols:** Protocols governing the asset

---

# Protocol Components

Protocols are formalized processes governing Commons operations.

## Protocol Types

| Type | Governs |
|------|---------|
| **Role Protocols** | How specific roles operate and transition |
| **Group Protocols** | How collective bodies function |
| **Asset Protocols** | How shared resources are managed |
| **Cultural Protocols** | How community practices unfold |

### Protocol Document Structure

- **Instantiation:** What triggers the protocol
- **Authority & Oversight:** Who has decision rights
- **Process:** Step-by-step procedures
- **Completion & Outputs:** When it's done and what it produces
- **Exceptions:** Edge cases and how to handle them
- **Related Protocols:** Connected protocols

---

# Agreement Components

Agreements are role-specific compacts that participants affirm upon membrane crossing. They transclude relevant content to create a complete picture of membership.

### Agreement Document Structure

- **Welcome:** Introduction to the role
- **Freedom to Participate:** Constitutional freedom statement
- **Your Role:** Transcluded role definition
- **Key Responsibilities:** Role-specific obligations
- **Your Access:** Platform and permission summary
- **About the Commons:** Transcluded identity and structure

---

# How Components Relate

```
Identity (why) → Structure (who/what) → Protocols (how) → Agreements (commitment)
```

- **Identity** provides the grounding that all other components serve
- **Structure** creates the organizational form through which identity is enacted
- **Protocols** operationalize structure through repeatable processes
- **Agreements** bind participants to the whole through role-specific commitments

---

# Wiki-Link Patterns

For machine-readability, this constitution uses consistent wiki-link patterns:

| Pattern | Meaning | Example |
|---------|---------|---------|
| `[[Document]]` | Link to document | `[[Member]]` |
| `[[Folder/Document\|Alias]]` | Link with display text | `[[1. Identity/Purpose\|Purpose]]` |
| `[[Document#Section]]` | Link to section | `[[Member#Benefits]]` |
| `![[Document]]` | Transclude document | `![[Member]]` |
| `![[Document#Section]]` | Transclude section | `![[Member#Responsibilities]]` |

---

# Machine-Readable Metadata

All documents include YAML frontmatter for AI agent parsing:

```yaml
---
id: [unique-identifier]
type: [role|group|asset|protocol|agreement|identity]
membrane: [0|1|2|3|all]
requires: [[prerequisite]]
governs: [[governed-item]]
triggers: [trigger-condition]
---
```

---

# Navigation

- **Main Document:** [[Re-acc Commons Constitution]]
- **Indices:**
  - [[1. Identity/Identity Index|Identity Index]]
  - [[2. Structure/Structure Index|Structure Index]]
    - [[2. Structure/Roles/Roles Index|Roles Index]]
    - [[2. Structure/Groups/Groups Index|Groups Index]]
    - [[2. Structure/Assets/Assets Index|Assets Index]]
  - [[3. Protocols/Protocols Index|Protocols Index]]
  - [[4. Agreements/Agreement Index|Agreement Index]]

---

# Constitutional Sources

| Document | Nature | Amendment |
|----------|--------|-----------|
| [[.claude/a-regenerative-accelerationist-manifesto\|Canonical Essay]] | Permanent source text | Never |
| [[Re-acc Commons Constitution]] | Living interpretation | Through consent |

The essay provides the permanent foundation. The constitution operationalizes it for current conditions.
