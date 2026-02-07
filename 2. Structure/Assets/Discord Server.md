---
id: asset-discord
type: asset
access_level: tiered
stewardship: "[[Stewardship]]"
platform: discord
---
The primary coordination and communication platform for the Re/acc Commons — where daily coordination, working circles, and governance processes unfold.

## Purpose

Discord is where we coordinate. [[GitHub Repository|GitHub]] is where we constitute. Discord provides:
- Real-time coordination for working circles
- Governance process facilitation
- Community building and relationship development
- Agent-human interaction channels

## Channel Architecture

### Public Layer (Membrane Zero → One)

| Channel | Purpose | Access |
|---------|---------|--------|
| `#threshold` | Introductions and charter acknowledgment | [[Newcomer|Newcomers]]: write. All others: read. |
| `#commons-floor` | General coordination and discussion | [[Participant|Participants]] and above |
| `#knowledge-commons` | Pattern documentation and knowledge sharing | Participants and above |
| `#proposals` | Governance proposals and consent processes | Participants and above ([[Member|Members]] vote) |
| `#accountability` | Documented accountability processes | Participants and above |
| Working circle channels | Domain-specific coordination | Participants and above |
| `#agent-commons` | Agent coordination and output | [[Agent|Agents]] + authorized participants |

### Inner Layer (Membrane Two)

| Channel | Purpose | Access |
|---------|---------|--------|
| `#stewardship` | Steward documentation and facilitation | Members: read. [[Steward|Stewards]]: read/write. |
| `#treasury` | Treasury proposals and transaction records | Members and above |

### Solidarity Economy (Membrane Three)

| Channel | Purpose | Access |
|---------|---------|--------|
| `#multisig-ops` | Operational treasury coordination | Stewards only |

## Role-to-Discord Mapping

| Commons Role | Discord Role | Assignment |
|-------------|--------------|------------|
| [[Newcomer]] | @Newcomer | Bot on introduction post |
| [[Participant]] | @Participant | Bot on agent verification |
| [[Member]] | @Member | Bot on consent completion + NFT verification |
| [[Steward]] | @Steward | Bot on consent completion + NFT verification |
| [[Agent]] | @Agent | Bot on registration verification |

## Bot-Enforcer Configuration

**Automated Actions:**
- Spam/disruption removal (Steward reversible within 24h)
- Role assignment upon verified introduction (Membrane Zero crossing)
- Role upgrades upon agent-verified patterns or consent completion

**Restricted Actions:**
- Role changes only upon documented accountability outcomes
- No autonomous alignment assessment — bots execute, humans judge

**NFT-Gated Roles:**
- @Member and @Steward roles can be unlocked via membership/stewardship NFTs
- NFT verification syncs with Discord through integration bot
- Provides on-chain verification of membership status

## Moderation Authority

| Actor | Authority | Accountability |
|-------|-----------|----------------|
| Bots | Spam removal, role assignment per protocol | Steward reversible |
| [[Steward|Stewards]] | Full moderation, emergency suspension | [[Commons Assembly]] |
| [[Member|Members]] | Report concerns, call-up mechanism | Stewardship |

## Related Documents

- [[3. Protocols/Asset Protocols/Discord Architecture Protocol|Discord Architecture Protocol]]
- [[3. Protocols/Cultural Protocols/Accountability Protocol|Accountability Protocol]]
- [[2. Structure/Roles/Roles Index|Roles Index]]
