---
id: role-steward
type: role
membrane: 3
requires: "[[Member]]"
discord_role: "@Steward"
nft_token: "stewardship-nft"
multisig_access: signer
kg_entity: "kg://ethboulder/role/steward"
---
Rotating curators with the highest trust level — those entrusted to tend conditions for the network to self-govern while maintaining facilitation authority, moderation tools, and multisig signing power.

## Purpose

Stewards are curators, not gatekeepers. They tend conditions for the network to self-govern. The moment stewardship becomes governance, it has failed. Monthly rotation ensures no one accumulates positional power.

## Criteria

- [[Member]] in good standing
- Deep commitment to network purpose, values, and democratic accountability
- Demonstrated facilitation capacity
- Willingness to serve in rotating curator role
- Not seeking to accumulate positional power

## Responsibilities

**Facilitation:** Ensure consent processes are followed, call for escalation when consent is ambiguous

**Constitution:** Merge governance PRs after consent is documented

**Accountability:** Facilitate accountability processes when triggered per [[3. Protocols/Cultural Protocols/Accountability Protocol|Accountability Protocol]]

**Treasury:** Sign multisig transactions after proper approval

**Documentation:** Maintain `#stewardship` channel with transparent documentation

**Rotation:** Complete knowledge transfer during monthly handoff

**Event Coordination:** Lead event circle during Pre-Event and Event phases, ensure convening execution

**Knowledge Graph Moderation:** Authority to revert contested edits, protect critical entities, manage entity disputes

## What Stewards Do NOT Have

- Tiebreaker power
- Veto authority
- Final say on content or direction
- Greater weight in consent processes

## Benefits

| Category | Access |
|----------|--------|
| **Authority** | Facilitation authority, moderation tools (serve network, not person) |
| **Channels** | Full admin all channels including `#multisig-ops` |
| **Treasury** | Signer access — approve/reject proposed transactions |
| **Knowledge Graph** | Moderation authority — revert edits, protect entities, resolve disputes |
| **Governance** | Same as Member — no additional voting weight |

**Note:** As a Steward, you are also a [[Member]] and retain all Member rights.

## Participation Expectations

![[3. Protocols/Cultural Protocols/Participation Cadence Protocol#Steward]]

## Event Cycle Responsibilities

| Phase | Steward Expectations |
|-------|---------------------|
| **Inter-Event** | Normal stewardship duties, third space relationship maintenance |
| **Pre-Event** | Lead Event Circle, coordinate logistics, facilitate session QV |
| **Event** | Full presence, real-time coordination, emergency decision authority |
| **Post-Event** | Lead retrospective, ensure knowledge graph enrichment, facilitate fast-track memberships |

## Term Structure

| Aspect | Detail |
|--------|--------|
| Term Length | 1 month |
| Rotation | Monthly handoff with knowledge transfer |
| Re-selection | May serve again after at least 1 month gap |
| Council Size | 2-3 active Stewards at any time |

## On-Chain Verification

| Platform | Permission | Mechanism |
|----------|------------|-----------|
| Discord | @Steward role | Bot upgrade on consent completion |
| Multi-sig | Signer | Gnosis Safe signer (threshold: majority must sign) |
| NFT | Stewardship NFT | Time-limited, minted on selection, burned on rotation |

## Emergency Authority

For actions posing immediate harm (doxxing, harassment, treasury theft):
- Any Steward can initiate immediate temporary suspension
- Post-hoc ratification by [[Stewardship]] within 48h
- Full accountability process follows
- Documented with emergency rationale

## Related Protocols

- [[3. Protocols/Role Protocols/Steward Protocol|Steward Protocol]]
- [[3. Protocols/Group Protocols/Stewardship Protocol|Stewardship Protocol]]
- [[3. Protocols/Asset Protocols/Treasury Management Protocol|Treasury Management Protocol]]
- [[3. Protocols/Cultural Protocols/Accountability Protocol|Accountability Protocol]]
- [[3. Protocols/Group Protocols/Event Circle Protocol|Event Circle Protocol]]
- [[3. Protocols/Asset Protocols/Knowledge Graph Protocol|Knowledge Graph Protocol]]
