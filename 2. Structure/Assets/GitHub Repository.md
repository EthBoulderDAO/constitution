---
id: asset-github
type: asset
access_level: tiered
stewardship: "[[Stewardship]]"
platform: github
---
The constitutional record of the Re/acc Commons — the authoritative source for governance documents, amendment history, and coordination infrastructure.

## Purpose

GitHub is the constitutional record — the authoritative source for:
- Current constitutional text
- All amendments with rationale, date, and consent record
- Accountability process documentation
- Treasury allocation decisions
- Federation agreements

Discord is where we coordinate. GitHub is where we constitute.

## Location

Repository: `[organization/reacc-commons-constitution]`

## Repository Structure

```
/
├── Re-acc Commons Constitution/     # Full constitution structure
│   ├── 0. Meta/
│   ├── 1. Identity/
│   ├── 2. Structure/
│   ├── 3. Protocols/
│   ├── 4. Agreements/
│   └── Re-acc Commons Constitution.md
├── Records/
│   ├── Amendments/                   # Amendment history
│   ├── Accountability/               # Process documentation
│   ├── Treasury/                     # Allocation records
│   └── Federation/                   # Agreement records
└── README.md
```

## Access Tiers

| Level | Who | Permissions |
|-------|-----|-------------|
| Reader | Public | View all content |
| Contributor | [[Participant]] and above | Open PRs, comment |
| Reviewer | [[Member]] and above | Approve PRs (as consent) |
| Merger | [[Steward]] | Merge PRs after consent documented |
| Admin | [[Stewardship]] | Repository settings |

## Amendment Workflow

1. **Proposal:** Open PR with clear rationale
2. **Notification:** All [[Member|Members]] notified via Discord
3. **Consent Window:** 72 hours for foundational changes
4. **Documentation:** Consent record captured in PR comments
5. **Merge:** [[Steward]] merges after consent documented
6. **Record:** Amendment logged in `/Records/Amendments/`

## Machine-Readable Standards

- YAML frontmatter on all documents
- Consistent wiki-link syntax
- Semantic file naming
- Section anchors for precise reference

## Integration Points

| System | Integration |
|--------|-------------|
| Discord | PR notifications to `#proposals` |
| NFT Contracts | Membership verification references |
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

- [[Commons Constitution]] — Primary content
- [[3. Protocols/Asset Protocols/Constitution Amendment Protocol|Constitution Amendment Protocol]]
- [[Knowledge Commons]] — Broader documentation
