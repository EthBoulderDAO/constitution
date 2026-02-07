---
id: protocol-knowledge-commons
type: protocol
protocol_type: asset
governs: "[[Knowledge Commons]]"
triggers: contribution
---
This protocol governs the stewardship, contribution, and federation of the [[Knowledge Commons]] — shared knowledge that costs nothing to share and creates compounding value.

## Contents

- [[#Principles]]
- [[#Contribution Process]]
- [[#Quality Standards]]
- [[#Schema Standards]]
- [[#Federation]]
- [[#Related Protocols]]

## Principles

**Design global, implement local.** Knowledge flows globally through open protocols. Each community adapts to their specific context.

**The cosmolocal pattern.** Successful practices spread through adaptation rather than replication. Local implementations feed learnings back into the global commons.

**Machine-readable by design.** Shared metadata standards enable AI agents to traverse, index, and connect patterns across the knowledge graph.

**Share freely.** All content in the Knowledge Commons is licensed for open sharing and adaptation (CC BY-SA 4.0 unless otherwise specified).

## Contribution Process

| Step | Action | Actor | Timeline |
|------|--------|-------|----------|
| 1 | Draft content | Contributor | As needed |
| 2 | Apply schema standards | Contributor | Before submission |
| 3 | Submit to relevant circle | Contributor | Submission |
| 4 | Review for quality | Circle curator | 1 week |
| 5 | Integrate into commons | Curator | After review |
| 6 | Index for discoverability | [[Agent]] | Automated |

### Who Can Contribute

- [[Participant|Participants]] and above can add content
- [[Working Circle]] curators maintain quality
- [[Agent|Agents]] can contribute within authorized scope

## Quality Standards

### Content Requirements

| Requirement | Description |
|-------------|-------------|
| **Accuracy** | Factually correct, sources cited where applicable |
| **Clarity** | Understandable to target audience |
| **Actionability** | Provides clear guidance for implementation |
| **Attribution** | Credits sources and prior work |
| **License** | Clear license statement (default: CC BY-SA 4.0) |

### Pattern Documentation

Patterns should include:
- **Context:** When this pattern applies
- **Problem:** What challenge it addresses
- **Solution:** How the pattern works
- **Implementation:** Practical steps
- **Outcomes:** Expected results
- **Variations:** Adaptations for different contexts
- **Sources:** Where this pattern originated or was refined

## Schema Standards

For machine-readability, all content includes YAML frontmatter:

```yaml
---
id: [unique-identifier]
type: [pattern|protocol|schema|learning|tool]
domain: [knowledge-domain]
federation: [public|federated|internal]
created: [ISO-date]
updated: [ISO-date]
authors: [list of contributors]
license: CC BY-SA 4.0
tags: [relevant-tags]
related: [[related-documents]]
---
```

### Domains

| Domain | Description |
|--------|-------------|
| `governance` | Decision-making, consent, accountability |
| `coordination` | Working circles, collaboration |
| `economics` | Treasury, value flow, solidarity economy |
| `technology` | Agents, infrastructure, tools |
| `federation` | Cross-network patterns |
| `culture` | Practices, rituals, values |

### Federation Visibility

| Level | Meaning |
|-------|---------|
| `public` | Visible to all, including external |
| `federated` | Shared with federated networks |
| `internal` | Commons members only |

## Federation

Knowledge is shared across the regenerative web through:

### Schema Bridges

[[Agent|Agents]] maintain interoperability between different knowledge commons:
- Map between different schema formats
- Translate identifiers across networks
- Preserve attribution through federation

### Mutual Indexing

Federated networks can discover and reference patterns:
- Shared search across federated commons
- Cross-referencing with network attribution
- Change notifications for linked content

### Learning Flow

What works in one node strengthens the whole web:
- Successful patterns documented and shared
- Failed experiments recorded with learnings
- Adaptations tracked and attributed

## Curation Responsibility

The **Knowledge Commons Circle** stewards this asset:
- Maintain documentation quality
- Curate and organize patterns
- Develop schema standards
- Support federation knowledge sharing
- Review and integrate contributions

## Related Protocols

- [[3. Protocols/Group Protocols/Working Circle Protocol|Working Circle Protocol]] — Knowledge Commons Circle
- [[3. Protocols/Asset Protocols/Federation Protocol|Federation Protocol]] — Cross-network sharing
- [[2. Structure/Assets/Knowledge Commons|Knowledge Commons]] — Asset documentation
