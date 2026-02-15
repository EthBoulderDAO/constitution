---
id: protocol-discord
type: protocol
protocol_type: asset
governs: "[[Discord Server]]"
triggers: architecture-change
kg_entity: "kg://ethboulder/protocol/discord"
---
This protocol governs the structure and operation of the [[Discord Server]] — the primary coordination platform.

## Contents

- [[#Channel Architecture]]
- [[#Role Synchronization]]
- [[#Bot Configuration]]
- [[#Moderation]]
- [[#Related Protocols]]

## Channel Architecture

### Community Layer

| Channel | Purpose | Write Access | Read Access |
|---------|---------|--------------|-------------|
| `#general` | General discussion | [[Attendee]]+ | All |
| `#knowledge-graph` | Graph coordination | [[Attendee]]+ | All |
| `#governance` | Proposals | [[Member]]+ | All |
| `#accountability` | Process records | [[Steward Council]] | [[Member]]+ |
| `#agent-commons` | Agent coordination | [[Agent]] | [[Member]]+ |

### Function Lead Channels

| Channel | Purpose | Write Access | Read Access |
|---------|---------|--------------|-------------|
| `#event-coordination` | Event planning | Event Lead + Members | Members+ |
| `#treasury` | Treasury operations | Treasury Lead + Members | Members+ |
| `#knowledge` | Graph stewardship | Knowledge Lead + Members | Members+ |
| `#third-space` | Partnerships | Third Space Lead + Members | Members+ |

### Governance Layer

| Channel | Purpose | Write Access | Read Access |
|---------|---------|--------------|-------------|
| `#steward-council` | Council coordination | [[Steward Council]] | [[Steward Council]] |
| `#multisig-ops` | Treasury execution | [[Steward Council]] | [[Steward Council]] |

## Role Synchronization

### Discord Role Mapping

| Network Role | Discord Role | Color | Assignment |
|-------------|--------------|-------|------------|
| [[Attendee]] | @Attendee | Gray | On event check-in |
| [[Member]] | @Member | Blue | On consent completion |
| [[Steward]] | @Steward | Gold | On election completion |
| [[Agent]] | @Agent | Purple | On registration |
| Function Lead | @Lead | Green | On volunteer acceptance |

## Bot Configuration

### Governance Bot

**Functions:**
- Post notifications for proposals
- Track consent emoji reactions
- Calculate quorum status
- Notify when windows close

**Permissions:**
- Read messages in `#governance`
- Send messages in `#governance`
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
| Message deletion | [[Steward Council]] | Log reason |
| Timeout | [[Steward Council]] | Log reason + duration |
| Temporary suspension | [[Steward Council]] | Per [[Accountability Protocol]] |
| Permanent ban | [[Member Assembly]] | Full consent |

### Principles

- Bots execute, humans judge
- Moderation serves network, not personal views
- All significant actions documented
- Emergency actions require ratification

## Channel Changes

Adding, removing, or restructuring channels requires:
- 3-member consent + 48h for minor changes
- Full member consent + 72h for structural changes

## Related Protocols

- [[Attendee Protocol]] — Entry process
- [[Member Protocol]] — Membership
- [[Accountability Protocol]] — Moderation
- [[Discord Server]] — Asset documentation
