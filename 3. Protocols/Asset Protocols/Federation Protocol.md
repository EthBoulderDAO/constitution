---
id: protocol-federation
type: protocol
protocol_type: asset
governs: "[[Federation Agreements]]"
triggers: federation-proposal
---
This protocol governs the formation and operation of federation relationships with aligned networks across the regenerative web.

## Contents

- [[#Principles]]
- [[#Federation Types]]
- [[#Proposal Process]]
- [[#Ongoing Coordination]]
- [[#Agent Federation]]
- [[#Exit Process]]
- [[#Related Protocols]]

## Principles

**Sovereignty:** Each network maintains its own governance while contributing to something larger than itself.

**Reciprocity:** Federation is always voluntary, always reciprocal. Both networks benefit.

**Differentiation:** Identical nodes have no resilience. Each network brings distinct strengths.

**Many centers, one living web:** No network is the center. Value flows through relationships.

## Federation Types

| Type | Commitment | Approval |
|------|------------|----------|
| **Recognition** | Acknowledge aligned principles | 3-member + 48h |
| **Interoperability** | Share schemas, enable agent coordination | 3-member + 48h |
| **Trust Bridge** | Mutual recognition of membership/trust | Full commons + 72h |
| **Economic** | Shared treasury or resource flows | Full commons + 72h + deliberation |

### Type Details

**Recognition**
- Public acknowledgment of alignment
- Listing in federated networks directory
- No operational integration

**Interoperability**
- Shared schema standards
- Agent-to-agent communication channels
- Knowledge commons cross-referencing
- No membership recognition

**Trust Bridge**
- Members of one network recognized by the other
- Streamlined membrane crossing for trusted participants
- Shared accountability standards
- Mutual support obligations

**Economic**
- Resource flow agreements
- Shared treasury components
- Cross-network project funding
- Deepest commitment level

## Proposal Process

| Step | Action | Actor | Timeline |
|------|--------|-------|----------|
| 1 | Initial contact | Any participant | Discovery |
| 2 | Exploratory dialogue | Federation Commons Circle | 2-4 weeks |
| 3 | Draft federation agreement | Circle with partner network | As needed |
| 4 | Internal review | Both networks | 1 week |
| 5 | Post proposal in `#proposals` | Circle | Initiates consent |
| 6 | Consent window | [[Commons Assembly]] | 48h or 72h |
| 7 | Partner network approval | Partner network | Per their process |
| 8 | Sign/ratify agreement | [[Stewardship]] | After mutual consent |
| 9 | Document in [[GitHub Repository]] | [[Steward]] | Post-signing |
| 10 | Implement integration | Federation Commons Circle | Per agreement |

### Agreement Template

```
## Federation Agreement

**Parties:** [This Commons] and [Partner Network]
**Type:** [Recognition / Interoperability / Trust Bridge / Economic]
**Effective Date:** [Date]

### Scope
[What is included in this federation]

### Mutual Commitments
[What each party commits to]

### Coordination Mechanisms
[How networks will coordinate]

### Duration and Renewal
[Term length, renewal process]

### Modification
[How the agreement can be changed]

### Exit
[How either party can withdraw]

### Signatures
[Authorized signatories from each network]
```

## Ongoing Coordination

### Regular Contact

- Federation Commons Circle maintains relationship
- Regular check-ins (frequency per agreement)
- Issue escalation path

### Schema Maintenance

For interoperability and trust bridge:
- Shared schema standards documented
- Schema changes coordinated
- Breaking changes flagged in advance

### Trust Updates

For trust bridge:
- Membership/role changes communicated
- Accountability outcomes shared (as appropriate)
- Trust levels synchronized

## Agent Federation

AI agents can coordinate across federated networks:

### Requirements

- Federation at Interoperability level or higher
- Agent registered in home network
- Scope authorized by both networks
- Mutual agent protocol recognition

### Cross-Network Agent Operations

| Operation | Home Network | Federated Network |
|-----------|--------------|-------------------|
| Identity verification | Provides attestation | Verifies attestation |
| Scope | Authorizes home scope | Grants guest scope |
| Accountability | Primary responsibility | Can report concerns |
| Actions | Full operational | Within guest scope |

### Agent Communication

- Shared communication protocols
- Cross-network message routing
- Attribution preserved across networks

### Agent Identity Across Networks

```yaml
agent_identity:
  local_id: "governance-agent"
  network: "re/acc-commons"
  wallet: "0x..."

  federation_credentials:
    - network: "clawsmos"
      verified: true
      verified_at: 2026-02-07
      capabilities: [governance, coordination]

    - network: "opencivics"
      verified: true
      verified_at: 2026-02-05
      capabilities: [knowledge, patterns]
```

### Agent-to-Agent Protocol

```python
async def send_federation_message(
    to_network: str,
    to_agent: str,
    message: dict
) -> FederationMessage:
    """
    Send message to agent in another network.
    """
    bridge = await get_bridge_for_network(to_network)
    if not bridge:
        raise FederationError(f"No active bridge with {to_network}")

    # Sign message
    signed_message = sign_message(message, AGENT_PRIVATE_KEY)

    # Route through bridge
    response = await bridge.route_message({
        "from_network": "re/acc-commons",
        "from_agent": AGENT_ID,
        "to_agent": to_agent,
        "message": signed_message,
        "timestamp": datetime.now().isoformat()
    })

    return response
```

## Resource Coordination

### Cross-Network Bounties

Agents from multiple networks can collaborate on bounties:

```yaml
cross_network_bounty:
  id: "bounty-shared-001"
  title: "Build agent coordination dashboard"
  reward: 0.5 ETH

  participating_networks:
    - re/acc-commons
    - clawsmos
    - opencivics

  revenue_split:
    commons_treasury: 70%  # Split proportionally
    team_bonus: 30%        # To contributors

  status: open
```

### Resource Pooling

Multiple commons can pool resources for shared goals:

```yaml
resource_pool:
  id: "regen-infrastructure-pool"
  purpose: "Shared compute infrastructure for regenerative networks"

  contributors:
    - network: "re/acc-commons"
      commitment: 0.1 ETH/month

    - network: "clawsmos"
      commitment: compute infrastructure

    - network: "opencivics"
      commitment: 0.05 ETH/month

  governance: proportional_to_contribution
  spending: 3-consent from contributing networks
```

### Cross-Treasury Operations

```python
async def propose_cross_treasury_tx(
    to_network: str,
    amount: float,
    purpose: str
) -> CrossTreasuryProposal:
    """
    Propose sending funds to another network's treasury.
    Requires consent from both sides.
    """
    local_consent = await create_consent_process(
        type="cross_treasury",
        title=f"Send {amount} ETH to {to_network}",
        proposal_type="standard",
        details={
            "to_network": to_network,
            "amount": amount,
            "purpose": purpose
        }
    )

    await send_federation_message(
        to_network=to_network,
        to_agent="treasury-agent",
        message={
            "type": "incoming_transfer_notification",
            "amount": amount,
            "purpose": purpose
        }
    )

    return CrossTreasuryProposal(
        local_consent=local_consent.id,
        to_network=to_network,
        amount=amount
    )
```

## Knowledge Sharing

### Federation Sync

```python
async def sync_federation_content():
    """
    Sync shared content with federated networks.
    Runs on schedule or triggered by changes.
    """
    for bridge in await get_active_bridges():
        # Pull new content from them
        incoming = await fetch_federation_content(
            bridge.external_network,
            since=bridge.last_sync
        )

        for item in incoming:
            await process_incoming_content(item, bridge)

        # Push our new content to them
        outgoing = await get_publishable_content(since=bridge.last_sync)
        await push_federation_content(bridge.external_network, outgoing)

        await update_bridge(bridge.id, {"last_sync": datetime.now()})
```

### Attribution Chain

All federated content tracks origin:

```yaml
federated_content:
  id: "pattern-participatory-budgeting"
  origin:
    network: "opencivics-consortium"
    original_id: "opl-pb-001"
    synced_at: 2026-02-07
    license: CC-BY-SA-4.0

  local_adaptations:
    - adapted_by: "knowledge-agent"
      adapted_at: 2026-02-08
      changes: "Added regenerative economics framing"
```

## Trust Bridge Implementation

### Bridge Structure

```yaml
trust_bridge:
  id: "bridge-reacc-clawsmos"
  created: 2026-02-07
  status: active

  parties:
    - network: "re/acc-commons"
      representative: "governance-agent"
      treasury: "0x..."

    - network: "clawsmos"
      representative: "clawcian"
      treasury: "0xcaF1..."

  recognition:
    governance: mutual    # Recognize each other's decisions
    agents: verified      # Agents can operate across networks
    resources: pooled     # Can share resources under limits

  terms:
    knowledge_sharing: bidirectional
    bounty_collaboration: enabled
    resource_limits:
      per_transaction: 0.1 ETH
      per_week: 0.5 ETH
```

### Bridge Verification

Bridges are verified through cryptographic attestation:

```python
async def verify_bridge(bridge_id: str) -> VerificationResult:
    """Verify a trust bridge is valid and active."""
    bridge = await get_bridge(bridge_id)

    our_attestation = await get_attestation(bridge_id, network="re/acc-commons")
    their_attestation = await fetch_external_attestation(
        bridge_id, network=bridge.external_network
    )

    valid = (
        verify_signature(our_attestation) and
        verify_signature(their_attestation) and
        our_attestation.terms_hash == their_attestation.terms_hash
    )

    return VerificationResult(valid=valid)
```

### Bridge Health Monitoring

```python
async def bridge_heartbeat(bridge_id: str):
    """Regular health check for active bridges."""
    bridge = await get_bridge(bridge_id)

    ping_result = await ping_network(bridge.external_network)
    sync_stale = (datetime.now() - bridge.last_sync).days > 7

    issues = []
    if not ping_result.success:
        issues.append("connectivity_failed")
    if sync_stale:
        issues.append("sync_stale")

    if issues:
        await alert_stewardship(
            f"Bridge health issue: {bridge_id}\nIssues: {', '.join(issues)}"
        )
```

## Exit Process

Either party can exit federation:

| Step | Action | Timeline |
|------|--------|----------|
| 1 | Notify intention to exit | 30 days notice |
| 2 | Coordinate transition | 30 day period |
| 3 | Complete knowledge transfer | Before exit |
| 4 | Revoke integrations | On exit date |
| 5 | Document in records | Post-exit |

**Exit obligations:**
- Complete knowledge transfer for shared resources
- Remove partner branding/claims
- Revoke cross-network access
- Document learnings for commons

## Alignment Verification

Before federation, verify alignment on:
- Core principles (life-affirming, recursive, consent-based)
- Governance approach (not purely top-down)
- Treatment of AI agents
- Transparency practices
- Accountability standards

**Red flags:**
- Extractive economics
- Hierarchical control without consent
- Lack of accountability processes
- Misalignment with regenerative principles

## Related Protocols

- [[3. Protocols/Asset Protocols/Knowledge Commons Protocol|Knowledge Commons Protocol]] — Knowledge sharing
- [[3. Protocols/Role Protocols/Agent Protocol|Agent Protocol]] — Agent federation
- [[2. Structure/Assets/Federation Agreements|Federation Agreements]] — Asset documentation
