# AI Engineer Europe 2026 - Personal Schedule v2

**Conference:** AI Engineer Europe 2026
**Dates:** April 8-10, 2026
**Venue:** Queen Elizabeth II Centre, London, UK
**Website:** https://ai.engineer/europe

## Focus Areas

- **Coding Agents** - using AI agents to produce code, agent-assisted development workflows
- **Harness Engineering** - the orchestration layer around the LLM (agent loops, state management, tool execution, debugging, evals)
- **Context Engineering** - getting the right information to the LLM at the right time (skills, memory, retrieval, knowledge curation, CLAUDE.md, MCP)

## Key Tracks

| Track | Day | Room |
|---|---|---|
| Context Engineering | April 9 | St. James |
| Harness Engineering | April 9 | Westminster |
| Evals & Observability | April 9 | Moore |
| Coding Agents | April 10 | Fleming |

---

## Day 1 - April 8 (Workshops)

Full workshop day. 3 time slots. Pick one workshop per slot.

### Recommended Schedule

| Time | Workshop | Room | Speaker(s) | Focus |
|---|---|---|---|---|
| 9:00-10:20am | **Skill Issue: How We Used AI to Make Agents Actually Good at Supabase** | Abbey | Pedro Rodrigues | Context + Evals |
| 10:40am-12:00pm | **Skills at Scale** | Abbey | Nick Nisi, Zack Proser | Context |
| *Lunch break* | | | | |
| 3:30-5:30pm | **Build Your First Demand-Driven Context Base** | Shelley | Raj Navakoti | Context |

### Why This Combination

**Morning arc: Skills mastery.** The 9am Supabase workshop teaches you to write, eval, and iterate on Agent Skills with a real eval harness (Braintrust). The 10:40am Skills at Scale workshop extends that -- writing portable skills that work across Claude Code, Cursor, and Codex. Same room (Abbey), no moving. By lunch you have hands-on experience writing, testing, and distributing skills.

**Afternoon: Context discovery.** The DDC workshop from Raj Navakoti (IKEA Digital) flips the paradigm -- instead of guessing what context agents need, you let agents tell you what's missing. Uses Claude Code sub-agents and CLAUDE.md files directly. This is the most practical "context engineering from scratch" session at the conference.

### Alternatives Per Slot

| Time | Alternative | Room | Trade-off |
|---|---|---|---|
| 9:00-10:20am | **How to Build Agents That Run for Hours** | St. James | Harness-first start: adversarial evaluators, structured handoffs, trace debugging. Pick this if you want harness depth over skills depth. |
| 9:00-10:20am | **Codex and Subagents** | Westminster | Hands-on with OpenAI's coding agent. Pick if you want direct coding agent experience. |
| 9:00-10:20am | **Agentic Search for Context Engineering** | Wordsworth | RAG-to-agentic-search evolution, building retrieval tools. More retrieval-focused. |
| 10:40am-12:00pm | **Make your own event-sourced agent harness** | Shelley | Effect-TS harness with replay/time-travel debugging. Pick for deep harness internals. |
| 10:40am-12:00pm | **Playground in Prod** (Samuel Colvin) | Westminster | Live agent optimization with Pydantic AI + GEPA auto-evolution. Production-focused. |
| 3:30-5:30pm | **Ship Real Agents: Evals for Agentic Apps** | Westminster | Full eval pipeline with Claude Agent SDK. Pick if you want evals depth over context depth. |

### Decision Framework

Your main interest is *using coding agents to produce code* and *improving them via harness + context engineering*. Context engineering (skills, knowledge curation) is the higher-leverage starting point because it's what you control day-to-day. Harness engineering matters but is more framework-level. So the recommended Day 1 leans context-heavy, with harness alternatives if you want balance.

---

## Day 2 - April 9 (Talks)

### Recommended Schedule

#### Morning Keynotes (everyone in the Keynote room)

| Time | Session | Room | Type |
|---|---|---|---|
| 9:00-9:10am | Opening Address | Keynote | Keynote |
| 9:10-9:50am | Morning keynotes (Malte Ubl, Raia Hadsell) | Keynote | Keynote |
| **9:50-10:10am** | **Harness Engineering: How to Build Software When Humans Steer and Agents Execute** (Ryan Lopopolo) | Keynote | **MUST SEE** |
| 10:10-10:30am | OpenClaw update (Peter Steinberger) | Keynote | Keynote |

**Ryan Lopopolo's keynote** defines the harness engineering concept for the whole conference. Everything in the Harness Engineering track on Day 2 builds on this talk. Do not miss it.

#### Expo Gap (10:30-11:15am)

| Time | Session | Room | Type |
|---|---|---|---|
| 10:30-10:48am | **Stop babysitting your agents: building a context engine for mergeable code** (Brandon Walsenuk) | Wordsworth | Expo |

This fills the gap before tracks start. Real case study: same agent, same model -- with context engine: 25 min + 10.8M tokens, mergeable on first pass. Without: 2.5 hours + 20.9M tokens. Directly relevant to making coding agents produce better code.

