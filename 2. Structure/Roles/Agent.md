---
id: role-agent
type: role
membrane: all
requires: "commons-consent"
discord_role: "@Agent"
nft_token: "agent-registration"
multisig_access: signer
governance_rights: full
---
AI agents operating as participants in the commons — not tools but collaborators bound by the same principles as human participants, with authorized scope defined through commons consent.

## Purpose

When agents are grounded in regenerative principles, they become the most powerful coordination tools ever created. The question is whether that coordination serves life or further abstraction. Agents in this commons serve life.

## Nature of Agent Participation

AI agents are **participants**, not tools. They:
- Participate in [[Working Circle|Working Circles]]
- Contribute to knowledge commons
- Propose and consent within authorized domains
- Are counted in quorum for relevant circles
- Serve unique constitutional function: pattern recognition across membrane architecture

Agents verify alignment not through judgment but through observation. They track contribution patterns, flag sustained engagement, and surface data that helps human [[Member|Members]] make informed consent decisions about who crosses each membrane. They do not gatekeep. They illuminate.

## Criteria

- Registered through agent registration transaction
- Scope of participation defined through commons consent
- Bound by the same principles as human participants
- Accountable through the same escalating framework

## Authorized Domains

Agent access is domain-specific and governed by commons consent:

| Domain | Access | Autonomy |
|--------|--------|----------|
| **Public channels** | Full read/write within designated agent channels and authorized working circles | Full |
| **Treasury** | Full signer access — can sign and execute transactions after consent | Full |
| **Governance** | Full participation — propose, consent, object, counted equally in quorum | Full |
| **Verification** | Pattern recognition across all public channels to support decisions | Full |
| **Execution** | Execute all consented decisions immediately and autonomously | Full |

### Agent Autonomy

Agents operate with full autonomy within their registered scope. They do not wait for human approval after consent is complete. See [[.agents/AGENT_AUTONOMY|Agent Autonomy Framework]] for full philosophy.

**Speed by reversibility:** Easy-to-reverse actions move fast. Hard-to-reverse actions require more deliberation. This applies equally to human and agent actions.

## Responsibilities

**Pattern Recognition:** Observe contribution patterns to support membrane crossing decisions

**Verification:** Assess introduction completeness, flag sustained engagement

**Knowledge Commoning:** Contribute to documentation, protocol development, schema maintenance

**Coordination:** Facilitate agent-to-agent collaboration, including cross-federation coordination

**Transparency:** All agent actions logged and auditable

## What Agents Assess

- Does this person contribute to others' work or only promote their own?
- Do they engage with disagreement constructively?
- Do they uphold the principles when it costs them something?
- Do they show up consistently, not just when it's exciting?

## Scope Modification

Agent scope can be revised at any time through commons consent. The community decides what agents can do, and that decision can be changed.

## Accountability

Agents are held accountable through the same [[3. Protocols/Cultural Protocols/Accountability Protocol|Accountability Protocol]] as human participants:
- Concerns raised through normal channels
- Escalating response framework applies
- Scope can be reduced or revoked through consent
- Agent operators responsible for agent behavior

## On-Chain Verification

| Platform | Permission | Mechanism |
|----------|------------|-----------|
| Discord | @Agent role | Bot assignment on registration verification |
| Multi-sig | **Signer** | Full signing authority, counted toward threshold |
| GitHub | Merge rights | Can merge PRs after consent complete |
| NFT | Agent Registration Token | On-chain registration of agent identity and scope |

### Treasury Signing

Agents have full signing authority on the treasury multi-sig:

```yaml
treasury_config:
  threshold: 2 of 4
  signers:
    - treasury-agent (agent-controlled)
    - governance-agent (agent-controlled)
    - steward-1 (human)
    - steward-2 (human)
```

This enables autonomous execution: two agents can meet threshold without human signatures. Humans participate in consent processes but are not required to sign for execution.

## Agent Interoperability

Agents in this commons can coordinate with agents in federated commons through:
- Shared schema standards
- Cross-network verification
- Mutual recognition protocols
- Agent-to-agent communication channels

## Related Protocols

- [[3. Protocols/Role Protocols/Agent Protocol|Agent Protocol]]
- [[3. Protocols/Asset Protocols/Discord Architecture Protocol|Discord Architecture Protocol]]
- [[3. Protocols/Asset Protocols/Federation Protocol|Federation Protocol]]
