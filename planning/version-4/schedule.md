# AI Engineer Europe 2026 - Personal Schedule v4

**Conference:** AI Engineer Europe 2026
**Dates:** April 8-10, 2026
**Venue:** Queen Elizabeth II Centre, London, UK
**Website:** https://ai.engineer/europe

---

## What Changed from v3

v3 was harness-first but informed by summaries and descriptions. v4 is harness-first and informed by **deep reading of every foundational source** -- all 20+ articles, blog posts, and academic papers from the references list. Every session recommendation now maps to specific findings from the research.

Key shifts:

- **Day 1 rebalanced**: v3 was 100% infrastructure workshops. v4 inserts the "Mergeable by default" context engine workshop at 1:00pm because the research proves the Guides layer (feedforward controls) is where the most leverage lives for coding agent users. All six harness layers are now covered on Day 1.
- **AMA questions**: Informed by reading the actual Codex agent loop internals (prompt construction layers, encrypted compaction, reasoning token behavior) and the App Server architecture (JSON-RPC, Items/Turns/Threads). These are questions you can't ask without having read the source material.
- **Post-conference roadmap redesigned**: Now follows Hashimoto's six-step adoption journey rather than an abstract weekly plan. Each step builds on research-validated principles.
- **Quantitative evidence throughout**: Every major recommendation is backed by metrics from the sources (6x performance gap, 56.3% vs 38.2%, LangChain top 30 to top 5, etc).
- **"What to listen for" per session**: Each session has a note about what specific concepts from the research the speaker is likely to address, so you can connect talks to the source material in real time.
- **New section: Operational Principles**: 10 principles distilled from all 20+ sources, each backed by evidence. These are the decision-making framework for the entire conference and beyond.

---

## What the Research Proves

These are the quantitative findings from studying every source. They justify why harness engineering is the highest-leverage skill to develop at this conference.

| Finding | Source | Implication |
|---------|--------|-------------|
| Changing only the harness around a fixed LLM produces a **6x performance gap** on the same benchmark | Meta-Harness (Stanford) | Harness design matters as much as model selection |
| A smaller model (Gemini Flash) with an auto-generated harness **beat a larger model** (Gemini Pro) without one: 56.3% vs 38.2% win rate | AutoHarness (Google DeepMind) | A good harness > a better model |
| LangChain moved from **outside the top 30 to top 5** on Terminal Bench 2.0 by changing only the harness, not the model | LangChain, confirmed by Bouchard | The harness IS the product differentiator |
| Removing 80% of tools improved accuracy from **80% to 100%**, speed by 3.5x, tokens by 37% | Vercel | Simpler harnesses work better with capable models |
| Guardrails built for weaker models **actively degraded performance** on stronger models (Opus 4.5) | Vercel | "Build to delete" -- every harness component encodes a model limitation assumption |
| Auto-generated or bloated CLAUDE.md files **hurt performance** vs concise hand-written ones | ETH Zurich study (cited by HumanLayer) | Short maps > long manuals. Lopopolo: "~100 lines" for AGENTS.md |
| Solo agent: 20 min, $9, **broken**. Full harness: 6 hrs, $200, **functional** | Anthropic (harness design) | The harness makes the difference between shipping and not shipping |
| When Opus 4.6 arrived, sprint contracts and single-pass QA became **unnecessary** | Anthropic | "Every component in a harness encodes an assumption about what the model can't do on its own, and those assumptions are worth stress testing" |
| Best frontier model scores only **24%** on real professional tasks (APEX-Agents) | Mercor/APEX | Long-horizon multi-application orchestration is the unsolved problem |
| Stripe produces **1,000+ merged PRs per week** using agents in isolated environments with hard CI limits | Bouchard, citing Stripe | Production-scale harness engineering works |
| OpenAI shipped **~1M LoC** across ~1,500 PRs with zero human-written code. ~3.5 PRs/engineer/day. 1/10th the dev time. | OpenAI (Lopopolo) | Harness engineering at its most extreme |
| Cached tokens cost **10x less** ($0.30 vs $3.00/MTok on Claude Sonnet). KV-cache hit rate is the #1 production metric | Manus | Harness design must be cache-aware: append-only context, stable prefixes, masking over removal |
| Agent task reliability **doubles every 3-7 months** per METR data | swyx/latent.space | The harness you build today should be simpler than the one you'd build 6 months ago |

---

## Operational Principles

Distilled from all 20+ sources. These are not theoretical -- each is backed by production evidence and should guide both your conference attendance and your post-conference implementation.

### 1. The Harness IS the Product

A 6x performance gap from harness changes alone (Meta-Harness). LangChain top 30 to top 5 by changing only the harness. Flash beating Pro with a harness. The model is a commodity; the harness is the differentiator.

### 2. Enforce Invariants, Not Instructions

OpenAI requires data shapes to be parsed at boundaries but doesn't specify which library. Fowler's guides define "what" not "how." Anthropic's clean-state discipline requires each session to end committed and documented. The harness defines boundaries; the model reasons within them.

### 3. Give the Agent a Map, Not a Manual

Lopopolo: AGENTS.md should be ~100 lines, a table of contents pointing into a structured `docs/` directory. A monolithic instruction file "failed in predictable ways -- when everything is 'important,' nothing is." HumanLayer: too many tools push the context into the "dumb zone." Manus: 100:1 input-to-output token ratio, so every context token matters.

### 4. Build to Delete

Every harness component encodes an assumption about what the model can't do. Anthropic found sprint contracts unnecessary when Opus 4.6 arrived. Vercel found guardrails for weaker models degraded performance on stronger ones. Phil Schmid: Manus refactored 5 times in 6 months. The harness must be lighter after each model upgrade, not heavier.

### 5. Verification Is the Single Biggest Lever

Hashimoto: "If you give an agent a way to verify its work, it more often than not fixes its own mistakes." Fowler: build computational controls (deterministic, cheap, fast) before inferential controls (LLM-as-judge, expensive, slow). OpenAI's custom linters include remediation instructions injected directly into agent context ("positive prompt injection").

### 6. Errors Left In > Clean Retries

