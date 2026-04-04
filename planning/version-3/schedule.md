# AI Engineer Europe 2026 - Personal Schedule v3

**Conference:** AI Engineer Europe 2026
**Dates:** April 8-10, 2026
**Venue:** Queen Elizabeth II Centre, London, UK
**Website:** https://ai.engineer/europe

## What Changed from v2

v2 optimized for context engineering (skills, knowledge curation) with harness as secondary. v3 rebalances: **harness engineering is the primary lens**, context engineering serves the harness. The user's goal is to understand and implement agent harnesses -- the full system that wraps around a model to make it reliable.

Key shifts:
- **Day 1 flipped**: v2 started with skills workshops. v3 starts with harness architecture and implementation workshops. Skills are still covered but as the "guides layer" of the harness, not as a standalone concern.
- **Day 2 deepened**: v2 hopped between Context and Harness tracks. v3 commits to the Harness Engineering track as the spine, with targeted context engineering sessions where they directly serve harness understanding.
- **Implementation framing**: every session is mapped to a harness component layer, so you know exactly what you're building.
- **Pre-reading and post-conference plan** added: the conference is one step in a larger learning arc.

## The Harness Mental Model

From the foundational sources (OpenAI, Anthropic, Fowler), a harness has six functional layers. This schedule is organized to cover all six:

```
Agent = Model + Harness

The Harness:
  1. GUIDES (feedforward)     -- skills, CLAUDE.md, tool definitions, progressive context
  2. SENSORS (feedback)       -- tests, linters, type checkers, AI code review
  3. EXECUTION INFRA          -- sandboxed execution, filesystem, git, browser automation
  4. MEMORY & STATE           -- progress files, git history, session initialization
  5. ORCHESTRATION            -- sub-agents, agent-to-agent review, lifecycle hooks
  6. VERIFICATION & GUARDRAILS -- structural tests, safety filters, observability
```

## Pre-Conference Reading (Before April 8)

Read in this order. Each builds on the previous:

