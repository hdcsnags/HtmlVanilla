# Copy Variants Reference — Session 83

> **Purpose:** Research and exploration only. This file documents A/B headline and subheadline variants per persona for evaluation purposes. No variant here reflects or should be interpreted as a committed production copy choice in `maestro-poc.html`.
>
> **Dependencies:**
> - `docs/messaging-brief.md` — pillar definitions (Orchestration, Memory, Human Control)
> - `docs/ab-test-plan.md` — persona descriptions and segmentation logic

---

## Pillar Quick Reference

| Pillar | Core Idea |
|---|---|
| **Orchestration** | Coordinate multiple AI agents across complex, multi-step workflows without manual glue code |
| **Memory** | Persistent context that survives across sessions, agents, and tasks — no re-explaining |
| **Human Control** | Approve, pause, redirect, or override any agent action at any granularity |

---

## Persona A — DevOps Lead

**Profile summary (from ab-test-plan.md):** Hands-on technical decision-maker responsible for pipeline reliability, deployment velocity, and reducing toil. Evaluates tools on integration depth, observability, and operational overhead. Skeptical of black-box automation.

---

### Variant Set A1 — Pillar Focus: Orchestration

| # | Headline | Subheadline |
|---|---|---|
| A1-α | Ship multi-agent pipelines without writing the glue | Maestro orchestrates your AI workers the same way you orchestrate your services — declaratively, observably, reliably. |
| A1-β | Stop duct-taping your AI workflows together | Define once. Run anywhere. Maestro handles agent sequencing, retries, and handoffs so your pipeline stays clean. |
| A1-γ | AI agents that behave like well-deployed services | Orchestrate, monitor, and version your agent workflows with the same discipline you apply to the rest of your stack. |
| A1-δ | Your agents, properly wired | Maestro brings infrastructure-grade orchestration to multi-agent AI — no bespoke scripts, no brittle chains. |

---

### Variant Set A2 — Pillar Focus: Memory

| # | Headline | Subheadline |
|---|---|---|
| A2-α | Agents that remember what you've already told them | Persistent memory across runs means your pipeline doesn't restart from zero every time a new agent spins up. |
| A2-β | Context that survives across deploys, agents, and sessions | Maestro maintains a shared memory layer so every agent in your workflow starts informed, not blank. |
| A2-γ | Stop re-feeding context on every run | Build once. Maestro stores, retrieves, and scopes memory so your agents stay aligned across the entire pipeline lifecycle. |
| A2-δ | Stateful pipelines. No custom state management. | Maestro's memory layer gives each agent the context it needs — automatically — without bolting on a vector store yourself. |

---

### Variant Set A3 — Pillar Focus: Human Control

| # | Headline | Subheadline |
|---|---|---|
| A3-α | Every agent action is an approval gate if you want it to be | Set intervention points at any step. Pause, inspect, redirect, or override — without killing the run. |
| A3-β | Full observability. Full override. | Maestro exposes every agent decision with the controls to act on it — because black-box automation doesn't belong in production. |
| A3-γ | AI automation you can actually put in a runbook | Configurable checkpoints, audit logs, and human-in-the-loop hooks that fit your existing incident and change processes. |
| A3-δ | Don't give up control to get automation | Maestro lets you define exactly where humans stay in the loop — by agent, by task type, by risk threshold. |

---

## Persona B — CTO

**Profile summary (from ab-test-plan.md):** Strategic technology executive accountable for AI investment ROI, architectural coherence, and organizational risk. Evaluates tools on scalability, vendor posture, governance, and fit within a multi-year technology roadmap. Less concerned with implementation detail; highly concerned with trajectory and regret minimization.

---

### Variant Set B1 — Pillar Focus: Orchestration

| # | Headline | Subheadline |
|---|---|---|
| B1-α | The coordination layer your AI strategy is missing | Maestro turns isolated AI capabilities into orchestrated systems — so your investment compounds instead of fragmenting. |
| B1-β | Enterprise AI doesn't fail at the model level. It fails at coordination. | Maestro provides the orchestration infrastructure that makes multi-agent AI deployable, scalable, and maintainable at org scale. |
| B1-γ | From AI experiments to AI systems | Orchestration is the difference between a proof of concept and a production platform. Maestro is that layer. |
| B1-δ | One orchestration platform. Every AI initiative. | Standardize how your organization builds and runs AI workflows before every team invents their own approach. |

---

### Variant Set B2 — Pillar Focus: Memory

