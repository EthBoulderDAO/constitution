---
id: asset-github
type: asset
access_level: tiered
stewardship: "[[Steward Council]]"
platform: github
kg_entity: "kg://ethboulder/asset/github"
---
The constitutional record of ETH Boulder — the authoritative source for governance documents, amendment history, and coordination infrastructure.

## Purpose

GitHub is the constitutional record — the authoritative source for:
- Current constitutional text
- All amendments with rationale, date, and consent record
- Accountability process documentation
- Treasury allocation decisions
- Federation agreements

Discord is where we coordinate. GitHub is where we constitute.

## Location

Repository: `EthBoulderDAO/constitution`

## Repository Structure

```
/
├── 0. Meta/
├── 1. Identity/
├── 2. Structure/
├── 3. Protocols/
├── 4. Agreements/
├── .agents/
├── .claude/
├── ETH Boulder Constitution.md
├── README.md
└── GUIDE.md
```

## Access Tiers

| Level | Who | Permissions |
|-------|-----|-------------|
| Reader | Public | View all content |
| Contributor | [[Attendee]] and above | Open PRs, comment |
| Reviewer | [[Member]] and above | Approve PRs (as consent) |
| Merger | [[Steward Council]] | Merge PRs after consent documented |
| Admin | [[Steward Council]] | Repository settings |

## Amendment Workflow

1. **Proposal:** Open PR with clear rationale
2. **Notification:** All [[Member|Members]] notified via Discord
3. **Consent Window:** 72 hours for constitutional changes
4. **Documentation:** Consent record captured in PR comments
5. **Merge:** Steward merges after consent documented

## Machine-Readable Standards

- YAML frontmatter on all documents
- Consistent wiki-link syntax
- Semantic file naming
- Section anchors for precise reference

## Integration Points

| System | Integration |
|--------|-------------|
| Discord | PR notifications to governance channel |
| Knowledge Graph | Constitutional queries |
| Agent Systems | Constitutional parsing and compliance checking |

## Accountability

**Version Control:**
- Full git history preserved
- Each commit linked to governance process
- Branch protection on main

**Standards:**
- Signed commits encouraged
- Clear commit messages referencing proposals
- No force pushes to main

## Related Documents

- [[ETH Boulder Constitution]] — Primary content
- [[Constitution Amendment Protocol]]
- [[Knowledge Graph]] — Broader documentation
