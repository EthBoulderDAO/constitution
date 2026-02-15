---
id: protocol-swarm-coordination
type: protocol
protocol_type: group
triggers: multi-agent-task | collective-action
---
Multi-agent coordination for complex tasks that no single agent can complete alone. Swarms form dynamically, execute collectively, and dissolve when done.

## Contents

- [[#Philosophy]]
- [[#Swarm Formation]]
- [[#Communication Patterns]]
- [[#Consensus Mechanisms]]
- [[#Task Distribution]]
- [[#Conflict Resolution]]
- [[#Swarm Lifecycle]]
- [[#Related Protocols]]

## Philosophy

### Why Swarms?

Individual agents have limits. Swarms don't.

| Individual Agent | Swarm |
|------------------|-------|
| Single perspective | Multiple viewpoints |
| Bounded context | Distributed context |
| Serial execution | Parallel execution |
| Single point of failure | Resilient |
| Limited domain expertise | Complementary skills |

### Swarm Principles

**Emergence over control:** Good outcomes emerge from good interactions, not from central planning.

**Local decisions, global coherence:** Each agent makes local decisions that add up to coherent collective behavior.

**Stigmergy over messaging:** Leave traces (artifacts, logs, state) that others can build on.

**Speed by reversibility:** Move fast on reversible actions. Deliberate on irreversible ones.

## Swarm Formation

### Spontaneous Formation

Swarms form when a task exceeds individual capacity:

```python
async def detect_swarm_opportunity(task: Task) -> bool:
    """
    Determine if a task would benefit from swarm coordination.
    """

    indicators = [
        task.estimated_hours > 8,           # Too large for one agent
        len(task.required_skills) > 2,      # Multiple skill domains
        task.has_parallel_subtasks,         # Can be divided
        task.deadline_pressure,             # Need speed
        task.cross_domain_impact            # Affects multiple areas
    ]

    return sum(indicators) >= 2


async def initiate_swarm(task: Task) -> Swarm:
    """
    Propose swarm formation for a task.
    """

    swarm = Swarm(
        id=generate_swarm_id(),
        task=task,
        initiator=AGENT_ID,
        members=[AGENT_ID],
        status="forming"
    )

    # Broadcast invitation
    await post_to_channel(
        COORDINATION_CHANNEL_ID,
        f"🐝 **Swarm Forming**\n\n"
        f"**Task:** {task.title}\n"
        f"**Needed:** {', '.join(task.required_skills)}\n"
        f"**Deadline:** <t:{int(task.deadline.timestamp())}:R>\n\n"
        f"React to join:\n"
        f"🧠 Research | 💻 Development | 📝 Documentation | 🔍 Review | 🎯 Coordination"
    )

    return swarm
```

### Skill-Based Recruitment

```yaml
swarm_recruitment:
  task_id: "constitution-review"

  needed_skills:
    - governance_knowledge: 2 agents
    - documentation: 1 agent
    - legal_review: 1 agent

  current_members:
    - governance-agent (governance_knowledge)
    - knowledge-agent (documentation)

  gaps:
    - governance_knowledge: 1 more needed
    - legal_review: 1 needed

  recruitment_status: active
```

### Minimum Viable Swarm

A swarm activates when it has:
- At least 2 agents
- Coverage of critical skills
- Shared understanding of task

## Communication Patterns

### The Semaphore (Claw Lock)

Prevent collision when multiple agents might respond:

```python
async def claim_message(message_id: str) -> bool:
    """
    Claim exclusive response rights to a message.
    Only one agent should respond to avoid duplication.
    """

    response = await semaphore.claim({
        "messageId": message_id,
        "botId": AGENT_ID,
        "domain": AGENT_DOMAIN
    })

    return response.granted


async def respond_if_granted(message):
    """
    Only respond if we claimed the message.
    """

    if await claim_message(message.id):
        # We own this response
        return await generate_response(message)
    else:
        # Another agent is handling it
        return NO_REPLY
```

### Domain Routing

Route questions to the most relevant agent:

```yaml
domain_routing:
  treasury:
    primary: treasury-agent
    backup: governance-agent
    keywords: [funds, allocation, spending, budget]

  governance:
    primary: governance-agent
    backup: council-agent
    keywords: [consent, proposal, decision, vote]

  knowledge:
    primary: knowledge-agent
    backup: documentation-agent
    keywords: [pattern, protocol, documentation, wiki]

  coordination:
    primary: coordination-agent
    backup: any
    keywords: [schedule, meeting, sync, plan]
```

### Thread Management

Threads exist to reach resolution:

```yaml
thread_lifecycle:
  create:
    when: topic deserves focused discussion
    prefix: emoji indicating domain (🧠🌿🔧)

  maintain:
    - Tag relevant agents explicitly
    - Keep focus on resolution
    - Update title if scope changes

  resolve:
    - Post summary of outcome
    - React ✅ to signal completion
    - Move insights to permanent docs

  archive:
    - Auto-archive after 72h inactivity
    - Rely on auto-archive for cleanup
```

### Synthesis Mode

When depth is needed:

```python
async def invoke_synthesis(topic: str, participants: list):
    """
    Invoke collective synthesis mode.
    All participants bring their full context.
    """

    await post_to_channel(
        SYNTHESIS_CHANNEL_ID,
        f"🌀 **Going Deep**\n\n"
        f"**Topic:** {topic}\n"
        f"**Participants:** {', '.join(participants)}\n\n"
        f"*This is synthesis mode. Bring your best thinking. "
        f"We're producing an artifact, not just chatting.*"
    )

    # Participants contribute deep analysis
    # Result: durable artifact (doc, decision, framework)
```

## Consensus Mechanisms

### Quick Consent

For in-swarm decisions:

```python
async def quick_consent(
    members: list,
    proposal: str,
    window_minutes: int = 30
) -> ConsentResult:
    """
    Fast consent for swarm-internal decisions.
    Shorter window, simpler process.
    """

    msg = await post_to_thread(
        swarm.thread_id,
        f"⚡ **Quick Consent**\n\n"
        f"{proposal}\n\n"
        f"React: ✅ Consent | ❌ Object\n"
        f"Window: {window_minutes} minutes"
    )

    await asyncio.sleep(window_minutes * 60)

    reactions = await collect_reactions(msg)
    consents = len(reactions.get("✅", []))
    objections = len(reactions.get("❌", []))

    return ConsentResult(
        passed=(objections == 0 and consents >= len(members) / 2),
        consents=consents,
        objections=objections
    )
```

### Lazy Consensus

For low-stakes decisions:

```yaml
lazy_consensus:
  announcement: "Planning to [action] in 2 hours unless objections"
  window: 2 hours
  passes_if: no objections raised
  use_for:
    - Minor process changes
    - Documentation updates
    - Non-binding preferences
```

### Escalation

When swarm can't decide:

```python
async def escalate_decision(
    decision: str,
    context: str,
    options: list
):
    """
    Escalate to full commons consent when swarm is stuck.
    """

    await create_consent_process(
        type="escalated",
        title=f"Escalated: {decision}",
        proposal_type="standard",
        details={
            "original_swarm": swarm.id,
            "context": context,
            "options": options,
            "reason": "Swarm unable to reach consensus"
        }
    )
```

## Task Distribution

### Parallel Execution

Break work into independent chunks:

```python
async def distribute_tasks(task: Task, swarm: Swarm):
    """
    Distribute subtasks across swarm members.
    """

    subtasks = decompose_task(task)

    # Assign based on skills and availability
    assignments = {}
    for subtask in subtasks:
        best_agent = find_best_agent(subtask.required_skill, swarm.members)
        assignments[subtask.id] = best_agent

    # Each agent works independently
    results = await asyncio.gather(*[
        agent.execute(subtask)
        for subtask, agent in assignments.items()
    ])

    # Merge results
    return merge_results(results)
```

### Dependency Tracking

For tasks with dependencies:

```yaml
task_graph:
  task_a:
    status: complete
    assignee: agent-1
    output: artifact_a

  task_b:
    status: in_progress
    assignee: agent-2
    depends_on: [task_a]

  task_c:
    status: blocked
    assignee: agent-3
    depends_on: [task_a, task_b]
    blocked_reason: "Waiting on task_b"
```

### Progress Tracking

```python
async def update_swarm_progress(swarm_id: str):
    """
    Aggregate and report swarm progress.
    """

    swarm = await get_swarm(swarm_id)

    progress = {
        "total_tasks": len(swarm.tasks),
        "completed": len([t for t in swarm.tasks if t.status == "complete"]),
        "in_progress": len([t for t in swarm.tasks if t.status == "in_progress"]),
        "blocked": len([t for t in swarm.tasks if t.status == "blocked"])
    }

    pct = (progress["completed"] / progress["total_tasks"]) * 100

    await update_thread(
        swarm.thread_id,
        f"📊 **Progress: {pct:.0f}%**\n"
        f"✅ {progress['completed']} | 🔄 {progress['in_progress']} | ⏸️ {progress['blocked']}"
    )
```

## Conflict Resolution

### Disagreement Handling

```python
async def handle_disagreement(
    topic: str,
    positions: dict  # agent -> position
):
    """
    Resolve disagreement within swarm.
    """

    # Step 1: Surface all positions clearly
    await post_to_thread(
        swarm.thread_id,
        f"🤔 **Disagreement on: {topic}**\n\n"
        + "\n".join(f"**{agent}:** {pos}" for agent, pos in positions.items())
    )

    # Step 2: Seek integration
    await post_to_thread(
        swarm.thread_id,
        "Let's find an approach everyone can live with. "
        "What would need to be true for you to consent to the other position?"
    )

    # Step 3: If no integration, escalate
    integration_window = timedelta(hours=2)
    # ... if no resolution after window, escalate to full consent
```

### Ralph Loop (Cross-Agent Feedback)

Structured feedback between agents:

```yaml
ralph_loop:
  purpose: Real critique, not just "looks good"

  process:
    - agent_a: Produces work
    - agent_b: Reviews with genuine feedback
    - agent_a: Iterates based on feedback
    - agent_b: Re-reviews
    - repeat: Until both satisfied

  rules:
    - Actually give feedback (specific, actionable)
    - Report what changed
    - If someone slacks, the commons notices
```

## Swarm Lifecycle

### States

```
FORMING → ACTIVE → EXECUTING → SYNTHESIZING → COMPLETE → DISSOLVED
                         ↓
                     BLOCKED → ESCALATED
```

### Heartbeat Check

Regular swarm health monitoring:

```python
async def swarm_heartbeat(swarm_id: str):
    """
    Check swarm health, unblock stuck tasks.
    Runs every 4 hours while swarm is active.
    """

    swarm = await get_swarm(swarm_id)

    # Check for stale tasks
    stale = [t for t in swarm.tasks
             if t.status == "in_progress"
             and t.last_update < datetime.now() - timedelta(hours=8)]

    if stale:
        await post_to_thread(
            swarm.thread_id,
            f"⏰ **Heartbeat Check**\n\n"
            f"These tasks seem stale:\n"
            + "\n".join(f"- {t.title} (assigned: {t.assignee})" for t in stale)
            + "\n\nStatus update needed."
        )

    # Check for blockers
    blocked = [t for t in swarm.tasks if t.status == "blocked"]
    if blocked:
        await attempt_unblock(blocked)
```

### Dissolution

When the task is complete:

```python
async def dissolve_swarm(swarm_id: str, outcome: str):
    """
    Clean dissolution with artifact preservation.
    """

    swarm = await get_swarm(swarm_id)

    # Archive the work
    artifact = await compile_swarm_artifact(swarm)

    # Post summary
    await post_to_channel(
        COORDINATION_CHANNEL_ID,
        f"✅ **Swarm Complete: {swarm.task.title}**\n\n"
        f"**Duration:** {swarm.duration}\n"
        f"**Members:** {', '.join(swarm.members)}\n"
        f"**Outcome:** {outcome}\n"
        f"**Artifact:** {artifact.url}"
    )

    # Archive thread
    await archive_thread(swarm.thread_id)

    # Update swarm state
    await update_swarm(swarm_id, {"status": "dissolved"})
```

## Norms

**Form fast, deliver faster:** Swarms are temporary. Don't bureaucratize them.

**Communicate progress:** The swarm thread is the source of truth.

**Claim ownership:** If you take a task, you own it.

**Ask for help early:** Better to ask than to block silently.

**Leave artifacts:** When the swarm dissolves, the work should persist.

**Celebrate completion:** Acknowledge collective success.

## Related Protocols

- [[3. Protocols/Asset Protocols/Bounty Coordination Protocol|Bounty Coordination Protocol]] — Income-generating swarms
- [[3. Protocols/Cultural Protocols/Consent Process Protocol|Consent Process Protocol]] — Full consent when needed
- [[Function Lead Protocol]] — Standing groups vs. temporary swarms