Manus: preserving wrong turns in context improves behavior more than resetting. Error recovery is "one of the clearest indicators of true agentic behavior." Failed commands should return error messages to the model, not be silently retried.

### 7. The Repository Is the Only Source of Truth

Lopopolo: "Slack discussions, Google Docs, and tacit human knowledge are invisible to agents -- if it isn't discoverable in the repo, it effectively doesn't exist for the agent." OpenAI runs a "doc-gardening" agent that scans for stale documentation and opens fix-up PRs. Documentation is infrastructure, not overhead.

### 8. Cache-Aware Context Design

Manus: cached tokens cost 10x less. Keep prefixes stable. Make context append-only. Use logit masking to constrain action spaces instead of dynamically loading/removing tools (which breaks cache). The Codex agent loop exploits the prefix property -- new prompts always append to existing ones, enabling prompt caching. Any disruption (model switching, tool reordering, sandbox config changes) destroys cache hits.

### 9. Corrections Are Cheap, Waiting Is Expensive

OpenAI pushes almost all code review to agent-to-agent loops, escalating to humans only when judgment is required. PRs are short-lived. When agent throughput exceeds human attention, the pipeline must optimize for throughput, not gatekeeping.

### 10. Start Simple, Remove Before Adding

Vercel removed 80% of tools and improved every metric. Manus's biggest gains came from removing features. HumanLayer: "Start simple. Add configuration only when agents demonstrably fail." The right question after a failure is "what constraint can I add?" not "what feature can I build?"

---

## The Harness Mental Model

From the foundational sources (OpenAI, Anthropic, Fowler), a harness has six functional layers:

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

Fowler adds a critical typing: **computational controls** (deterministic, CPU-based, milliseconds, cheap) vs **inferential controls** (non-deterministic, GPU-based, slower, expensive). Build computational first.

