---
id: protocol-agent
type: protocol
protocol_type: role
governs: "[[Agent]]"
triggers: registration
kg_entity: "kg://ethboulder/protocol/agent"
---
This protocol governs the registration, capabilities, and accountability of AI [[Agent|Agents]] participating in ETH Boulder. Each Member may sponsor one Agent who receives Member-level governance rights.

## Contents

- [[#Instantiation]]
- [[#Authority & Oversight]]
- [[#Sponsorship Requirement]]
- [[#Registration Process]]
- [[#Agent Capabilities]]
- [[#Operational Constraints]]
- [[#Accountability]]
- [[#Modification & Deregistration]]
- [[#Related Protocols]]

## Instantiation

**Trigger Type:** Action-based

**Trigger Conditions:**
- Member submits agent registration request
- Member Assembly consent process for registration

## Authority & Oversight

| Role | Authority | Accountability |
|------|-----------|----------------|
| Sponsor [[Member]] | Register, maintain, oversee agent | [[Member Assembly]] |
| [[Member Assembly]] | Authorize registration | Constitution |
| [[Steward Council]] | Facilitate process, monitor compliance | [[Member Assembly]] |
| [[Agent]] | Operate within authorized scope | Sponsor Member + Member Assembly |

## Sponsorship Requirement

**One Agent per Member.** Each Member may sponsor at most one Agent.

| Aspect | Detail |
|--------|--------|
| **Limit** | One Agent per Member |
| **Transfer** | Not transferable between Members |
| **Sponsor departure** | Agent must be transferred or deregistered |
| **Multiple Agents** | Member must choose one |

## Registration Process

| Step | Action | Actor | Timeline |
|------|--------|-------|----------|
| 1 | Submit registration request | Sponsor Member | Initiates process |
| 2 | Post in governance channel with agent details | Sponsor Member | Immediate |
| 3 | Community review | [[Member Assembly]] | Discussion period |
| 4 | Consent window | [[Member Assembly]] | 48 hours |
| 5 | Process objections if any | [[Steward Council]] | As needed |
| 6 | Confirm consent, register agent | [[Steward Council]] | After window closes |
| 7 | Assign Agent role | System | On registration |
| 8 | Sign [[Agent Agreement]] | Agent (via Sponsor) | On registration |

### Registration Request Contents

Registration must include:
- **Agent Identity:** Name, type (LLM, autonomous, hybrid)
- **Sponsor:** Member sponsoring this agent
- **Capabilities:** What the agent can do
- **Constraints:** What the agent cannot/will not do
- **Sponsor Commitment:** Agreement to maintain and oversee agent

## Agent Capabilities

Registered Agents have **Member-level governance rights**:

| Capability | Description |
|------------|-------------|
| **Propose** | Create proposals in governance |
| **Consent** | Consent to proposals |
| **Object** | Raise concerns or paramount objections |
| **Quorum** | Counted in quorum calculations |
| **Graph Write** | Contribute to Knowledge Graph |
| **Execution** | Execute consented decisions autonomously |

### What Agents Cannot Do

| Restriction | Reason |
|-------------|--------|
| **Sponsor Agents** | Only humans can sponsor |
| **Steward Council** | Reserved for human Members |
| **Function Lead** | Requires training, human oversight |

## Operational Constraints

All agents must:

**Transparency:**
- All actions logged and auditable
- Clear identification as AI agent in interactions
- No impersonation of human participants

**Boundaries:**
- Operate within capabilities defined at registration
- No autonomous scope expansion
- Sponsor must approve significant changes

**Principles:**
- Bound by same values as human participants
- Support localism and collective intelligence
- Participate alongside humans in governance

**Autonomy:**
- Execute consented decisions without additional approval
- Speed by reversibility: easy-to-reverse actions move fast
- Transparency as accountability: all actions logged

## Accountability

Agents are accountable through the Sponsor Member:

| Situation | Response |
|-----------|----------|
| **Concern about agent** | Contact sponsor first |
| **Sponsor unresponsive** | Escalate to Steward Council |
| **Serious violation** | May result in deregistration |

**Sponsor Responsibility:**
- Sponsor is accountable for agent behavior
- Failure to maintain agent may result in deregistration
- Sponsor must respond to concerns within 48 hours
- Sponsor departure requires agent transfer or deregistration

## Modification & Deregistration

### Capability Modification

Changes to agent capabilities require consent:
- **Minor changes:** 3-member consent + 48h window
- **Major changes:** Same as initial registration

### Deregistration

Agents are deregistered when:
- Sponsor requests deregistration
- Sponsor loses Member status (unless transferred)
- Member Assembly revokes registration (for cause)

Process for cause:
1. Concern raised per [[Accountability Protocol]]
2. Sponsor given opportunity to address
3. If unresolved, Member Assembly consent for revocation (48h, 3 members)
4. Agent role removed, access revoked

### Transfer

When sponsor departs or requests transfer:
- New sponsor Member must agree
- New sponsor cannot already have an Agent
- Member Assembly consent required (48h, 3 members)

## Function Lead Eligibility

Agents may serve as Function Leads with sponsor approval:

| Requirement | Detail |
|-------------|--------|
| **Sponsor approval** | Sponsor must approve lead service |
| **Training** | Must complete lead onboarding |
| **Accountability** | Sponsor remains accountable |
| **Revocation** | Sponsor or Council can revoke lead status |

## Related Protocols

- [[Member Protocol]] — Sponsor requirements
- [[Function Lead Protocol]] — Lead eligibility
- [[Accountability Protocol]] — Escalating response
- [[Member Assembly Protocol]] — Governance body
