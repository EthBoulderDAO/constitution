---
id: asset-constitution
type: asset
access_level: public
stewardship: "[[Stewardship]]"
---
The governing agreement for all participants in the Re/acc Commons — encoding collective identity, membrane architecture, and coordination protocols.

## Purpose

- Encode shared identity, purpose, values, and worldview
- Define membrane architecture for progressive trust
- Specify roles, groups, and their relationships
- Establish protocols for coordination and accountability
- Provide machine-readable structure for AI agents

## Location

Primary: [[GitHub Repository]] at `/Re-acc Commons Constitution/`
Readable: Obsidian vault with wiki-links
Canonical: GitHub is authoritative source of truth

## Technical Structure

```
Re-acc Commons Constitution/
├── 0. Meta/
├── 1. Identity/
├── 2. Structure/
│   ├── Roles/
│   ├── Groups/
│   └── Assets/
├── 3. Protocols/
│   ├── Role Protocols/
│   ├── Group Protocols/
│   ├── Asset Protocols/
│   └── Cultural Protocols/
├── 4. Agreements/
└── Re-acc Commons Constitution.md
```

## Machine-Readable Features

- YAML frontmatter with structured metadata
- Consistent wiki-link patterns for graph traversal
- Transclusion syntax for content embedding
- Section anchors for precise referencing

## Access and Permissions

| Level | Who | Permissions |
|-------|-----|-------------|
| Reader | Anyone | View constitution |
| Contributor | [[Participant]] and above | Propose amendments via PR |
| Merger | [[Steward]] | Merge PRs after consent documented |

## Amendment Process

This constitution is a foundational shared norm. Changes follow full commons consent:

1. Propose via Pull Request with clear rationale
2. All [[Member|Members]] notified
3. 72-hour consent window
4. No unresolved paramount objections
5. [[Steward]] merges after consent documented in PR

The [[Canonical Essay]] is never amended through this process. It stands as the source text. This constitution is the living interpretation.

Previous versions remain accessible. The history of our governance is itself a knowledge commons.

## Accountability

**Version Control:**
- Full git history maintained
- Each amendment includes: change, rationale, proposer, consent record, date
- Previous versions accessible

**Standards:**
- Clear rationale for all changes
- Consent record preserved in PR
- No unilateral modifications

## Related Documents

- [[Canonical Essay]] — Permanent source text
- [[3. Protocols/Asset Protocols/Constitution Amendment Protocol|Constitution Amendment Protocol]]
- [[GitHub Repository]] — Storage location