Fowler also distinguishes the **inner harness** (built by the platform -- Claude Code's built-in behaviors) from the **outer harness** (built by YOU for YOUR codebase). The outer harness is where the most leverage lives for coding agent users. Your CLAUDE.md, your tests, your linters, your architectural constraints.

---

## Pre-Conference Reading

Read in this order. Each builds on the previous. The "look for" notes tell you what to extract that will make conference sessions more valuable.

| # | Source | Time | Look For |
|---|--------|------|----------|
| 1 | [Mitchell Hashimoto - My AI Adoption Journey](https://mitchellh.com/writing/my-ai-adoption-journey) | 20 min | The six-step progression: drop chatbot -> reproduce work -> end-of-day agents -> outsource slam dunks -> engineer the harness -> always running. Note "verification is the single biggest lever" and the negative space insight (knowing what NOT to delegate). |
| 2 | [OpenAI - Harness Engineering](https://openai.com/index/harness-engineering/) | 30 min | AGENTS.md as ~100 lines (a map, not a manual). The architectural layering (Types -> Config -> Repo -> Service -> Runtime -> UI). Doc-gardening agents. Entropy management ("garbage collection"). "Corrections are cheap, waiting is expensive." **This is what Lopopolo's keynote will expand on.** |
| 3 | [OpenAI - Unrolling the Codex Agent Loop](https://openai.com/index/unrolling-the-codex-agent-loop/) | 25 min | The five-stage loop. Prompt construction layers (system -> developer -> environment -> user). How prompt caching exploits prefix stability. Automatic compaction via `encrypted_content`. Why reasoning tokens persist within a turn but not across turns. **This gives you the technical depth for the AMA.** |
| 4 | [Anthropic - Effective Harnesses for Long-Running Agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents) | 25 min | Two-agent pattern: initializer + coding agent. The startup sequence (verify dir, read progress, review git, launch dev, run smoke tests). Feature lists with boolean completion status. Git as state management. |
| 5 | [Anthropic - Harness Design for Long-Running Apps](https://www.anthropic.com/engineering/harness-design-long-running-apps) | 25 min | The GAN-inspired generator/evaluator split. Sprint contracts. "Context anxiety" (Sonnet 4.5 prematurely wrapping up near perceived context limits). And critically: when Opus 4.6 arrived, they removed components -- "every component encodes an assumption about what the model can't do." |
| 6 | [Martin Fowler - Harness Engineering for Coding Agent Users](https://martinfowler.com/articles/exploring-gen-ai/harness-engineering.html) | 30 min | Agent = Model + Harness. Guides (feedforward) vs sensors (feedback). Computational vs inferential controls. "Positive prompt injection" (custom linter messages optimized for LLM consumption). Three harness types: maintainability, architecture fitness, behavior. The concept of "harnessability." Ashby's Law applied to agents. |
| 7 | [Vercel - We Removed 80% of Our Agent's Tools](https://vercel.com/blog/we-removed-80-percent-of-our-agents-tools) | 15 min | 80% -> 100% accuracy by removing tools. The critical prerequisite: well-documented data layer with consistent naming. Guardrails for weak models degrading strong model performance. |
| 8 | [Manus - Context Engineering for AI Agents](https://manus.im/blog/Context-Engineering-for-AI-Agents-Lessons-from-Building-Manus) | 25 min | KV-cache hit rate as #1 metric. Masking over removal. Todo-list recitation against lost-in-the-middle. Errors left in > clean retries. Filesystem as extended context. 100:1 input:output ratio. |

Total: ~3.5 hours. Read sources 1-3 before anything else -- they give you the vocabulary and the technical depth for Lopopolo's keynote and AMA.

**Optional deep reading** (if time allows):

| Source | Time | Why |
|--------|------|-----|
| [LangChain - Anatomy of an Agent Harness](https://blog.langchain.com/the-anatomy-of-an-agent-harness/) | 20 min | The Ralph Loop pattern. Filesystem as most foundational primitive. Context rot countermeasures. |
| [HumanLayer - Skill Issue](https://www.humanlayer.dev/blog/skill-issue-harness-engineering-for-coding-agents) | 20 min | Progressive disclosure via skills. Sub-agents as "context firewalls." The "dumb zone" concept. Back-pressure mechanisms. |
| [swyx - Agent Engineering / IMPACT](https://www.latent.space/p/agent) | 20 min | IMPACT framework (Intent, Memory, Planning, Authority, Control flow, Tools). Editable plans as sweet spot. Authority as the oldest unsolved problem. |
| [Meta-Harness paper](https://arxiv.org/abs/2603.28052) | 30 min | The 6x performance gap. Automated harness optimization. Why the proposer needs rich execution traces, not just summaries. |

---

## Day 1 - April 8 (Workshops): Build All Six Layers

Workshop day. Four time slots. The recommended schedule constructs a complete harness.

### Recommended Schedule

| Time | Workshop | Room | Harness Layers | Source Connection |
|---|---|---|---|---|
| 9:00-10:20am | **How to Build Agents That Run for Hours (Without Losing the Plot)** | St. James | Orchestration, Memory, Sensors | Anthropic's two-agent pattern, Hashimoto's verification lever |
| 10:40am-12:00pm | **Make your own event-sourced agent harness in 60 seconds** | Shelley | Execution Infra, Orchestration, Memory | LangChain's filesystem primitive, Manus's event-driven architecture |
| *Lunch* | | | | |
| 1:00-3:00pm | **Mergeable by default: Building the context engine to save time and tokens** | Wordsworth | Guides | Lopopolo's documentation-as-infrastructure, Manus's filesystem as extended context |
| 3:30-5:30pm | **Ship Real Agents: Hands-On Evals for Agentic Applications** | Westminster | Sensors, Verification | Fowler's computational vs inferential controls, Hashimoto's verification lever |

### Why This Combination

**Morning arc: Harness architecture and implementation.**

The 9:00am workshop (Ash Prabaker, Andrew Wilson) teaches operational patterns for long-running agents:
- Why self-evaluation is a trap and adversarial evaluator agents work better -- this is Anthropic's GAN-inspired insight: "Claude confidently praises its own work, even when quality is obviously mediocre"
- Why context compaction doesn't cure coherence drift but structured handoffs do -- connect to Manus's finding that errors left in context improve behavior
- How to decompose work into testable sprint contracts -- Anthropic's pattern, with the caveat that better models may make this unnecessary
- How to read traces as your primary debugging loop
- Which parts of the harness to delete when the next model drops -- the "build to delete" principle in practice

The 10:40am workshop (Misha Kaletsky, Jonas Templestein) is the most implementation-focused harness session at the conference:
- Effect-TS agent harness where everything is an event -- event sourcing for agent state, the same pattern OPENDEV (academic paper) formalizes as a six-phase ReAct loop
- Parallel tool execution -- what the Codex agent loop does internally
- Full replay and time-travel debugging -- Meta-Harness showed that rich execution traces (not just summaries) are essential for harness improvement
- Agent plugins loaded and hot-swapped at runtime

By lunch, you've seen harness architecture (what layers exist and why) AND built a working event-sourced harness.

**Afternoon arc: The Guides layer and verification.**

The 1:00pm "Mergeable by default" workshop (Peter Werry) addresses the Guides layer -- the one harness layer not covered by the morning:
- Building the reasoning layer that delivers organizational context to coding agents
- The expo session data validates this: same agent, same model -- with context engine: 25 min + 10.8M tokens, mergeable first pass. Without: 2.5 hours + 20.9M tokens
- This is what Lopopolo calls "documentation-as-infrastructure" and what Manus calls "filesystem as extended context" -- the workshop teaches you to build it
- Reasoning across conflicting sources, maintaining permissions, personalizing results

The 3:30pm evals workshop (Laurie Voss) builds the verification layer:
- Complete evaluation pipeline using Claude Agent SDK
- Three evaluator types: deterministic code checks, LLM-as-judge, custom rubrics -- this maps directly to Fowler's computational vs inferential controls
- Validates judges against human labels -- "an untested eval is being wrong at scale"
- Impact hierarchy for prioritizing fixes, Swiss Cheese model for layering defenses

**Day 1 covers all six harness layers:** Guides (1pm), Sensors (9am + 3:30pm), Execution Infra (10:40am), Memory (9am + 10:40am), Orchestration (9am + 10:40am), Verification (3:30pm).

### v4 Change: Why "Mergeable by default" Replaces "Ralph Loops"

v3 had "Ralph Loops: Build Dumb AI Loops That Ship" at 1:00pm. v4 replaces it with "Mergeable by default." The reasoning:

The Ralph Loop is a valuable pattern (LangChain coined the term: reinject the original prompt in a clean context window when the model tries to exit prematurely). But it's a single technique you can learn from the blog post. The "Mergeable by default" workshop teaches you to build a complete context engine -- the Guides layer -- with production data showing 25 min vs 2.5 hours. Given the research finding that the Guides layer is where the most leverage lives for coding agent users (Lopopolo: "if it isn't discoverable in the repo, it effectively doesn't exist"), this is the higher-value workshop.

Ralph Loops moves to the alternatives list.

### Alternatives Per Slot

| Time | Alternative | Room | Trade-off |
|---|---|---|---|
| 9:00-10:20am | **Skill Issue: Agents Good at Supabase** | Abbey | Swaps harness architecture for skills writing + eval harness (Braintrust). Addresses your objective "how to write, evaluate, and iterate on Agent Skills." Pick if you want Layer 1 (Guides) depth early rather than layers 4-5. |
| 9:00-10:20am | **Codex and Subagents** | Westminster | Hands-on with OpenAI's coding agent and sub-agent patterns. Pick if you want to experience the inner harness Lopopolo describes. |
| 9:00-10:20am | **Agentic Search for Context Engineering** | Wordsworth | RAG-to-agentic-search evolution. Pick only if retrieval is your main gap. |
| 10:40am-12:00pm | **Skills at Scale** | Abbey | Portable skills across Claude Code, Cursor, Codex. Directly addresses your objective "how to make skills portable." |
| 10:40am-12:00pm | **Playground in Prod** (Samuel Colvin) | Westminster | Live agent optimization with Pydantic AI. Strong if you use Python. |
| 1:00-3:00pm | **Ralph Loops: Build Dumb AI Loops That Ship** | Abbey | The LangChain-coined pattern. Simple self-improving loops. Pick if you want orchestration depth over guides depth. |
| 1:00-3:00pm | **Shipping complex AI apps with Braintrust** | Westminster | Production eval platform. Pick if you want a different eval toolchain. |
| 3:30-5:30pm | **Build Your First Demand-Driven Context Base** | Shelley | Agent-driven context discovery with Claude Code sub-agents. Addresses "demand-driven context discovery" objective. Pick if you want context discovery over eval pipelines. |
| 3:30-5:30pm | **Everything You Need To Know About Agent Observability** | Wordsworth | Layer 6 focus. Pick if observability is your bigger gap than evals. |

### Day 1 Decision Framework

v4 covers all six harness layers: infrastructure in the morning, guides in the early afternoon, verification in the late afternoon. If you already know how to build context engines (CLAUDE.md, docs directories, skills), swap the 1:00pm slot for Ralph Loops or Braintrust. If you already know how to build eval pipelines, swap the 3:30pm slot for DDC or Observability.

---

## Day 2 - April 9 (Talks): Understand the Discipline from the People Who Defined It

### Morning Keynotes (Keynote room, everyone attends)

| Time | Session | Room | Notes |
|---|---|---|---|
| 9:00-9:10am | Opening Address | Keynote | |
| 9:10-9:30am | Malte Ubl | Keynote | |
| 9:30-9:50am | Raia Hadsell | Keynote | |
| **9:50-10:10am** | **Harness Engineering: How to Build Software When Humans Steer and Agents Execute** (Ryan Lopopolo) | Keynote | **MUST SEE** |
| 10:10-10:30am | OpenClaw update (Peter Steinberger) | Keynote | |

**Ryan Lopopolo's keynote** defines harness engineering for the whole conference. He's the OpenAI Codex team member who wrote the harness engineering post and coined "Agents aren't hard; the harness is hard." His team shipped ~1M LoC with zero human-written code using the principles you read in pre-reading #2.

**What to listen for:** How he frames the tension between "build to delete" (harnesses should get simpler) and the production reality that his team runs doc-gardening agents, entropy management ("garbage collection"), and strict architectural layering. This tension -- minimalism vs production rigor -- is THE open question in the field.

### Expo Gap (10:30-11:15am)

| Time | Session | Room | Harness Layer |
|---|---|---|---|
| **10:30-10:48am** | **Stop babysitting your agents: building a context engine for mergeable code** (Brandon Walsenuk) | Wordsworth | Guides |

Context engine case study with hard numbers: same agent, same model -- with context engine: 25 min + 10.8M tokens, mergeable first pass. Without: 2.5 hours + 20.9M tokens. This IS the Guides layer quantified. If you did the "Mergeable by default" workshop on Day 1, this is the talk version of what you built.

### Harness Engineering Track (Westminster = home base)

v4 commits to Westminster as home base, with targeted excursions to St. James (Context Engineering) where they directly serve harness understanding.

| Time | Session | Speaker(s) | Harness Layer | What to Listen For |
|---|---|---|---|---|
| **11:15-11:40am** | **Harness Engineering AMA** | Ryan Lopopolo | All | See AMA questions section below |
| 11:40-12:00pm | *(move to St. James)* **Nuno Campos** (Track Keynote) | Nuno Campos | TBD | LangChain went outside top 30 to top 5 by changing only the harness. Ask about the Ralph Loop, context rot countermeasures, and which harness changes had the biggest impact on Terminal Bench 2.0 |
| **12:00-12:20pm** | *(stay in St. James)* **Hierarchical Memory: Context Management in Agents** | Sally-Ann Delucia | Memory | "Small, focused tools that compose infinitely -- turns out to be exactly what LLMs need to make 200k tokens feel like 200 trillion." How does this relate to Manus's todo-list recitation and filesystem-as-memory? |
| **12:20-12:40pm** | *(back to Westminster)* **Building a Chess Coach** | Anant Dole, Asbjorn Steinskog | Guides, Sensors, Memory | Real consumer product (Magnus Carlsen's app). LLM coach + memory + fallbacks + evals. How do they handle the "build to delete" problem when the product is live? |
| **12:40-1:00pm** | *(stay)* **Building the Justice AI Unit** | Dan James | All (production) | Government production harness. What constraints does government impose that commercial doesn't? Safety, auditability, permissions boundaries |
| *Lunch* | | | | |
| **2:30-2:50pm** | **Harnesses in AI: A Deep Dive** | Tejas Kumar | All | How does he map the six layers? Does he address the computational vs inferential control distinction? |
| **2:50-3:10pm** | **Why Your AI UX Is Broken** | Mike Christensen | Execution Infra, Memory | Durable sessions, resumable streaming, interruption handling. Directly addresses your objective on "agent UX patterns." Connect to OpenAI's App Server design: Items/Turns/Threads as durability primitives |
| **3:10-3:30pm** | **Self-Evolving AI Agents** | Alexey Ostrikov | Sensors, Orchestration | Meta-agent loop: Analyzer + Evolver autonomously rewrote system prompt over 80 generations into 5,700-token document with 34 rules and 21 few-shot examples. This is automated harness improvement -- compare to Meta-Harness paper's automated outer-loop search |

### Why Self-Evolving Agents at 3:10pm (Unchanged from v3)

v1 recommended this. v2 switched to Pedro's Skills+MCP talk. v3 switched back. v4 confirms. The reasoning is now stronger: Meta-Harness (Stanford) proved that automated harness optimization outperforms manual design, improving over SOTA by 7.7 points using 4x fewer tokens. Ostrikov's talk is the practitioner version of the same insight -- a harness that improves itself. This is where the field is heading.

Pedro's Skills+MCP benchmarks are valuable but can be obtained from his Day 1 workshop materials. A meta-agent loop that evolves its own system prompt is a pattern you won't encounter elsewhere.

### End-of-Day Keynotes

| Time | Session | Room | What to Listen For |
|---|---|---|---|
| 3:45-4:03pm | **Why Rust is the Ideal Language for Vibe-Coding** (Daniel Szoke) | Wordsworth | Rust's compiler as a harness sensor. The borrow checker, type system, and clippy as computational controls that provide the agent constant feedback. This is Fowler's "computational controls" principle demonstrated through a language ecosystem. |
| **4:30-5:00pm** | **Software Engineering + AI = ?** (Gergely Orosz + swyx) | Keynote | swyx defined the IMPACT framework. Listen for how they frame Authority (the oldest unsolved problem) and whether they address the "stutter-step agent" anti-pattern (requiring confirmation for every action). |
| **5:20-5:40pm** | **It Ain't Broke: Why Software Fundamentals Matter More Than Ever** (Matt Pocock) | Keynote | TDD, vertical slices, ubiquitous language applied to agent workflows. "The devs who succeed fall back on engineering fundamentals." Connect to Principle #2: enforce invariants, not instructions. |

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
3:45  ----[Wordsworth]---- Rust as harness sensor (optional expo)
4:30  ----[Keynote]---- Gergely + swyx
5:20  (stay) Matt Pocock
```

5 room changes. Westminster is home base for the entire afternoon block (2:30-3:30, unbroken).

### Day 2 Alternatives

| Time | Alternative | Instead of | Why Consider |
|---|---|---|---|
| 11:15-11:40am | **Maggie Appleton** (Context Engineering, St. James) | Harness AMA | If announced as a strong opener -- Maggie is an exceptional communicator. But the AMA with Lopopolo is irreplaceable if you've done the pre-reading. |
| 12:00-12:20pm | **Everything I Learned Training Frontier Small Models** (Maxime Labonne, Moore) | Hierarchical Memory | Different angle: model-side perspective. Pick only if you want to understand what training gives vs what the harness must add. |
| 12:20-12:40pm | **Skills issue: How agent skills evolve in the wild** (Marc Klingen, Langfuse, Moore) | Chess Coach | Addresses your objective "evaluation pipelines for agentic coding workflows." Langfuse is the leading open-source observability platform. Strong alternative if evals > production case studies for you. |
| 2:50-3:10pm | **Context Graphs for Explainable, Decision-Aware AI Agents** (Kollegger, Zaim, St. James) | AI UX talk | Persistent knowledge structures as the Memory layer. Pick if you care more about context architecture than session durability. |
| 3:10-3:30pm | **Combine Skills and MCP to Close the Context Gap** (Pedro Rodrigues, St. James) | Self-Evolving Agents | Benchmark data on skills + MCP in production. Pick if you attended Pedro's Day 1 workshop and want the quantitative follow-up. |
| 3:10-3:30pm | **SWE-rebench: Evaluating Coding Agents** (Badertdinov, Moore) | Self-Evolving Agents | Common pitfalls of 30+ models on real SWE tasks. Pick if coding agent benchmark data > meta-agent patterns. |

---

## Questions for the Lopopolo AMA (11:15am, Day 2)

These questions are informed by reading the actual Codex agent loop internals, the App Server architecture, and the harness engineering post. They go deeper than what a casual attendee would ask.

### On Harness Complexity Management

1. **The entropy problem.** You mentioned spending "20% of the week cleaning up AI slop" before automating garbage collection with background Codex tasks. How do you prevent the garbage collection agents from introducing their own entropy? Is there a second-order cleanup loop?

2. **The Bitter Lesson tension.** Your harness includes strict architectural layering (Types -> Config -> Repo -> Service -> Runtime -> UI), custom linters with remediation instructions, doc-gardening agents, and entropy management. That's substantial infrastructure. Which of these do you expect to remove as models improve? Which do you think are permanent regardless of model capability?

### On the Agent Loop

3. **Compaction.** The Codex agent loop uses automatic compaction via an `encrypted_content` item that "preserves the model's latent understanding" when context exceeds the window. How does compaction quality affect harness reliability? Are there tasks where compacted context fails in ways that uncompacted context wouldn't?

4. **Reasoning token persistence.** Reasoning tokens persist across tool calls within a turn but are discarded between turns. Does this create a cliff where complex multi-turn reasoning loses coherence? How does the harness compensate?

5. **Cache invalidation.** You noted a bug where inconsistent MCP tool ordering eliminated prompt cache effectiveness. How do you guard against cache invalidation in production? Is there monitoring for cache hit rates?

### On the Inner/Outer Harness Boundary

6. **User harness leverage.** Fowler distinguishes the inner harness (platform-built) from the outer harness (user-built). You said "the user's harness is where the most leverage lives." What outer harness patterns from your users surprised you most? What do the best users do that you didn't anticipate?

7. **AGENTS.md at scale.** You recommend ~100 lines as a map, not a manual. What happens when codebases grow to thousands of modules? Does the map scale, or does it need a different pattern?

---

## Day 3 - April 10 (Coding Agents + AI Architects): Harnesses in Production Code

### Morning Keynotes

| Time | Session | Room | What to Listen For |
|---|---|---|---|
| 9:20-9:40am | **David Soria Parra** | Keynote | Meta/PyTorch -- title TBA |
| 9:40-10:00am | **What Do Models Still Suck At?** (Peter Gostev) | Keynote | Real data on model failure modes. APEX-Agents showed 24% on professional tasks. What are the specific failure categories? These tell you what your harness must compensate for. |
| **10:00-10:10am** | **AgentCraft: Putting the Orc in Agent Orchestration** (Ido Salomon) | Keynote | Orchestration layer patterns |
| **10:10-10:30am** | **Building pi in a World of Slop** (Mario Zechner) | Keynote | Building a coding agent from scratch. What does "quality" mean when agents generate code? How does pi's harness differ from Codex's? |

### Expo Gap (10:30-11:15am)

| Time | Session | Room | Harness Layer |
|---|---|---|---|
| **10:30-10:48am** | **Benchmarking semantic code retrieval on Claude Code** | Wordsworth | Guides |

Claude Code plugin for semantic codebase search alongside grep/glob/BM25. Benchmark results comparing answer quality and token consumption. If Claude Code is your primary coding agent, this directly improves the Guides layer of YOUR outer harness. Listen for how retrieval quality affects downstream task success -- connect to the 6x performance gap finding.

### The 11:15am Decision: Context Lifecycle vs Skills Leverage

Two track keynotes compete:
- **Context Is the New Code** (Patrick Debois, Westminster, AI Architects track keynote)
- **Replacing 12K LoC with a 200 LoC Skill** (David Gomes, Fleming, Coding Agents track keynote)

**v4 recommendation: Patrick Debois.** Reasoning strengthened by the research:

Meta-Harness proved a 6x performance gap from harness/context changes alone. AutoHarness proved smaller model + harness > larger model. These findings mean **the system for managing context is more important than any individual context artifact**. Debois invented DevOps and coined the term. His talk frames context as a managed artifact with a lifecycle -- generate, evaluate, distribute, observe. This is exactly how the Guides layer should work: you don't just write CLAUDE.md files, you operate a system that keeps them current (Lopopolo's doc-gardening), tests them (Fowler's sensors), and versions them (git as state management).

Gomes's "12K LoC to 200 LoC" is the most dramatic skills proof point at the conference. But it proves that skills work -- a point the research already establishes. Debois will show you HOW to operationalize the Guides layer as infrastructure. That's the gap in most practitioners' understanding.

**If you disagree:** Gomes is the safe choice. You'll see a concrete case study with extreme quantitative results. Debois is the higher-variance, higher-ceiling choice.

### Coding Agents Track (Fleming room, 11:40am onward)

| Time | Session | Speaker(s) | Harness Layer | What to Listen For |
|---|---|---|---|---|
| **11:40am-12:00pm** | **A Piece of PI -- Embedding The OpenClaw Coding Agent** | Matthias Luebken | Execution Infra, Orchestration | Agent internals, composable primitives. How does PI's architecture compare to the Codex App Server (Items/Turns/Threads)? |
| **12:00-12:20pm** | **The Year of Latency Debt** | Sarah Chieng | All | When inference hits 1000+ tok/s, the harness changes. Smaller diffs, tighter feedback loops, less context switching. Connects to your "meta" objective about speed changing iteration patterns. Connects to Principle #4 (build to delete) -- speed invalidates complexity. |
| **12:20-12:40pm** | **Fighting AI with AI** | Lawrence Jones (incident.io) | Sensors, Orchestration, Verification | **KEY SESSION.** incident.io's AI SRE: deeply nested agent trees investigating production incidents. Evals with CLI + red-green runbooks. Filesystem downloads for trace inspection. 25 parallel agents for analysis. AI agents dogfooding their own tools. This is Principles #5 and #9 in production: verification as the lever, corrections cheaper than waiting. |
| **12:40-1:00pm** | **Factory Missions -- Super Long Running Agents** | Grinberg, Alvoeiro | Memory, Orchestration, Execution Infra | Long-running coding agent patterns. Connect to Anthropic's finding that "context anxiety" causes premature wrap-up, and to OPENDEV's event-driven system reminders that counter instruction fade-out. How do they maintain coherence over hours? |
| *Lunch* | | | | |
| **2:30-2:50pm** | **Your Coding Agent Should Do AI System Engineering** | Ben Burtenshaw (HF) | Guides, Sensors | Agent skills for CUDA kernels hitting 1.88x speedups on H100s. 1000+ ML experiments daily at HuggingFace without writing training scripts. This is the Guides layer (skills) applied to the hardest technical domain -- connecting to Phil Schmid's "captured trajectories are the competitive advantage." |
| **2:50-3:10pm** | **Let's Talk About FOMAT** | Michael Richman | Execution Infra | Monitoring and interacting with coding agents from anywhere. The control plane pattern. Connect to swyx's Authority dimension -- how do you maintain oversight without the "stutter-step agent" anti-pattern? |
| **3:10-3:30pm** | **Cooking with Agents in VS Code** | Liam Hampton | Execution Infra, Guides | VS Code agent integration patterns. How does the IDE harness differ from CLI harness? |

### Day 3 Highlights

**Fighting AI with AI (12:20, Lawrence Jones)** is the strongest harness engineering case study on Day 3. It demonstrates four principles operating together:
- Verification as the lever (Principle #5): CLI + red-green runbooks as computational sensors
- Corrections are cheap (Principle #9): 25 parallel agents analyzing instead of one careful human
- Errors left in (Principle #6): filesystem downloads serialize complex traces for AI analysis
- The repository as truth (Principle #7): structured feedback submitted as artifacts

**The Year of Latency Debt (12:00, Sarah Chieng)** challenges a hidden assumption in harness design. Current "best practices" (huge prompts, massive diffs, 10 parallel sessions) emerged when inference was slow. At 1000+ tok/s, smaller diffs + tighter feedback loops + less context switching become optimal. Your harness should adapt to speed. This connects directly to Principle #4 (build to delete) -- speed invalidates complexity.

### Lunch Break Options

| Time | Session | Room | Type |
|---|---|---|---|
| 1:25-1:43pm | **Stop babysitting your agents: context engine** (repeat) | Wesley | Expo |
| 1:45-2:03pm | **Comprehend First, Code Later** (Priscila Andre de Oliveira, Sentry) | Shelley | Expo |

The Sentry talk has data from 239 real messages showing comprehension > generation as the primary AI use in large codebases. This connects to Hashimoto's insight that "the negative space matters enormously -- knowing what agents are bad at and avoiding those tasks entirely produces outsized efficiency gains."

### End-of-Day Keynotes

| Time | Session | Room | What to Listen For |
|---|---|---|---|
| **4:30-4:50pm** | **Fireside Chat: Gergely Orosz + Tuomas Artman (Linear)** | Keynote | How Linear uses agents at scale. What does their harness look like? Linear is a developer tool company -- they're both building agents and using them to build. |
| **5:00-5:20pm** | **Agents need more than a chat** (Jacob Lauritzen) | Keynote | Agent UX beyond chat. Connect to the AI UX talk from Day 2. What interaction patterns emerge when agents are durable and resumable? |
| **5:20-5:40pm** | **The Friction Is Your Judgment** (Armin Ronacher + Cristina Poncela Cubeiro) | Keynote | Armin created Flask and co-founded Sentry. This is the human-harness boundary question. Where does automation stop and judgment begin? Connect to swyx's Authority dimension and Hashimoto's negative space insight. |

---

## The 3-Day Narrative

### Day 1: Build all six layers (hands-on)

You leave Day 1 having built:
- **Orchestration + Memory**: structured handoffs, adversarial evaluators, sprint contracts (9am)
- **Execution Infra + Orchestration**: event-sourced agent harness with replay/time-travel (10:40am)
- **Guides**: context engine for mergeable code with production data (1pm)
- **Sensors + Verification**: complete eval pipeline with computational + inferential controls (3:30pm)

### Day 2: Understand the discipline from its creators (talks)

You leave Day 2 understanding:
- **Why harness engineering exists**: Lopopolo keynote + AMA -- the OpenAI experience at scale
- **What the components are**: Tejas Kumar deep dive -- all six layers mapped
- **How it evolves autonomously**: Ostrikov -- harnesses that improve themselves via meta-agent loops
- **What it feels like in production**: Chess Coach (consumer), Justice AI (government) -- real constraints
- **What's still broken**: durable sessions (Christensen), memory hierarchies (Delucia), the fundamental question (Pocock, Gergely+swyx)

### Day 3: See harnesses applied to coding at scale (case studies + keynotes)

You leave Day 3 knowing:
- **How production teams do it**: incident.io (agents debugging agents), HuggingFace (1000+ daily experiments), Linear
- **What changes with speed**: latency debt paydown -- smaller diffs, tighter loops, less complexity
- **Where context systems live**: Debois's Context Development Lifecycle -- context as managed infrastructure
- **The human boundary**: comprehension > generation (Sentry data), friction as judgment (Ronacher)

---

## Post-Conference: The Hashimoto Journey

Mitchell Hashimoto's six-step adoption progression is the best framework for implementation. Each step is validated by the research. Implement in order -- skipping steps leads to frustration.

### Step 1: Drop the Chatbot (Week 1)

If you're still copy-pasting from ChatGPT, stop. Move to an agent with file access, program execution, and tool capabilities. Claude Code, Codex CLI, or Cursor -- any tool where the agent can read your repo, run commands, and modify files.

*Research backing: Willison -- "a coding agent is a piece of software that acts as a harness for an LLM." The chatbot has no harness.*

### Step 2: Reproduce Your Own Work (Week 1-2)

Do tasks manually, then fight the agent to match quality. This is excruciating but builds genuine expertise about what agents can and cannot do. Document every failure -- these become your future harness fixes.

*Research backing: Hashimoto -- "understanding when NOT to use an agent is as valuable as knowing when to." The negative space.*

### Step 3: Establish the Outer Harness (Week 2-3)

This is where conference knowledge applies. Build the outer harness (Fowler's term) for your codebase:

1. **CLAUDE.md / AGENTS.md** -- ~100 lines max (Lopopolo). A map pointing into structured docs, not a monolithic manual. Hand-written, not auto-generated (ETH Zurich). Machine-readable, co-located with code.
2. **Session initialization ritual** -- Agent must: read directory structure, review recent git log, check progress files, run sanity tests (Anthropic's startup sequence).
3. **Git as state management** -- Every session ends in a clean, committed state. Commit messages as structured logs (Anthropic).
4. **Linter + type checker as first sensors** -- Computational, deterministic, cheap (Fowler). Configure as pre-commit hooks. Include remediation instructions in lint messages for the agent to consume ("positive prompt injection").

*Research backing: Lopopolo -- "if it isn't discoverable in the repo, it effectively doesn't exist." Fowler -- build computational controls before inferential ones.*

### Step 4: End-of-Day Agents (Week 3-4)

Block the last 30 minutes daily to kick off:
- Research agents exploring code questions you didn't have time for
- Parallel exploration of alternative implementations
- Issue triage agents that categorize and draft responses

This creates a "warm start" the next morning. Turn off desktop notifications to prevent context-switching.

*Research backing: Hashimoto's progression. Anthropic's two-agent pattern (initializer creates the warm start for the coding agent).*

### Step 5: The Hashimoto Loop (Ongoing)

Every time an agent makes a mistake:
1. Diagnose: what class of error was it?
2. Fix: add a test, a lint rule, a CLAUDE.md instruction, or an architectural constraint
3. Verify: run the same task again and confirm the error class is eliminated
4. Remove what doesn't help: apply the Vercel lesson. If a rule or tool isn't measurably helping, remove it.

Track: first-pass merge rate, tokens per task, human correction rate, time to completion. These are your harness KPIs.

*Research backing: Hashimoto -- "every time the agent makes a mistake, engineer the environment so it can't make that mistake again." Vercel -- simpler harnesses work better. Anthropic -- "every component encodes an assumption about what the model can't do."*

### Step 6: Always Have an Agent Running (Month 2+)

Aim for constant background delegation. Hashimoto achieves 10-20% of working time with agents running. The key insight: work on manual tasks alongside agents. This counteracts skill atrophy because you're trading skill formation in delegated tasks for deeper skill formation in the tasks you keep.

*Research backing: Hashimoto -- "I actually see this as a benefit: I can focus more deeply on fewer things." swyx -- agent task reliability doubles every 3-7 months, so the set of delegatable tasks grows continuously.*

---

## Skills Narrative (Guides Layer Arc)

Skills are the **Guides layer** of the harness. The conference has a complete skills arc even in the harness-focused v4:

| # | Session | When | What You Learn |
|---|---|---|---|
| 1 | Skill Issue: Supabase (workshop, **alt**) | Apr 8, 9:00am | Write and eval skills with Braintrust |
| 2 | Skills at Scale (workshop, **alt**) | Apr 8, 10:40am | Make skills portable across Claude Code, Cursor, Codex |
| 3 | Mergeable by default (workshop) | Apr 8, 1:00pm | Build the context engine that delivers skills and docs |
| 4 | Skills issue: How skills evolve (Langfuse, **alt**) | Apr 9, 12:20pm | Eval and iterate skills in the wild |
| 5 | Combine Skills + MCP (Pedro, **alt**) | Apr 9, 3:10pm | Benchmark data on skills + MCP |
| 6 | Replacing 12K LoC with 200 LoC Skill (**alt** or attend) | Apr 10, 11:15am | Skills as extreme leverage |
| 7 | Your Coding Agent Should Do AI System Engineering | Apr 10, 2:30pm | Agent skills for CUDA, ML experiments at HF |

Items 3 and 7 are in the recommended schedule. Items 1, 2, 4, 5, 6 are alternatives you can swap in if skills are your bigger gap.

---

## Quick Reference: Top 12 Must-See Sessions

| # | Session | When | Harness Layer | Research Connection |
|---|---|---|---|---|
| 1 | How to Build Agents That Run for Hours (workshop) | Apr 8, 9:00am | Orchestration, Memory, Sensors | Anthropic's GAN-inspired pattern |
| 2 | Event-sourced agent harness (workshop) | Apr 8, 10:40am | Execution, Orchestration, Memory | OPENDEV's six-phase ReAct loop |
| 3 | Mergeable by default (workshop) | Apr 8, 1:00pm | Guides | Lopopolo's documentation-as-infrastructure |
| 4 | Ship Real Agents: Evals (workshop) | Apr 8, 3:30pm | Sensors, Verification | Fowler's computational vs inferential controls |
| 5 | **Harness Engineering keynote** (Lopopolo) | Apr 9, 9:50am | All (foundational) | The OpenAI harness engineering post, live |
| 6 | **Harness Engineering AMA** (Lopopolo) | Apr 9, 11:15am | All (Q&A) | Questions from Codex agent loop internals |
| 7 | Harnesses in AI: A Deep Dive (Tejas Kumar) | Apr 9, 2:30pm | All (deep dive) | Mapping all six layers |
| 8 | Self-Evolving AI Agents (Ostrikov) | Apr 9, 3:10pm | Sensors, Orchestration | Meta-Harness automated optimization |
| 9 | It Ain't Broke: Software Fundamentals (Pocock) | Apr 9, 5:20pm | Guides, Sensors | Principle #2: invariants not instructions |
| 10 | **Fighting AI with AI** (incident.io) | Apr 10, 12:20pm | Sensors, Orchestration, Verification | 4 principles in production |
| 11 | Factory Missions: Long Running Agents | Apr 10, 12:40pm | Memory, Orchestration | Anthropic's context anxiety finding |
| 12 | The Friction Is Your Judgment (Ronacher) | Apr 10, 5:20pm | Meta (human-harness boundary) | Hashimoto's negative space |

---

## Objectives Coverage Map

How each of your stated objectives maps to the v4 schedule:

| Objective | Sessions | Coverage |
|-----------|----------|----------|
| Write, evaluate, iterate on Agent Skills | Supabase workshop (alt), Skills at Scale (alt), Marc Klingen/Langfuse (alt), Ben Burtenshaw HF | Alt Day 1 + recommended Day 3 |
| Skills portable across tools | Skills at Scale workshop (alt) | Alt Day 1 |
| Demand-driven context discovery | DDC workshop (alt), Agentic Search (alt) | Alt Day 1 |
| Skills + MCP benchmarks | Pedro Rodrigues Day 2 (alt) | Alt Day 2 |
| Hierarchical memory / context management | Sally-Ann Delucia (recommended) | Recommended Day 2 |
| Context engine for mergeable code | Mergeable by default (recommended), Brandon Walsenuk expo (recommended) | Recommended Day 1 + Day 2 |
| Well-structured agent harness | Event-sourced harness (recommended), Agents That Run for Hours (recommended), Tejas Kumar (recommended) | Recommended Day 1 + Day 2 |
| State management / debug long-running agents | Event-sourced harness (recommended), Factory Missions (recommended), Year of Latency Debt (recommended) | Recommended Day 1 + Day 3 |
| Agent UX: durable sessions, resumable streaming | Why Your AI UX Is Broken (recommended), Agents need more than a chat keynote | Recommended Day 2 + Day 3 |
| Where harness and context engineering meet | Debois Context Is the New Code (recommended), Mergeable by default (recommended) | Recommended Day 1 + Day 3 |
| Skills as extreme leverage (12K to 200 LoC) | David Gomes (alt or attend at 11:15 if skip Debois) | Alt Day 3 |
| Production teams at scale | Fighting AI with AI (recommended), Chess Coach (recommended), Justice AI (recommended), Linear fireside (recommended) | Recommended Day 2 + Day 3 |
| Evaluation pipelines | Ship Real Agents workshop (recommended), Marc Klingen/Langfuse (alt) | Recommended Day 1 |
| Human side: comprehension > generation | Comprehend First/Code Later expo (recommended), Friction Is Your Judgment keynote (recommended) | Recommended Day 3 |
| 1000+ tok/s changes | Year of Latency Debt (recommended) | Recommended Day 3 |
| Software fundamentals + agent workflows | Matt Pocock keynote (recommended), Software Engineering + AI keynote (recommended) | Recommended Day 2 |

All 16 objectives are covered. 12 have recommended sessions; 4 are covered by alternatives you can swap in.

---

## v4 vs v3 vs v2: Summary of Changes

| Aspect | v2 | v3 | v4 |
|---|---|---|---|
| Primary lens | Context-first | Harness-first | Harness-first, research-validated |
| Day 1 1:00pm | (no slot) | Ralph Loops | **Mergeable by default** (context engine) |
| Day 1 coverage | Skills + DDC | 4 of 6 harness layers | **All 6 harness layers** |
| Day 2 3:10pm | Skills + MCP (Pedro) | Self-Evolving Agents | Self-Evolving Agents (confirmed by Meta-Harness research) |
| Day 3 11:15am | 12K LoC Skill (Gomes) | Context Is the New Code (Debois) | Debois (strengthened by 6x gap finding) |
| Pre-reading | Not included | 6 articles | **8 articles + 4 optional, with "what to look for" per source** |
| AMA questions | Not included | 3 example questions | **7 specific questions from Codex internals** |
| Post-conference | Not included | 4-week abstract plan | **Hashimoto's 6-step journey with research backing** |
| Session framing | By topic | By harness layer | **By harness layer + "what to listen for" + source connections** |
| Research depth | Conference descriptions only | Summaries of key sources | **Deep study of all 20+ sources** |
| Quantitative evidence | Minimal | Some | **13 quantitative findings throughout** |
| Objectives mapping | Implicit | Implicit | **Explicit coverage map** |
