---
id: asset-federation
type: asset
access_level: internal
stewardship: "[[Network Assembly]]"
kg_entity: "kg://ethboulder/asset/federation-agreements"
---
Formal relationships with aligned networks across the Ethereum localism web — agreements that enable trust to flow between federated communities while each maintains sovereignty.

## Purpose

This network is one node in a web, not the center of it. Federation agreements enable:
- Schema bridges maintaining interoperability
- Agent-to-agent coordination across network boundaries
- Mutual recognition of trust architectures
- Knowledge graph synchronization
- Shared learning that strengthens the whole web

We actively seek federation with Ethereum localism and bioregional networks.

## Federation Principles

**Sovereignty:** Each network maintains its own governance while contributing to something larger than itself.

**Reciprocity:** Federation is always voluntary, always reciprocal. Both networks benefit from the relationship.

**Differentiation:** Identical nodes have no resilience. Federation requires that networks bring distinct strengths.

**Many centers, one living web:** No network is the center. Value flows through relationships, not hierarchy.

## Types of Federation

| Type | Description | Commitment Level |
|------|-------------|-----------------|
| **Recognition** | Acknowledge aligned principles and values | Low — acknowledgment only |
| **Interoperability** | Share schemas and enable agent coordination | Medium — technical integration |
| **Trust Bridge** | Mutual recognition of membership/trust levels | High — governance alignment |
| **Third Space** | Physical venue partnership | Medium — physical integration |
| **Economic** | Shared treasury or resource flows | Highest — financial interdependence |

## Agreement Structure

Each federation agreement documents:
- **Parties:** Networks/spaces involved
- **Type:** Level of federation
- **Scope:** What is shared/recognized
- **Protocols:** How coordination works
- **Graph Integration:** Entity relationships in knowledge graph
- **Duration:** Term and renewal process
- **Exit:** How either party can withdraw

## Current Federations

| Network/Space | Type | Status | Notes |
|---------------|------|--------|-------|
| RegenHub | Third Space | Active | Primary venue partner |
| *Global Forum on Ethereum Localism* | Recognition | Affiliated | Principle alignment |
| *[Future partners]* | *[Type]* | *[Status]* | |

## Third Space Federation

Third spaces receive special treatment as constitutional infrastructure:

| Element | Description |
|---------|-------------|
| **Physical Presence** | Venue for network gatherings |
| **Community Bridge** | Access to venue's existing community |
| **Event Hosting** | Framework for annual convening |
| **Bioregional Grounding** | Physical anchor for digital coordination |

See [[Third Space Network]] for partner registry and [[3. Protocols/Asset Protocols/Third Space Federation Protocol|Third Space Federation Protocol]] for process.

## Agent Federation

AI agents in federated networks can coordinate through:
- Shared communication protocols (MCP)
- Cross-network identity verification
- Mutual task delegation
- Knowledge graph synchronization
- Query routing across federated graphs

## Approval Process

Federation agreements follow consent process based on commitment level:

| Type | Approval |
|------|----------|
| Recognition | 3-member consent + 48h |
| Interoperability | 3-member consent + 48h |
| Third Space | 3-member consent + 48h |
| Trust Bridge | Full network consent + 72h |
| Economic | Full network consent + 72h + extended deliberation |

## Knowledge Graph Integration

Federation relationships are represented in the graph:

```cypher
# Federation entity
(:Federation {
  type: "trust-bridge",
  parties: ["eth-boulder", "partner-network"],
  status: "active",
  agreement_date: "2026-01-15"
})

# Relationships
(:Network)-[:FEDERATED_WITH]->(:Network)
(:ThirdSpace)-[:PARTNER_OF]->(:Network)
(:Agent)-[:CAN_COORDINATE_WITH]->(:Agent)
```

## Related Documents

- [[3. Protocols/Asset Protocols/Federation Protocol|Federation Protocol]]
- [[3. Protocols/Asset Protocols/Third Space Federation Protocol|Third Space Federation Protocol]]
- [[Third Space Network]] — Physical venue partnerships
- [[Knowledge Graph]] — Federation sync infrastructure
- [[1. Identity/Values|Values]] — Federation Over Consolidation
