---
id: protocol-third-space-federation
type: protocol
protocol_type: asset
governs: "[[Third Space Network]]"
triggers: partnership-formation
kg_entity: "kg://ethboulder/protocol/third-space-federation"
---
This protocol governs the formation, maintenance, and evolution of federation partnerships with third spaces — the physical venues that ground digital coordination in bioregional reality.

## Contents

- [[#Principles]]
- [[#Partnership Tiers]]
- [[#Formation Process]]
- [[#Agreement Elements]]
- [[#Maintenance]]
- [[#Related Protocols]]

## Principles

**Third spaces are constitutional infrastructure.** They are not merely venues but partners in cultivating scenius.

**Physical presence is not optional.** The network cannot be purely digital. Third spaces ground our coordination in place.

**Federation, not ownership.** Third spaces maintain their own identity and governance. We partner, not absorb.

**Reciprocity.** Both the network and the third space must benefit from the relationship.

## Partnership Tiers

| Tier | Description | Commitment |
|------|-------------|------------|
| **Affiliated** | Informal relationship, network members welcome | Low |
| **Partner** | Formal agreement, event hosting capability | Medium |
| **Federation** | Deep integration, knowledge graph sync, joint programming | High |

### Tier Progression

Partnerships typically progress through tiers:
1. Informal use by network members → Affiliated
2. Successful event hosting → Partner
3. Sustained collaboration → Federation

Regression possible if relationship deteriorates.

## Formation Process

### Discovery & Cultivation

| Step | Action | Actor | Timeline |
|------|--------|-------|----------|
| 1 | Identify potential partner | Any participant | Ongoing |
| 2 | Initial relationship building | Third Space Lead | 1-3 months |
| 3 | Informal network use | Network members | As natural |
| 4 | Assess partnership fit | Third Space Lead | When ready |

### Affiliation (Low Commitment)

| Step | Action | Actor |
|------|--------|-------|
| 1 | Circle confirms mutual interest | Third Space Lead |
| 2 | Document informal understanding | Circle |
| 3 | Add to knowledge graph as Affiliated | Circle |
| 4 | Announce to network | Circle |

No formal consent required for affiliation.

### Partnership (Medium Commitment)

| Step | Action | Actor | Process |
|------|--------|-------|---------|
| 1 | Draft partnership agreement | Third Space Lead | Negotiation |
| 2 | Third space confirms terms | Partner | Agreement |
| 3 | Submit to Member Assembly | Circle | Proposal |
| 4 | Consent process | Assembly | 3-member + 48h |
| 5 | Sign agreement | Both parties | After consent |
| 6 | Update knowledge graph | Agent | Automated |

### Federation (High Commitment)

| Step | Action | Actor | Process |
|------|--------|-------|---------|
| 1 | Demonstrate successful partnership | Both parties | Track record |
| 2 | Propose federation upgrade | Third Space Lead | Proposal |
| 3 | Detailed agreement negotiation | Circle + Partner | Extended |
| 4 | Submit to Member Assembly | Circle | Full consent |
| 5 | Consent process | Assembly | Full consent + 72h |
| 6 | Implement integration | Knowledge Lead | Technical |

## Agreement Elements

### Standard Partnership Agreement

| Element | Description |
|---------|-------------|
| **Parties** | ETH Boulder + Third Space |
| **Tier** | Partnership or Federation |
| **Duration** | Typically 1 year, renewable |
| **Space Access** | Terms for network use of physical space |
| **Event Hosting** | Framework for hosting network events |
| **Mutual Recognition** | Network recognizes venue; venue recognizes members |
| **Financial Terms** | Venue fees, revenue sharing, or in-kind exchange |
| **Exit Clause** | How either party can withdraw (typically 30 days notice) |

### Federation Agreement Additions

| Element | Description |
|---------|-------------|
| **Knowledge Graph Integration** | Venue entity, relationship permissions |
| **Joint Programming** | Framework for collaborative events |
| **Community Bridge** | How venue community can engage network |
| **Federation Sync** | If venue has own graph, sync terms |

## Financial Terms

### Common Structures

| Structure | Description | When Used |
|-----------|-------------|-----------|
| **In-Kind** | Mutual benefit, no money exchanged | Common for affiliates |
| **Event-Based** | Pay per event use | Common for partners |
| **Monthly Retainer** | Regular payment for ongoing access | Rare, high usage |
| **Revenue Share** | Share proceeds from joint events | Federation tier |
| **Grant** | Network provides grant to third space | Supporting mission-aligned spaces |

### Budget Integration

Third space costs included in:
- Event budget (event-related venue costs)
- Federation grants (ongoing partnership support)
- Grants allocations (third space development)

## Maintenance

### Annual Review

| Step | Action | Actor | Timeline |
|------|--------|-------|----------|
| 1 | Gather feedback from both parties | Third Space Lead | Post-Event |
| 2 | Assess relationship health | Circle | Post-Event |
| 3 | Propose renewal/changes | Circle | Post-Event |
| 4 | Consent if changes needed | Assembly | If applicable |
| 5 | Update agreement | Both parties | Before renewal date |

### Relationship Health Indicators

| Indicator | Green | Yellow | Red |
|-----------|-------|--------|-----|
| **Event Hosting** | Smooth, positive feedback | Some friction | Major issues |
| **Community Engagement** | Active cross-pollination | Limited interaction | Conflict |
| **Financial** | Terms honored | Occasional issues | Disputes |
| **Communication** | Regular, open | Sporadic | Breakdown |

### Relationship Degradation

If relationship deteriorates:
1. Direct conversation between Circle and partner
2. Mediation by Steward if needed
3. Tier downgrade proposal if unresolved
4. Partnership termination as last resort

### Termination Process

| Step | Action | Actor |
|------|--------|-------|
| 1 | Notice per agreement (typically 30 days) | Either party |
| 2 | Transition planning | Third Space Lead |
| 3 | Knowledge graph update | Agent |
| 4 | Final accounting | Treasury |
| 5 | Document learnings | Circle |

## Knowledge Graph Integration

### Third Space Entity

```cypher
(:ThirdSpace {
  id: "kg://ethboulder/thirdspace/[name]",
  name: "Partner Name",
  type: "coworking|cafe|makerspace|other",
  tier: "affiliated|partner|federation",
  location: "Boulder, CO",
  agreement_date: "YYYY-MM-DD",
  renewal_date: "YYYY-MM-DD"
})
```

### Relationships

```cypher
(:ThirdSpace)-[:PARTNER_OF]->(:Network {name: "ETH Boulder"})
(:Session)-[:HELD_AT]->(:ThirdSpace)
(:Person)-[:REGULAR_AT]->(:ThirdSpace)
(:Event)-[:VENUE]->(:ThirdSpace)
```

## Related Protocols

- [[3. Protocols/Asset Protocols/Federation Protocol|Federation Protocol]] — General federation framework
- [[Function Leads]] — Third Space Lead stewardship
- [[Third Space Network]] — Asset documentation
- [[Function Lead Protocol]] — Event Lead venue coordination