| # | Headline | Subheadline |
|---|---|---|
| B2-α | Institutional knowledge that your AI actually retains | Maestro's memory architecture means your agents accumulate organizational context — not just task context. |
| B2-β | AI that learns your business, not just your prompts | Persistent, scoped memory lets Maestro surface the right context to the right agent at the right moment — at scale. |
| B2-γ | The compounding advantage of AI memory | Every workflow run makes the next one smarter. Maestro's memory layer turns interactions into durable organizational intelligence. |
| B2-δ | Stop paying the context-rebuild tax | Maestro eliminates the hidden cost of re-establishing context across agents, sessions, and teams — making AI ROI real. |

---

### Variant Set B3 — Pillar Focus: Human Control

| # | Headline | Subheadline |
|---|---|---|
| B3-α | Governance built in. Not bolted on. | Maestro gives your organization configurable control over every AI agent action — with the audit trail your compliance team will ask for. |
| B3-β | Automate ambitiously. Control completely. | Set organizational policies for when AI acts autonomously and when humans decide — without slowing down what's working. |
| B3-γ | The oversight infrastructure AI deployment demands | Maestro puts approval workflows, intervention hooks, and accountability logging at the foundation of every AI workflow you ship. |
| B3-δ | AI autonomy on your terms | Define control boundaries at the org, team, or task level. Maestro enforces them — so your board can trust the system, not just the demo. |

---

## Persona C — ML Engineer

**Profile summary (from ab-test-plan.md):** Practitioner building, fine-tuning, and deploying models and agent systems. Evaluates tools on technical expressiveness, composability with existing ML infrastructure, minimal magic, and respect for the underlying primitives. Distrustful of abstraction that hides important behavior.

---

### Variant Set C1 — Pillar Focus: Orchestration

| # | Headline | Subheadline |
|---|---|---|
| C1-α | Orchestrate agents the way you'd architect a distributed system | Maestro gives you explicit control over agent graphs, execution order, and failure handling — no hidden scheduler behavior. |
| C1-β | Multi-agent orchestration without the framework lock-in | Compose agents from any model, any provider, any runtime. Maestro handles the wiring; you keep the flexibility. |
| C1-γ | Build agent workflows that behave exactly as designed | Declarative orchestration with deterministic execution semantics — so you can reason about your pipeline the way you reason about your code. |
| C1-δ | The orchestration primitive your agent stack has been missing | Explicit DAGs, typed handoffs, and composable agent interfaces. Maestro adds structure without adding magic. |

---

### Variant Set C2 — Pillar Focus: Memory

| # | Headline | Subheadline |
|---|---|---|
| C2-α | Persistent memory that behaves like a first-class system component | Maestro's memory layer is queryable, scopeable, and inspectable — not a black box attached to your prompt pipeline. |
| C2-β | Give your agents the context layer they deserve | Typed memory scopes, retrieval hooks, and TTL controls. Build agents that know what they need — without managing a vector store by hand. |
| C2-γ | Memory as infrastructure, not afterthought | Maestro integrates persistent context into the agent lifecycle so you stop hacking around statelessness and start building stateful systems. |
| C2-δ | Stop re-injecting context. Start building agents that remember. | Maestro's memory API gives you programmatic control over what agents retain, retrieve, and share across runs. |

---

### Variant Set C3 — Pillar Focus: Human Control

| # | Headline | Subheadline |
|---|---|---|
| C3-α | Interrupt, inspect, and redirect any agent at any point | Maestro exposes deterministic breakpoints and override hooks so you can debug agentic behavior the way you debug any other system. |
| C3-β | Human-in-the-loop that doesn't break your pipeline | Define intervention conditions programmatically. Maestro pauses, waits for input, then resumes — with full state preserved. |
| C3-γ | Build agents you can actually debug | Structured approval flows, step-level observability, and override primitives that plug into your existing toolchain. |
| C3-δ | Control surfaces for every layer of your agent stack | Per-agent, per-task, and per-action control policies — configurable in code, not locked behind a UI you can't script. |

---

## Notes for Research Use

- **Variant naming convention:** `[Persona letter][Pillar number]-[Greek letter]`. Example: `B2-γ` = CTO persona, Memory pillar, third variant.
- **No winner designation:** This file intentionally avoids indicating which variant is preferred, selected, or in use. Winner selection is handled in `docs/ab-test-plan.md` and reflected in test execution tooling.
- **Pillar coverage:** Each persona has three pillar sets (Orchestration, Memory, Human Control) with four variants each = 12 variants per persona, 36 variants total.
- **Iteration:** New variants should be appended within the appropriate set with the next available Greek letter. Retired variants should be struck through with a deprecation note rather than deleted, to preserve research history.
- **Do not backport:** Copy finalized for `maestro-poc.html` or any production surface should not be reverse-merged into this file as a "winner" — doing so defeats the research-neutral purpose of this document.
