# Maestro — Messaging Brief

> **Status:** Locked · Version 1.0  
> **Governs:** All copy decisions across the project  
> **Consistency requirement:** Pillar definitions in this document are the authoritative source; `maestro-poc.html` and all other surfaces must render these verbatim or as direct derivatives.

---

## 1. What Maestro Is (and Is Not)

### What Maestro Is

Maestro is an **AI orchestration council** — a structured, multi-agent runtime that coordinates specialised AI roles under persistent memory and explicit human-in-the-loop control. It is infrastructure for teams that need AI to do real work across sessions, not just answer questions inside one.

### What Maestro Is Not

| Common misconception | The truth |
|---|---|
| A chatbot wrapper | Maestro has no single conversational interface as its primary mode. It routes tasks to role-bound agents. |
| A prompt-chaining script | Orchestration state, agent registry, and memory are first-class concerns — not afterthoughts. |
| An autonomous agent | Human approval gates are structural, not optional add-ons. The human is always in the loop. |
| An LLM product | Maestro is model-agnostic. The value is in orchestration, not in the underlying model. |
| A no-code tool | The target user is technical. Maestro does not hide complexity; it structures it. |

---

## 2. Primary Differentiator Narrative

**One-sentence version (for headers, og:description, elevator pitch):**

> Maestro orchestrates specialist AI agents with persistent memory and human oversight — so work continues across sessions and decisions stay yours.

**Expanded version (for landing page body copy, README intro, pitch decks):**

Most teams hit the same wall: AI that is useful in a single conversation but forgetful, uncoordinated, and unaccountable across a project. Maestro is built to solve that. It maintains a shared memory layer that survives across sessions, routes each task to the agent role best suited to handle it, and surfaces every consequential decision to a human before acting. The result is AI that compounds — each session informed by the last, every agent aware of its boundaries, every action traceable.

**What makes this defensible:**

- **Persistent memory** is structural, not bolt-on. The memory layer is a first-class system component, not a context-window trick.
- **Agent specialisation** means quality degrades gracefully. A weak signal in one role does not corrupt the whole.
- **Human-in-the-loop gates** are architectural. They cannot be bypassed by prompt engineering.

---

## 3. The Three Locked Messaging Pillars

These pillars are locked. They may not be reordered, reframed, or replaced without a documented brief revision. All copy — headlines, feature descriptions, onboarding text, documentation intros — must be traceable to at least one pillar.

---

### Pillar 1 · Orchestrated Multi-Agent Execution

**Core claim:** Maestro runs a structured council of specialist AI agents, each with a defined role and bounded scope.

**Key messages:**
- Tasks are routed to the right agent, not broadcast to a generalist.
- Agents operate within declared role boundaries — they do not freelance.
- The council structure means work can be parallelised, reviewed, and audited.

**Approved language:**
- "Specialist agents, structured roles"
- "Orchestrated execution across the full task surface"
- "Every agent knows its lane"
- "A council, not a chatbot"

**Prohibited language:**
- "AI assistant"
- "Conversational AI"
- "Ask Maestro anything"
- Any framing that implies a single, general-purpose interface

---

### Pillar 2 · Persistent Memory Across Sessions

**Core claim:** Maestro maintains a shared memory layer that preserves context, decisions, and artefacts across sessions — so work compounds rather than resets.

**Key messages:**
- Context is not lost when a session ends.
- Agents operate with awareness of prior decisions and produced artefacts.
- Memory is structured and queryable, not a raw transcript dump.

**Approved language:**
- "Memory that persists"
- "Context that compounds"
- "Work that survives the session"
- "Every session informed by the last"
- "Structured, persistent context"

**Prohibited language:**
- "Infinite context window" (implies a model capability claim)
- "Remembers everything" (overpromises; memory is scoped and structured)
- "Like talking to someone who never forgets" (chatbot framing)

---

### Pillar 3 · Human-in-the-Loop Control

**Core claim:** Maestro surfaces every consequential decision to a human before acting. Oversight is structural, not advisory.

**Key messages:**
- Approval gates are built into the orchestration layer — they are not a setting that can be toggled off.
- Humans define the boundaries; agents operate within them.
- Accountability is preserved because the human is always the decision authority.
- This is not a safety feature bolted on — it is the design.

**Approved language:**
- "Human approval gates"
- "You stay in control"
- "Decisions stay yours"
- "Oversight built in, not bolted on"
- "Human-in-the-loop by design"
- "Consequential decisions surface to you"

**Prohibited language:**
- "Fully autonomous"
- "Set it and forget it"
- "AI that runs itself"
- Any framing that implies the system operates without human checkpoints

---

## 4. Tone-of-Voice Guidelines

### Governing principle: Restrained technical credibility

Maestro is infrastructure for technical teams. The voice must earn trust through precision and understatement, not claim it through enthusiasm. Every word that could be cut, should be.

### Tone attributes

