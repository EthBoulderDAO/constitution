---
id: asset-discord
type: asset
access_level: tiered
stewardship: "[[Steward Council]]"
platform: discord
kg_entity: "kg://ethboulder/asset/discord"
---
The primary coordination and communication platform for ETH Boulder — where daily coordination, governance processes, and community building unfold.

## Purpose

Discord is where we coordinate. [[GitHub Repository|GitHub]] is where we constitute. Discord provides:
- Governance process facilitation
- Community building and relationship development
- Agent-human interaction channels
- Function Lead coordination

## Channel Architecture

### Community Layer

| Channel | Purpose | Access |
|---------|---------|--------|
| `#general` | General coordination and discussion | [[Attendee\|Attendees]] and above |
| `#knowledge-graph` | Graph documentation and discussion | All participants |
| `#governance` | Proposals and consent processes | All ([[Member\|Members]] + [[Agent\|Agents]] vote) |
| `#accountability` | Documented accountability processes | Members and above |
| `#agent-commons` | Agent coordination and output | [[Agent\|Agents]] + Members |

### Function Lead Channels

| Channel | Purpose | Access |
|---------|---------|--------|
| `#event-coordination` | Event planning and logistics | Event Leads + Members |
| `#treasury` | Treasury proposals and records | Treasury Lead + Members |
| `#knowledge` | Knowledge Graph stewardship | Knowledge Lead + Members |
| `#third-space` | Partnership coordination | Third Space Lead + Members |

### Governance Layer

| Channel | Purpose | Access |
|---------|---------|--------|
| `#steward-council` | Council coordination | [[Steward Council]] members |
| `#multisig-ops` | Treasury execution | Stewards only |

## Role-to-Discord Mapping

| Network Role | Discord Role | Assignment |
|-------------|--------------|------------|
| [[Attendee]] | @Attendee | On event check-in |
| [[Member]] | @Member | On consent completion |
| [[Steward]] | @Steward | On election completion |
| [[Agent]] | @Agent | On registration |
| Function Lead | @Lead | On lead volunteer acceptance |

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

## Moderation Authority

| Actor | Authority | Accountability |
|-------|-----------|----------------|
| Bots | Spam removal, automated actions | Steward reversible |
| [[Steward Council]] | Full moderation, emergency suspension | [[Member Assembly]] |
| [[Member\|Members]] | Report concerns, call-up mechanism | Steward Council |

## Related Documents

- [[Discord Architecture Protocol]]
- [[Accountability Protocol]]
- [[Roles Index]]
