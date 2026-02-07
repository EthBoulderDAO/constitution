---
id: protocol-discord
type: protocol
protocol_type: asset
governs: "[[Discord Server]]"
triggers: architecture-change
---
This protocol governs the structure and operation of the [[Discord Server]] — the primary coordination platform.

## Contents

- [[#Channel Architecture]]
- [[#Role Synchronization]]
- [[#Bot Configuration]]
- [[#NFT Integration]]
- [[#Moderation]]
- [[#Related Protocols]]

## Channel Architecture

### Public Layer (Membrane Zero → One)

| Channel | Purpose | Write Access | Read Access |
|---------|---------|--------------|-------------|
| `#threshold` | Introductions | [[Newcomer]] | All |
| `#commons-floor` | General discussion | [[Participant]]+ | [[Participant]]+ |
| `#knowledge-commons` | Documentation | [[Participant]]+ | [[Participant]]+ |
| `#proposals` | Governance | [[Participant]]+ | [[Participant]]+ |
| `#accountability` | Process records | [[Steward]] | [[Participant]]+ |
| `#agent-commons` | Agent coordination | [[Agent]] | [[Participant]]+ |
| `#[working-circle]` | Circle channels | Circle members | [[Participant]]+ |

### Inner Layer (Membrane Two)

| Channel | Purpose | Write Access | Read Access |
|---------|---------|--------------|-------------|
| `#stewardship` | Steward coordination | [[Steward]] | [[Member]] |
| `#treasury` | Treasury operations | [[Member]]+ | [[Member]]+ |

### Solidarity Economy (Membrane Three)

| Channel | Purpose | Write Access | Read Access |
|---------|---------|--------------|-------------|
| `#multisig-ops` | Treasury execution | [[Steward]] | [[Steward]] |

## Role Synchronization

### Discord Role Mapping

| Commons Role | Discord Role | Color | Assignment |
|-------------|--------------|-------|------------|
| [[Newcomer]] | @Newcomer | Gray | Bot on intro post |
| [[Participant]] | @Participant | Green | Bot on verification |
| [[Member]] | @Member | Blue | Bot on consent + NFT |
| [[Steward]] | @Steward | Gold | Bot on consent + NFT |
| [[Agent]] | @Agent | Purple | Bot on registration |

### NFT-Gated Roles

@Member and @Steward can be verified via NFT:
1. User connects wallet to Discord verification bot
2. Bot checks for Membership or Stewardship NFT
3. Matching role assigned/confirmed
4. Syncs with on-chain state

**Fallback:** Manual role assignment by Steward if NFT verification unavailable

## Bot Configuration

### Verification Bot

**Functions:**
- Check introduction completeness in `#threshold`
- Query Agent for pattern verification
- Assign roles on successful verification
- Sync NFT-based role verification

**Permissions:**
- Read messages in `#threshold`
- Manage roles (add/remove)
- Send messages in `#threshold`

### Governance Bot

**Functions:**
- Post notifications for proposals
- Track consent emoji reactions
- Calculate quorum status
- Notify when windows close

**Permissions:**
- Read messages in `#proposals`
- Send messages in `#proposals`
- Add reactions

### Moderation Bot

**Functions:**
- Spam detection and removal
- Link safety checking
- Rate limiting for new accounts

**Permissions:**
- Read all channels
- Delete messages (spam only)
- Timeout users (rate limiting)

**Constraints:**
- Cannot assess alignment
- Cannot make moderation judgments
- Can be overridden by Steward within 24h

## NFT Integration

### Membership NFT

- Minted on [[Member Protocol|Member]] consent completion
- Contains metadata: join date, membrane level
- Verifiable on-chain credential
- Unlocks @Member Discord role
- Links to multi-sig viewer access

### Stewardship NFT

- Minted on [[Steward Protocol|Steward]] selection
- Time-limited (corresponds to term)
- Contains metadata: term dates, scope
- Unlocks @Steward Discord role
- Links to multi-sig signer access
- Burned on rotation

### Agent Registration Token

- Minted on [[Agent Protocol|Agent]] registration
- Contains metadata: scope, operator, registration date
- Unlocks @Agent Discord role
- Links to multi-sig signer access

## Moderation

### Automated Actions

| Action | Trigger | Override |
|--------|---------|----------|
| Spam removal | Automated detection | Steward 24h |
| Rate limiting | New account + high volume | Automatic expiry |
| Link warning | Suspicious links | Steward review |

### Human Actions

| Action | Authority | Documentation |
|--------|-----------|---------------|
| Message deletion | [[Steward]] | Log reason |
| Timeout | [[Steward]] | Log reason + duration |
| Temporary suspension | [[Steward]] | Per [[3. Protocols/Cultural Protocols/Accountability Protocol\|Accountability Protocol]] |
| Permanent ban | [[Commons Assembly]] | Full consent |

### Principles

- Bots execute, humans judge
- Moderation serves commons, not personal views
- All significant actions documented
- Emergency actions require ratification

## Channel Changes

Adding, removing, or restructuring channels requires:
- 3-member consent + 48h for minor changes
- Full commons consent + 72h for structural changes

## Related Protocols

- [[3. Protocols/Role Protocols/Newcomer Protocol|Newcomer Protocol]] — Threshold process
- [[3. Protocols/Role Protocols/Participant Protocol|Participant Protocol]] — Verification
- [[3. Protocols/Cultural Protocols/Accountability Protocol|Accountability Protocol]] — Moderation
- [[2. Structure/Assets/Discord Server|Discord Server]] — Asset documentation
