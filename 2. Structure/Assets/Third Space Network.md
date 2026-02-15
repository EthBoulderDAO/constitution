---
id: asset-third-space-network
type: asset
access_level: internal
stewardship: "[[Function Leads]]"
kg_entity: "kg://ethboulder/asset/third-space-network"
---
Registry of federation partnerships with Boulder's third spaces — the physical venues where scenius happens and digital coordination meets bioregional reality.

## Purpose

Third spaces (neither home nor work) are constitutional infrastructure. They provide:
- Physical venues for network gatherings
- Serendipitous encounter opportunities
- Grounding for digital coordination
- Federation partnerships with local communities

The Third Space Network maintains formal relationships with these venues.

## Why Third Spaces Matter

Scenius — collective genius — requires physical co-presence. Boulder's density of cafes, coworking spaces, makerspaces, and gathering places creates the substrate for emergent collaboration.

The network cannot be purely digital. Third spaces are where:
- Attendees first encounter the network
- Ideas cross-pollinate through chance encounter
- Trust builds through repeated face-to-face interaction
- The annual convening physically manifests

## Partner Registry

Current and potential third space partners:

| Partner | Type | Status | Primary Use |
|---------|------|--------|-------------|
| **RegenHub** | Coworking/Events | Active Partner | Event venue, regular meetups |
| *Additional partners TBD* | | | |

## Partnership Tiers

| Tier | Description | Benefits |
|------|-------------|----------|
| **Affiliated** | Informal relationship | Network members welcome |
| **Partner** | Formal agreement | Event hosting, member recognition |
| **Federation** | Deep integration | Knowledge graph sync, joint programming |

## Federation Agreement Elements

Third space federation agreements include:

| Element | Description |
|---------|-------------|
| **Mutual Recognition** | Network recognizes venue as partner; venue recognizes network members |
| **Space Access** | Terms for network use of physical space |
| **Event Hosting** | Framework for hosting network events |
| **Knowledge Sharing** | How learnings flow between network and venue community |
| **Graph Integration** | Venue entity in knowledge graph with appropriate relationships |
| **Financial Terms** | If any — venue fees, revenue sharing, in-kind exchange |

## Knowledge Graph Integration

Third spaces are represented in the knowledge graph:

```cypher
# Third space entity
(:ThirdSpace {
  id: "kg://ethboulder/thirdspace/regenhub",
  name: "RegenHub",
  type: "coworking",
  location: "Boulder, CO",
  partnership_tier: "federation",
  agreement_date: "2026-01-15"
})

# Relationships
(:ThirdSpace)-[:HOSTS]->(:Session)
(:ThirdSpace)-[:PARTNER_OF]->(:Network)
(:Person)-[:REGULAR_AT]->(:ThirdSpace)
```

## Event Cycle Integration

| Phase | Third Space Activities |
|-------|----------------------|
| **Inter-Event** | Relationship cultivation, new partner outreach, casual meetups |
| **Pre-Event** | Venue booking, logistics coordination, partner briefing |
| **Event** | On-site coordination, partner liaison, space management |
| **Post-Event** | Partner feedback, relationship maintenance, agreement renewal |

## Cultivation Process

New third space partnerships develop through:

1. **Introduction** — Third Space Lead introduces network to venue
2. **Informal Use** — Network members begin frequenting venue
3. **Partnership Proposal** — Third Space Lead proposes formal agreement
4. **Consent** — Member Assembly approves per federation protocol
5. **Integration** — Venue added to graph, agreement documented

## Related Documents

- [[3. Protocols/Asset Protocols/Third Space Federation Protocol|Third Space Federation Protocol]]
- [[Function Leads]] — Third Space Lead stewardship
- [[Federation Agreements]] — General federation framework