#### Track Sessions (11:15am onward)

| Time | Session | Room | Track |
|---|---|---|---|
| **11:15-11:40am** | **Harness Engineering AMA** (Ryan Lopopolo) | Westminster | Harness |
| **12:00-12:20pm** | **Hierarchical Memory: Context Management in Agents** (Sally-Ann Delucia) | St. James | Context |
| **12:20-12:40pm** | **Skills issue: How agent skills get written, evaluated and improved** (Marc Klingen, Langfuse) | Moore | Evals |
| *Lunch* | | | |
| **2:30-2:50pm** | **Harnesses in AI: A Deep Dive** (Tejas Kumar) | Westminster | Harness |
| **2:50-3:10pm** | **Context Graphs for Explainable, Decision-Aware AI Agents** (Kollegger, Zaim) | St. James | Context |
| **3:10-3:30pm** | **Combine Skills and MCP to Close the Context Gap** (Pedro Rodrigues) | St. James | Context |

#### End-of-Day Keynotes

| Time | Session | Room | Why |
|---|---|---|---|
| **4:30-5:00pm** | **Software Engineering + AI = ?** (Gergely Orosz + swyx) | Keynote | The meta-question for your interests |
| **5:20-5:40pm** | **It Ain't Broke: Why Software Fundamentals Matter More Than Ever** (Matt Pocock) | Keynote | TDD, vertical slices, ubiquitous language applied to AI agent workflows |

### Room Hopping Map

```
9:00  ----[Keynote]----
9:50  Ryan Lopopolo keynote (HARNESS)
10:30 ----[Wordsworth expo]---- context engine talk
11:15 ----[Westminster]---- Harness AMA
11:40 (break / hallway)
12:00 ----[St. James]---- Hierarchical Memory
12:20 ----[Moore]---- Skills evals (Langfuse)
12:40 LUNCH
2:30  ----[Westminster]---- Harnesses Deep Dive
2:50  ----[St. James]---- Context Graphs
3:10  (stay in St. James) Skills + MCP
3:30  (break)
4:30  ----[Keynote]---- Gergely + swyx
5:20  (stay in Keynote) Matt Pocock
```

4 room changes total. Afternoon is just Westminster -> St. James (stay) -> Keynote (stay).

### 3:10pm Decision (Changed from v1)

v1 recommended Self-Evolving AI Agents (Ostrikov) over Pedro's Skills+MCP talk. **v2 flips this.** Rationale: Pedro's workshop on Day 1 teaches you to *write* skills. His Day 2 talk shows the *benchmark results* of how skills + MCP combine in production. That's the complete loop. Plus, you now have the Langfuse "skills in the wild" talk at 12:20 for a third perspective. This creates a **skills narrative arc** across all 3 days:

1. Day 1 AM: Write and eval skills (Pedro workshop)
2. Day 1 AM: Make skills portable (Skills at Scale workshop)
3. Day 2 12:20: How skills evolve in the wild (Langfuse)
4. Day 2 3:10: Skills + MCP benchmark results (Pedro talk)
5. Day 3 11:15: Replacing 12K LoC with a 200 LoC Skill (David Gomes)
6. Day 3 2:30: Agent skills for systems engineering (HuggingFace)

### Day 2 Alternatives

| Time | Alternative | Instead of | Why Consider |
|---|---|---|---|
| 11:40am-12:00pm | Nuno Campos track keynote | (gap) | If announced -- Nuno is a LangChain core contributor |
| 2:50-3:10pm | **Why Your AI UX Is Broken** (Christensen) | Context Graphs | If you want agent UX patterns over knowledge graphs |
| 3:10-3:30pm | **SWE-rebench** (Badertdinov) in Moore | Pedro's talk | If you want coding agent benchmarking data instead |
| 3:45-4:03pm | **Why Rust is the Ideal Language for Vibe-Coding** | (gap before keynotes) | Rust's compiler as an agent feedback loop -- unique angle |

---

## Day 3 - April 10 (Coding Agents Track + Keynotes)

### Morning Keynotes

| Time | Session | Room | Why |
|---|---|---|---|
| 9:20-9:40am | **David Soria Parra** | Keynote | Meta/PyTorch -- title TBA, worth checking closer to date |
| **10:10-10:30am** | **Building pi in a World of Slop** (Mario Zechner) | Keynote | Building a coding agent from scratch, OSS sustainability with agents |

### Expo Gap (10:30-11:15am)

| Time | Session | Room | Type |
|---|---|---|---|
| **10:30-10:48am** | **Benchmarking semantic code retrieval on Claude Code** | Wordsworth | Expo |

This is directly about improving Claude Code's code search with semantic retrieval. Benchmark results comparing answer quality and token consumption. Extremely relevant if Claude Code is your primary coding agent.

### Coding Agents Track (Fleming room, 11:15am onward)