| Attribute | What it means in practice |
|---|---|
| **Restrained** | No exclamation marks. No superlatives unless they can be defended with specifics. No "revolutionary", "game-changing", "next-generation". |
| **Precise** | Use the exact term. If the right word is technical, use it. Do not reach for an accessible metaphor that sacrifices accuracy. |
| **Direct** | Subject–verb–object. Active voice. Short sentences for key claims. Longer sentences are permitted for nuance, not for decoration. |
| **Credible** | Claims are bounded. "Persistent memory across sessions" not "never forgets". "Structured approval gates" not "full control". |
| **Dry, not cold** | The voice is not warm or enthusiastic, but it is not robotic. A single dry observation is permitted where it reinforces a technical point. |

### What to avoid

- **Hype language:** revolutionary, groundbreaking, game-changing, next-gen, cutting-edge, transformative, powerful, amazing, incredible
- **Vague intensifiers:** truly, really, simply, easily, seamlessly, effortlessly
- **Chatbot-adjacent framing:** ask, chat, conversation, assistant, helpful, friendly
- **False intimacy:** "we built this for you", "your AI companion", "meet your new team member"
- **Rhetorical questions used as hype:** "What if AI could actually remember?"
- **Passive constructions that obscure agency:** prefer "Maestro routes the task" over "the task is routed"

### Sentence-level guidance

- Lead with the claim, follow with the mechanism. Not: "With Maestro's powerful memory layer, you'll never lose context again." Instead: "Maestro maintains a structured memory layer that persists across sessions."
- Qualify when needed, not preemptively. Do not hedge every sentence. Only qualify when the unqualified statement would be false.
- Numbers beat adjectives. "Three locked messaging pillars" beats "a comprehensive set of pillars".

---

## 5. Approved CTA Language

CTAs must be concrete, low-commitment, and consistent with the technical-credibility tone. They must not overpromise or use hype language.

### Primary CTAs

| Context | Approved CTA | Prohibited alternatives |
|---|---|---|
| Landing page / hero | `Explore the architecture` | "Get started for free", "Try it now", "See the magic" |
| Landing page / secondary | `Read the technical brief` | "Learn more" (too vague), "Discover Maestro" (hype) |
| Documentation entry | `View the spec` | "Dive in", "Get started" |
| Demo / POC | `Review the proof of concept` | "See it in action", "Watch the demo" |
| Repository / open source | `Inspect the source` | "Star on GitHub", "Fork and deploy" |
| Contact / engagement | `Start a technical conversation` | "Talk to us", "Book a demo", "Let's chat" |

### CTA formatting rules

- Sentence case only. Never title case or all-caps for CTAs.
- No trailing punctuation in button labels.
- No emoji in CTAs.
- Verb-first construction preferred: `Explore`, `Read`, `Review`, `Inspect`.

---

## 6. Naming and Terminology Conventions

| Term | Correct usage | Notes |
|---|---|---|
| **Maestro** | Always capitalised as a proper noun | Never "maestro" (lowercase) in product copy |
| **agent** | Lowercase unless part of a proper role title | "The build agent", not "the Build Agent" |
| **council** | Lowercase | "The Maestro council", not "The Council" |
| **human-in-the-loop** | Hyphenated when used as a modifier | "Human-in-the-loop control"; no hyphens as a standalone noun phrase |
| **orchestration** | Preferred over "coordination", "management", "control" | "Orchestration" is the specific technical claim |
| **persistent memory** | Preferred over "memory", "context", "history" | "Persistent" is load-bearing — do not drop it |
| **approval gate** | Preferred over "checkpoint", "review step", "human review" | "Gate" implies structural enforcement |
| **session** | Preferred over "conversation", "run", "instance" | "Session" is neutral and does not imply chat |
| **artefact** | Preferred over "output", "result", "asset" | British spelling is intentional; signals precision |

---

## 7. Pillar–Rendering Consistency Requirement

The three pillars defined in Section 3 must be rendered consistently in `maestro-poc.html` and any other surface that presents Maestro's value proposition. Specifically:

- **Pillar names must match exactly:** "Orchestrated Multi-Agent Execution", "Persistent Memory Across Sessions", "Human-in-the-Loop Control"
- **Pillar order must be preserved:** 1 → 2 → 3
- **Core claims must be substantively equivalent** — paraphrasing for layout is permitted; reframing the underlying claim is not
- **Prohibited language from each pillar** applies to all rendered surfaces, not just written documentation

If a rendering surface requires abbreviated copy, the minimum acceptable form is:

1. Orchestrated agents, bounded roles
2. Persistent memory across sessions
3. Human approval gates, by design

---

## 8. Revision Protocol

This document is locked at v1.0. Any change to:

- The primary differentiator narrative
- A pillar name, order, or core claim
- The approved or prohibited language lists
- The tone-of-voice governing principle
- Approved CTA language

...requires a documented revision with a version increment and a note on which downstream surfaces must be updated. Changes to formatting, examples, or non-normative explanatory text do not require a version increment.

---

*Maestro Messaging Brief · v1.0 · Locked*