| # | Source | Time | What You Get |
|---|--------|------|-------------|
| 1 | [Mitchell Hashimoto - My AI Adoption Journey](https://mitchellh.com/writing/my-ai-adoption-journey) | 20 min | The origin story. "Engineer the harness" as a practice. Every agent mistake becomes an environmental fix. |
| 2 | [OpenAI - Harness Engineering](https://openai.com/index/harness-engineering/) | 30 min | The discipline defined. How a small team shipped ~1M LoC with zero human-written code. Codex harness principles. |
| 3 | [Anthropic - Effective Harnesses for Long-Running Agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents) | 25 min | Bridging context windows. Progress files, incremental work, clean-state discipline. |
| 4 | [Martin Fowler - Harness Engineering for Coding Agent Users](https://martinfowler.com/articles/exploring-gen-ai/harness-engineering.html) | 30 min | Agent = Model + Harness. The guides/sensors framework. Inner vs outer harness. |
| 5 | [Vercel - We Removed 80% of Our Agent's Tools](https://vercel.com/blog/we-removed-80-percent-of-our-agents-tools) | 15 min | The minimalist case. 80% -> 100% accuracy by removing tools. The bitter lesson applied. |
| 6 | [Manus - Context Engineering for AI Agents](https://manus.im/blog/Context-Engineering-for-AI-Agents-Lessons-from-Building-Manus) | 25 min | 5 framework rebuilds. KV-cache optimization, attention recitation, logit masking. |

These six give you the theoretical foundation. Ryan Lopopolo's Day 2 keynote will assume familiarity with the OpenAI post (source #2) -- he's the Codex team lead who wrote it.

---

## Day 1 - April 8 (Workshops): Build a Harness

Workshop day. Four time slots. The recommended schedule constructs a harness from the ground up.

### Recommended Schedule

| Time | Workshop | Room | Harness Layer |
|---|---|---|---|
| 9:00-10:20am | **How to Build Agents That Run for Hours (Without Losing the Plot)** | St. James | Orchestration, Memory, Sensors |
| 10:40am-12:00pm | **Make your own event-sourced agent harness in 60 seconds** | Shelley | Execution Infra, Orchestration, Memory |
| *Lunch* | | | |
| 1:00-3:00pm | **Ralph Loops: Build Dumb AI Loops That Ship** | Abbey | Orchestration, Sensors |
| 3:30-5:30pm | **Ship Real Agents: Hands-On Evals for Agentic Applications** | Westminster | Sensors, Verification |

### Why This Combination

**Morning arc: Harness architecture and implementation.**

The 9:00am workshop (Ash Prabaker, Andrew Wilson) teaches you the operational patterns of a long-running agent harness:
- Why self-evaluation is a trap and adversarial evaluator agents work better (Sensors)
- Why context compaction doesn't cure coherence drift but structured handoffs do (Memory)
- How to decompose work into testable sprint contracts (Orchestration)
- How to read traces as your primary debugging loop (Verification)
- Which parts of your harness to delete when the next model drops (Bitter Lesson)

The 10:40am workshop (Misha Kaletsky, Jonas Templestein) is the most implementation-focused harness session at the conference. You build an actual Effect-TS agent harness where everything is an event:
- Multiple LLM requests per turn with parallel tool execution (Execution Infra)
- Full replay and time-travel debugging (Memory)
- Event sourcing for agent state -- audit trails, undo/redo, branching (Orchestration)
- Agent plugins loaded and hot-swapped at runtime (Execution Infra)

By lunch, you've seen harness architecture (what layers exist and why) AND built a working event-sourced harness. This is the theoretical + practical foundation for the rest of the conference.

**Afternoon arc: Feedback loops and verification.**

The 1:00pm "Ralph Loops" workshop (Chris Parsons) is deceptively simple but deeply relevant:
- Build a single agent loop that processes one ticket at a time, evaluates its own output, and improves on the next run
- Build a synthetic feedback loop for local testing without production data
- Build a self-improving cycle where output quality increases per run without prompt changes
- The core insight: dumb loops beat clever workflows. This is the Vercel lesson applied to practice.

The 3:30pm evals workshop (Laurie Voss) builds the verification layer:
- Complete evaluation pipeline from scratch using Claude Agent SDK
- Three types of evaluators: deterministic code checks, LLM-as-judge, custom rubrics
- Validates your judges against human labels (because an untested eval is "being wrong at scale")
- Impact hierarchy for prioritizing fixes, Swiss Cheese model for layering defenses
- Leaves you with a working notebook and repeatable process

**Day 1 builds harness layers 2, 3, 4, 5, and 6.** Layer 1 (Guides -- skills, CLAUDE.md) gets covered on Days 2-3.

### Alternatives Per Slot

| Time | Alternative | Room | Trade-off |
|---|---|---|---|
| 9:00-10:20am | **Skill Issue: Agents Actually Good at Supabase** | Abbey | Swaps harness architecture for skills writing + eval harness (Braintrust). Pick if you want to start with Layer 1 (Guides) instead of layers 4-5. |
| 9:00-10:20am | **Agentic Search for Context Engineering** | Wordsworth | Context retrieval focus. Pick only if retrieval is your main gap. |
| 10:40am-12:00pm | **Skills at Scale** | Abbey | Portable skills across Claude Code, Cursor, Codex. Layer 1 focus. Good if you want skills depth early. |
| 10:40am-12:00pm | **Playground in Prod** (Samuel Colvin) | Westminster | Live agent optimization with Pydantic AI + GEPA auto-evolution. Production harness tuning. Strong alternative if you use Python/Pydantic AI. |
| 1:00-3:00pm | **Mergeable by default: Context engine** (Peter Werry) | Wordsworth | Context engine for mergeable code. Layer 1 + real production lessons. Pick if context delivery is your bigger gap than orchestration. |
| 1:00-3:00pm | **Shipping complex AI apps with Braintrust** | Westminster | Production-grade eval platform. Pick if you want a different eval tool than Phoenix (3:30pm). |
| 3:30-5:30pm | **Build Your First Demand-Driven Context Base** | Shelley | Agent-driven context discovery with Claude Code sub-agents. Layer 1 + 5 focus. Pick if you want context engineering as the afternoon instead of evals. |
| 3:30-5:30pm | **Everything You Need To Know About Agent Observability** | Wordsworth | Agent self-diagnostics. Layer 6 focus. Pick if observability is your gap over evals. |

### Day 1 Decision Framework

The recommended schedule optimizes for **building harness infrastructure** (the execution, orchestration, feedback, and verification layers). v2 optimized for **building harness inputs** (skills, context). Both are valid paths:

- If your agents fail because **they do the wrong thing** -> you need better inputs (v2's approach: skills + DDC)
- If your agents fail because **they lose coherence, can't recover, or you can't debug them** -> you need better infrastructure (v3's approach: event sourcing + evals)

Most practitioners need both. v3 assumes the infrastructure gap is larger, because skills are easier to learn incrementally (they're markdown files) while harness architecture requires dedicated workshop time.

---

## Day 2 - April 9 (Talks): Understand the Discipline

### Morning Keynotes (Keynote room, everyone attends)

| Time | Session | Room | Why |
|---|---|---|---|
| 9:00-9:10am | Opening Address | Keynote | |
| 9:10-9:30am | Malte Ubl | Keynote | |
| 9:30-9:50am | Raia Hadsell | Keynote | |
| **9:50-10:10am** | **Harness Engineering: How to Build Software When Humans Steer and Agents Execute** (Ryan Lopopolo) | Keynote | **MUST SEE -- defines the field** |
| 10:10-10:30am | OpenClaw update (Peter Steinberger) | Keynote | |

**Ryan Lopopolo's keynote** is the single most important session of the conference for your goals. He leads the OpenAI Codex team. His statement -- "Agents aren't hard; the harness is hard" -- is why the harness engineering discipline exists. His post is pre-reading item #2. Everything in the Harness Engineering track builds on this talk.

### Expo Gap (10:30-11:15am)

| Time | Session | Room | Harness Layer |
|---|---|---|---|
| **10:30-10:48am** | **Stop babysitting your agents: building a context engine for mergeable code** (Brandon Walsenuk) | Wordsworth | Guides |

Context engine case study: same agent, same model -- with context engine: 25 min + 10.8M tokens, mergeable first pass. Without: 2.5 hours + 20.9M tokens. This is the Guides layer in action -- how the right feedforward information transforms agent output.

### Harness Engineering Track (Westminster room, 11:15am onward)

v3 commits to the Westminster room as home base. The Harness Engineering track IS the primary track for your goals.

| Time | Session | Speaker(s) | Harness Layer | Track |
|---|---|---|---|---|
| **11:15-11:40am** | **Harness Engineering AMA** | Ryan Lopopolo | All layers | Harness |
| 11:40-12:00pm | *(move to St. James)* **Nuno Campos** (Track Keynote, TBA) | Nuno Campos | TBD | Context |
| **12:00-12:20pm** | *(stay in St. James)* **Hierarchical Memory: Context Management in Agents** | Sally-Ann Delucia | Memory | Context |
| **12:20-12:40pm** | *(back to Westminster)* **Building a Chess Coach** | Anant Dole, Asbjorn Steinskog | Guides, Sensors, Memory | Harness |
| **12:40-1:00pm** | *(stay)* **Building the Justice AI Unit** | Dan James | All (production) | Harness |
| *Lunch* | | | | |
| **2:30-2:50pm** | **Harnesses in AI: A Deep Dive** | Tejas Kumar | All layers | Harness |
| **2:50-3:10pm** | **Why Your AI UX Is Broken** | Mike Christensen | Execution Infra, Memory | Harness |
| **3:10-3:30pm** | **Self-Evolving AI Agents** | Alexey Ostrikov | Sensors, Orchestration | Harness |

### Session Details and Why Each Matters

**Harness Engineering AMA (11:15)** -- Q&A with Ryan Lopopolo. This is your chance to ask implementation questions about the Codex harness. Come prepared with questions from your pre-reading of the OpenAI post. Example questions worth asking:
- How do they handle harness complexity growth over time? (Bitter Lesson tension)
- What's the boundary between inner harness (platform) and outer harness (user)?
- How do they decide what to enforce as invariants vs. leave to the model?

**Nuno Campos (11:40)** -- LangChain core contributor. Title TBA but likely about agent harness anatomy (LangChain published "The Anatomy of an Agent Harness" in March 2026). Worth the room hop for the LangChain perspective on harness components.

**Hierarchical Memory (12:00)** -- "The Unix philosophy -- small, focused tools that compose infinitely -- turns out to be exactly what LLMs need to make 200k tokens feel like 200 trillion." This is the Memory & State layer of the harness. Data from thousands of deployed agents.

**Building a Chess Coach (12:20)** -- Consumer AI product (Magnus Carlsen's chess app) using an agent harness in production. LLM coach + memory layer, prompt design, fallbacks, evals, evaluation-driven iteration. Real production harness with real constraints (latency, reliability, consumer expectations).

**Harnesses in AI: A Deep Dive (2:30)** -- Tejas Kumar's deep technical dive into harness architecture. All six layers covered.

**Why Your AI UX Is Broken (2:50)** -- Durable sessions, resumable streaming, interruption handling, multi-device continuity. This is the Execution Infrastructure layer that most teams build badly: "teams end up building their own fragile plumbing instead of shipping their actual product." Practical patterns for durable execution at the experience layer.

**Self-Evolving AI Agents (3:10)** -- Meta-agent loop: an Analyzer diagnoses failures from execution logs, an Evolver autonomously rewrites the system prompt. Over 80 generations, a bare-bones prompt evolved into a 5,700-token structured document with 34 rules and 21 few-shot examples. Won 1st place in international agent competition. This is the Sensors and Orchestration layers taken to their logical extreme -- the harness improving itself.

### End-of-Day Keynotes

| Time | Session | Room | Why |
|---|---|---|---|
| 3:45-4:03pm | **Why Rust is the Ideal Language for Vibe-Coding** (Daniel Szoke) | Wordsworth | The compiler as a harness sensor. Rust's tooling-enforced invariants provide an agentic feedback loop. Unique angle on "enforce invariants, not instructions." |
| **4:30-5:00pm** | **Software Engineering + AI = ?** (Gergely Orosz + swyx) | Keynote | The meta-question |
| **5:20-5:40pm** | **It Ain't Broke: Why Software Fundamentals Matter More Than Ever** (Matt Pocock) | Keynote | TDD, vertical slices, ubiquitous language applied to agent workflows. "The devs who succeed fall back on engineering fundamentals." |

### Room Hopping Map

```
9:00  ----[Keynote]----
9:50  Ryan Lopopolo keynote (HARNESS - foundational)
10:30 ----[Wordsworth expo]---- context engine talk
11:15 ----[Westminster]---- Harness AMA (Ryan Lopopolo)
11:40 ----[St. James]---- Nuno Campos (LangChain)
12:00 (stay in St. James) Hierarchical Memory
12:20 ----[Westminster]---- Chess Coach (harness in production)
12:40 (stay) Justice AI Unit (harness in government)
1:00  LUNCH
2:30  ----[Westminster]---- Harnesses Deep Dive (Tejas Kumar)
2:50  (stay) AI UX / Durable Sessions
3:10  (stay) Self-Evolving Agents
3:45  ----[Wordsworth]---- Rust as harness (optional expo)
4:30  ----[Keynote]---- Gergely + swyx
5:20  (stay) Matt Pocock
```

5 room changes. The Westminster room is home base for the whole afternoon (2:30-3:30 unbroken).

### Day 2 Alternatives

| Time | Alternative | Instead of | Why Consider |
|---|---|---|---|
| 12:00-12:20pm | **Skills issue: How agent skills evolve in the wild** (Langfuse, Moore) | Hierarchical Memory | If you want the Sensors perspective -- how to eval and iterate skills (guides). Langfuse is the leading open-source observability platform. |
| 12:20-12:40pm | **Proving Agents Correct: Memory Architecture and Formal Verification** (Fleming) | Chess Coach | TLA+ formal models as a machine-checkable security regression suite. Formal verification of agent harness invariants. More theoretical but unique. |
| 2:50-3:10pm | **Context Graphs for Explainable, Decision-Aware AI Agents** (St. James) | AI UX talk | If you care more about persistent context structures (Memory layer) than session durability (Execution layer). |
| 3:10-3:30pm | **Combine Skills and MCP to Close the Context Gap** (Pedro Rodrigues, St. James) | Self-Evolving Agents | Benchmark data on skills + MCP. If you attended Pedro's Day 1 workshop in v2, this completes the loop. But Ostrikov's self-evolving agent is a more novel harness pattern. |
| 3:10-3:30pm | **SWE-rebench: Evaluating Coding Agents** (Moore) | Self-Evolving Agents | If you want coding agent benchmark data -- common pitfalls of 30+ models on real SWE tasks. |

### Day 2: The 3:10pm Decision (Changed from v1 and v2)

v1 recommended Self-Evolving Agents. v2 switched to Pedro's Skills+MCP talk. **v3 switches back to Self-Evolving Agents.** Rationale: a meta-agent loop that autonomously improves its own system prompt across 80 generations is the most advanced harness pattern at the conference. It demonstrates the feedback loop (Sensors) driving automated improvement (Orchestration) without human intervention. This is where harness engineering is heading.

---

## Day 3 - April 10 (Coding Agents Track + Keynotes): See Harnesses in Production Code

### Morning Keynotes

| Time | Session | Room | Why |
|---|---|---|---|
| 9:20-9:40am | **David Soria Parra** | Keynote | Meta/PyTorch -- title TBA |
| 9:40-10:00am | **What Do Models Still Suck At?** (Peter Gostev) | Keynote | Real data on where models fail -- know your failure modes to design better harnesses |
| **10:10-10:30am** | **Building pi in a World of Slop** (Mario Zechner) | Keynote | Building a coding agent from scratch. OSS + agent quality concerns. |

### Expo Gap (10:30-11:15am)

| Time | Session | Room | Harness Layer |
|---|---|---|---|
| **10:30-10:48am** | **Benchmarking semantic code retrieval on Claude Code** | Wordsworth | Guides |

Claude Code plugin for semantic codebase search alongside grep/glob/BM25. Benchmark results comparing answer quality and token consumption. If Claude Code is your primary coding agent, this directly improves its Guides layer.

### The 11:15am Decision: Coding Agents vs Context Lifecycle

Two track keynotes compete:
- **Replacing 12K LoC with a 200 LoC Skill** (David Gomes, Fleming) -- Coding Agents track keynote
- **Context Is the New Code** (Patrick Debois, Westminster) -- Context deserves CI/CD, versioning, peer review

**v3 recommendation: Patrick Debois.** Here's why this is different from v2:

v2 recommended Gomes because it was context-focused and skills were the primary lens. v3 is harness-focused. Debois's talk frames context as a **managed artifact with a lifecycle** -- generate, evaluate, distribute, observe. This is exactly how the Guides layer of a harness should work: context isn't just files you write, it's a system you operate. The Context Development Lifecycle maps directly onto harness engineering's core principle: "the repository is the source of truth." Debois invented DevOps and coined the term -- when he says context needs the same rigor as code, it's coming from the person who proved that operations needed the same rigor as development.

That said, Gomes's "12K LoC to 200 LoC" talk is concretely impressive. If you want the case study that proves skills work, see the alternative below.

### Coding Agents Track (Fleming room, 11:15am or 11:40am onward)

| Time | Session | Speaker(s) | Harness Layer | Notes |
|---|---|---|---|---|
| *11:15-11:40am* | *(at Debois in Westminster, or Gomes in Fleming -- see above)* | | | |
| **11:40am-12:00pm** | **A Piece of PI -- Embedding The OpenClaw Coding Agent** | Matthias Luebken | Execution Infra, Orchestration | Agent internals, composable primitives |
| **12:00-12:20pm** | **The Year of Latency Debt** | Sarah Chieng | All | When inference hits 1000+ tok/s, smaller diffs + automated feedback loops. Harness design changes with speed. |
| **12:20-12:40pm** | **Fighting AI with AI** | Lawrence Jones (incident.io) | Sensors, Orchestration, Verification | **KEY SESSION**: agents debugging agents. Filesystem downloads for trace inspection, 25 parallel agents for analysis, AI-powered feedback loops. This IS harness engineering in production. |
| **12:40-1:00pm** | **Factory Missions -- Super Long Running Agents** | Grinberg, Alvoeiro | Memory, Orchestration, Execution Infra | Long-running coding agent patterns at scale |
| *Lunch* | | | | |
| **2:30-2:50pm** | **Your Coding Agent Should Do AI System Engineering** | Ben Burtenshaw (HF) | Guides, Sensors | Agent skills for CUDA kernels + ML experiments. 1000+ ML experiments daily at HuggingFace. |
| **2:50-3:10pm** | **Let's Talk About FOMAT** | Michael Richman | Execution Infra | Monitoring and interacting with coding agents from anywhere. The control plane pattern for async agent management. |
| **3:10-3:30pm** | **Cooking with Agents in VS Code** | Liam Hampton | Execution Infra, Guides | VS Code agent integration patterns |

### Day 3 Highlights

**Fighting AI with AI (12:20, Lawrence Jones)** is the strongest harness engineering case study on Day 3. incident.io's AI SRE system is a deeply nested tree of agents investigating production incidents. Their approach:
- Evals with a CLI + red-green runbook that AI agents can follow (Sensors)
- Filesystem downloads: serializing complex agent traces as markdown for AI analysis (Memory)
- 25 parallel AI agents analyzing investigations, clustering results (Orchestration)
- AI agents dogfooding their own tools, submitting structured feedback (Verification)

This is the Sensors + Orchestration layers working at production scale.

**The Year of Latency Debt (12:00, Sarah Chieng)** matters for harness design: at 1000+ tok/s, the harness needs to change. Current "bad habits" (huge prompts, massive diffs, 10 parallel sessions) become unnecessary. The harness should adapt to speed: smaller diffs, tighter feedback loops, less context switching.

### Lunch Break Option

| Time | Session | Room | Type |
|---|---|---|---|
| 1:25-1:43pm | **Stop babysitting your agents: context engine** (repeat) | Wesley | Expo |
| 1:45-2:03pm | **Comprehend First, Code Later** (Priscila, Sentry) | Shelley | Expo |

The Sentry talk has real data: 239 messages analyzed, showing comprehension > generation as the #1 AI use in large codebases. Relevant for understanding when the harness should prioritize understanding over action.

### End-of-Day Keynotes

| Time | Session | Room | Why |
|---|---|---|---|
| **4:30-4:50pm** | **Fireside Chat: Gergely Orosz + Tuomas Artman (Linear)** | Keynote | How Linear uses agents at scale |
| **5:00-5:20pm** | **Agents need more than a chat** (Jacob Lauritzen) | Keynote | Agent UX beyond chat interfaces |
| **5:20-5:40pm** | **The Friction Is Your Judgment** (Armin Ronacher + Cristina Poncela Cubeiro) | Keynote | Armin created Flask and co-founded Sentry. Where human judgment matters in agent workflows. |

---

## The 3-Day Narrative: Theory -> Architecture -> Production

### Day 1: Build the infrastructure layers

You leave Day 1 with hands-on experience in:
- **Orchestration**: structured handoffs, event-sourced agent loops, simple self-improving loops
- **Execution**: Effect-TS harness with replay, time-travel debugging, hot-swap plugins
- **Sensors**: adversarial evaluator agents, traces as debugging, deterministic + inferential evals
- **Verification**: complete eval pipeline, impact hierarchy, Swiss Cheese defense model

### Day 2: Understand the discipline from the people who defined it

You leave Day 2 understanding:
- **Why**: Lopopolo's keynote + AMA -- the foundational principles from OpenAI's experience
- **What**: Tejas Kumar's deep dive -- all six harness layers mapped out
- **How it evolves**: Self-Evolving Agents -- harnesses that improve themselves
- **What it feels like in production**: Chess Coach, Justice AI Unit -- real constraints, real trade-offs
- **What's still missing**: Durable sessions, memory hierarchy, the human judgment question

### Day 3: See it applied to coding at scale

You leave Day 3 knowing:
- **How production teams do it**: incident.io (agents debugging agents), HuggingFace (1000+ daily experiments), Linear
- **What changes with speed**: latency debt paydown, smaller diffs, tighter loops
- **Where skills fit**: 12K LoC -> 200 LoC, CUDA kernels, the guides layer of the harness
- **The human side**: comprehension > generation, friction as judgment

---

## Post-Conference: Implementation Roadmap

After the conference, implement in this order. Each step builds on the previous.

### Week 1: Establish the Outer Harness

The "outer harness" (Fowler's term) is what YOU set up for YOUR codebase. This is where the most leverage lives.

1. **CLAUDE.md / rules files** -- Write machine-readable project documentation. Not for humans; for agents. Include architectural constraints, dependency rules, naming conventions.
2. **Session initialization ritual** -- Define what an agent must do before starting work: read directory structure, review recent git log, check progress files, run sanity tests.
3. **Git as state management** -- Every agent session ends in a clean, committed state. Use commit messages as structured logs of what happened and why.

*Harness layers covered: Guides, Memory*

### Week 2: Build the Feedback Loop

4. **Linter + type checker as first sensors** -- These are computational, deterministic, and cheap. Run them after every agent action. Configure as pre-commit hooks.
5. **Structural tests** -- Tests that enforce architectural invariants (e.g., no circular dependencies, all API endpoints have auth middleware). These prevent the class of errors agents make most often.
6. **Simple eval pipeline** -- Based on the Day 1 workshop: deterministic checks + one LLM-as-judge evaluator for your most common agent task.

*Harness layers covered: Sensors, Verification*

### Week 3: Add Orchestration

7. **Sub-agents as context firewalls** -- For any task that takes more than one session, use sub-agents to isolate discrete subtasks. This prevents context pollution.
8. **Progress files** -- claude-progress.txt or similar. Document what was done, what's pending, what failed. The next session reads this first.
9. **Incremental over comprehensive** -- Configure agents to work feature-by-feature, not attempt full implementations. Each session produces a mergeable unit.

*Harness layers covered: Orchestration, Memory*

### Week 4: Iterate Based on Failures

10. **The Hashimoto loop** -- Every time an agent makes a mistake, engineer the environment so it can never make that mistake again. Add a test, a lint rule, a CLAUDE.md instruction, or a constraint.
11. **Remove what doesn't work** -- Apply the Vercel lesson. If a tool, rule, or instruction isn't measurably helping, remove it. Simpler harnesses work better.
12. **Measure** -- Track: first-pass merge rate, tokens per task, human correction rate, time to completion. These are your harness KPIs.

*This is the core harness engineering discipline: continuous environmental improvement.*

---

## Quick Reference: Top 12 Must-See Sessions (Harness Focus)

| # | Session | When | Harness Layer |
|---|---|---|---|
| 1 | **How to Build Agents That Run for Hours** (workshop) | Apr 8, 9:00am | Orchestration, Memory, Sensors |
| 2 | **Make your own event-sourced agent harness** (workshop) | Apr 8, 10:40am | Execution, Orchestration, Memory |
| 3 | **Ship Real Agents: Evals for Agentic Apps** (workshop) | Apr 8, 3:30pm | Sensors, Verification |
| 4 | **Harness Engineering keynote** (Lopopolo) | Apr 9, 9:50am | All (foundational) |
| 5 | **Harness Engineering AMA** (Lopopolo) | Apr 9, 11:15am | All (Q&A) |
| 6 | **Harnesses in AI: A Deep Dive** (Tejas Kumar) | Apr 9, 2:30pm | All (deep dive) |
| 7 | **Why Your AI UX Is Broken** (Christensen) | Apr 9, 2:50pm | Execution Infra |
| 8 | **Self-Evolving AI Agents** (Ostrikov) | Apr 9, 3:10pm | Sensors, Orchestration |
| 9 | **It Ain't Broke: Software Fundamentals** (Pocock) | Apr 9, 5:20pm | Guides, Sensors |
| 10 | **Fighting AI with AI** (incident.io) | Apr 10, 12:20pm | Sensors, Orchestration, Verification |
| 11 | **Factory Missions: Super Long Running Agents** | Apr 10, 12:40pm | Memory, Orchestration |
| 12 | **The Friction Is Your Judgment** (Ronacher) | Apr 10, 5:20pm | Meta (human-harness boundary) |

---

## Skills Narrative (Unchanged from v2, Now Framed as Guides Layer)

Skills are the **Guides layer** of the harness -- feedforward controls that shape agent behavior before it acts. The conference has a complete skills arc even in the harness-focused v3 schedule:

1. **Day 1 alternative**: Write and eval skills (Pedro workshop, 9:00am Abbey)
2. **Day 1 alternative**: Make skills portable (Skills at Scale workshop, 10:40am Abbey)
3. **Day 2**: How skills evolve in the wild (Langfuse, 12:20pm Moore -- alternative)
4. **Day 2**: Skills + MCP benchmark results (Pedro, 3:10pm St. James -- alternative)
5. **Day 3**: 12K LoC -> 200 LoC Skill (Gomes, 11:15am Fleming -- alternative)
6. **Day 3**: Agent skills for systems engineering (HuggingFace, 2:30pm Fleming)

If you find Day 1's harness workshops confirm what you already know, swap the 9:00am slot for Pedro's skills workshop and the 10:40am for Skills at Scale. You'll still get harness depth on Days 2-3.

---

## v3 vs v2: Summary of Changes

| Aspect | v2 | v3 |
|---|---|---|
| Day 1 focus | Skills mastery + context discovery | Harness architecture + implementation + evals |
| Day 1 primary | Supabase Skills + Skills at Scale + DDC | Agents That Run for Hours + Event-Sourced Harness + Ralph Loops + Evals |
| Day 2 3:10pm | Skills + MCP (Pedro) | Self-Evolving Agents (Ostrikov) |
| Day 3 11:15am | Replacing 12K LoC (Gomes) | Context Is the New Code (Debois) |
| Narrative | Context-first, harness-second | Harness-first, context serves the harness |
| Pre-reading | Not included | 6 foundational articles in order |
| Post-conference | Not included | 4-week implementation roadmap |
| Session framing | By topic | By harness layer |