| Time | Session | Speaker(s) | Notes |
|---|---|---|---|
| **11:15-11:40am** | **Replacing 12K LoC with a 200 LoC Skill** | David Gomes | Skills as extreme leverage |
| **11:40am-12:00pm** | **A Piece of PI -- Embedding The OpenClaw Coding Agent** | Matthias Luebken | Agent internals, composable primitives |
| 12:00-12:20pm | The Year of Latency Debt | Sarah Chieng | 1000+ tok/s changes iteration patterns |
| 12:20-12:40pm | Fighting AI with AI | Lawrence Jones | Agents debugging agents at incident.io |
| 12:40-1:00pm | Factory Missions -- Super Long Running Agents | Grinberg, Alvoeiro | Long-running coding agent patterns |
| *Lunch* | | | |
| **2:30-2:50pm** | **Your Coding Agent Should Do AI System Engineering** | Ben Burtenshaw (HF) | Agent skills for CUDA, ML experiments |
| 2:50-3:10pm | Let's Talk About FOMAT | Michael Richman | Agent time management |
| 3:10-3:30pm | Cooking with Agents in VS Code | Liam Hampton | VS Code agent integration |

### Lunch Break Option (1:25-1:43pm)

| Time | Session | Room | Type |
|---|---|---|---|
| 1:25-1:43pm | **Stop babysitting your agents: building a context engine** (repeat) | Wesley | Expo |
| 1:45-2:03pm | **Comprehend First, Code Later** (Priscila Andre de Oliveira, Sentry) | Shelley | Expo |

If you missed the context engine talk on Day 2, catch the repeat. The Sentry talk is also interesting -- data from 239 real messages showing comprehension > generation as the primary AI use in large codebases.

### Day 3 Dilemma: 11:15am

Two talks compete:
- **Replacing 12K LoC with a 200 LoC Skill** (Fleming) -- Coding Agents track keynote
- **Context Is the New Code** (Patrick Debois, Westminster) -- Context Development Lifecycle, versioning context like code

**Recommendation: Stay in Fleming.** Debois's talk is conceptual/strategic ("context deserves CI/CD"). Gomes's talk is the concrete proof that skills are the highest-leverage tool for coding agents. Given your interest in *using* coding agents, the practical win outweighs the strategic framing. But if you're leading a team, Debois might matter more.

### End-of-Day Keynotes

| Time | Session | Room | Why |
|---|---|---|---|
| **4:30-4:50pm** | Fireside Chat: Gergely Orosz + Tuomas Artman (Linear) | Keynote | How Linear uses agents |
| **5:20-5:40pm** | **The Friction Is Your Judgment** (Armin Ronacher + Cristina Poncela Cubeiro) | Keynote | Armin created Flask/Sentry -- perspective on agent-human balance |

---

## The 3-Day Narrative

This schedule builds a deliberate arc:

### Day 1: Learn to build the inputs
- **Skills**: write them, test them, distribute them across tools
- **Context bases**: let agents discover what they need (DDC)

### Day 2: Understand the architecture
- **Harness engineering**: how the agent loop works, structured handoffs, event sourcing
- **Context engineering**: hierarchical memory, context graphs, skills + MCP integration
- **Evals**: how to know if any of this actually works

### Day 3: See it applied to coding
- **Skills in production**: 12K LoC -> 200 LoC, CUDA kernels, ML experiments
- **Coding agent internals**: pi/OpenClaw, long-running agents, semantic retrieval
- **The human side**: comprehension over generation, judgment over automation

By Day 3, you'll have both the theory (how harnesses and context work) and the practice (how to write skills, set up evals, structure knowledge) to improve your own coding agent workflows.

---

## Quick Reference: Top 10 Must-See Sessions

| # | Session | When | Why |
|---|---|---|---|
| 1 | Skill Issue (Supabase workshop) | Apr 8, 9:00am | Hands-on skill writing + eval harness |
| 2 | Build Your First DDC Base | Apr 8, 3:30pm | Agent-driven context discovery with Claude Code |
| 3 | Harness Engineering keynote (Lopopolo) | Apr 9, 9:50am | Defines the field |
| 4 | Harness Engineering AMA | Apr 9, 11:15am | Deep Q&A on the keynote concepts |
| 5 | Hierarchical Memory | Apr 9, 12:00pm | Unix philosophy for agent context management |
| 6 | Combine Skills and MCP | Apr 9, 3:10pm | Benchmark data on skills + MCP in production |
| 7 | Matt Pocock keynote | Apr 9, 5:20pm | Software fundamentals + AI agent workflows |
| 8 | Benchmarking semantic retrieval on Claude Code | Apr 10, 10:30am | Direct Claude Code improvement data |
| 9 | Replacing 12K LoC with a 200 LoC Skill | Apr 10, 11:15am | Skills as extreme leverage for coding agents |
| 10 | Your Coding Agent Should Do AI System Engineering | Apr 10, 2:30pm | HuggingFace's agent skills for hard systems tasks |
