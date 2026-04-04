# AI Engineer Europe 2026 - Personal Schedule

**Conference:** AI Engineer Europe 2026
**Dates:** April 8-10, 2026
**Venue:** Queen Elizabeth II Centre, London, UK
**Website:** https://ai.engineer/europe

## Focus Areas

- **Coding Agents** - building with and improving AI coding agents
- **Harness Engineering** - the orchestration layer around the LLM (agent loops, state management, tool execution, debugging)
- **Context Engineering** - getting the right information to the LLM at the right time (skills, memory, retrieval, knowledge curation)

## Relevant Tracks

The conference has 3 tracks directly aligned with these interests:

| Track | Day | Room |
|---|---|---|
| Context Engineering | April 9 | St. James |
| Harness Engineering | April 9 | Westminster |
| Coding Agents | April 10 | Fleming |

---

## Day 1 - April 8 (Workshops)

Day 1 is entirely hands-on workshops. No tracks assigned.

### Recommended Schedule

| Time | Workshop | Room | Focus |
|---|---|---|---|
| 9:00-10:20am | **How to Build Agents That Run for Hours (Without Losing the Plot)** | St. James | Harness |
| 10:40am-12:00pm | **Make your own event-sourced agent harness in 60 seconds** | Shelley | Harness |
| 1:00-3:00pm | **Mergeable by default: Building the context engine to save time and tokens** | Wordsworth | Context |
| 3:30-5:30pm | **Build Your First Demand-Driven Context Base** | Shelley | Context |

### Workshop Details

**How to Build Agents That Run for Hours** (Ash Prabaker, Andrew Wilson)
- Self-evaluation vs adversarial evaluator agents
- Context compaction vs structured handoffs
- Decomposing work into testable sprint contracts
- Traces as your primary debugging loop

**Make your own event-sourced agent harness** (Misha Kaletsky, Jonas Templestein)
- Effect-TS based agent harness where everything is an event
- Parallel tool execution, plugin hot-swapping
- Full replay and time-travel debugging
- Event sourcing for agent state

**Mergeable by default: Building the context engine** (Peter Werry)
- Building the reasoning layer that delivers organizational context to coding agents
- Reasoning across conflicting sources, maintaining permissions
- Personalizing results based on who's asking and what they're working on
- Lessons from production, including what went wrong

**Build Your First Demand-Driven Context Base** (Raj Navakoti)
- Let agents tell you what context is missing instead of guessing what to curate
- Uses Claude Code sub-agents and CLAUDE.md files
- DDC is to knowledge bases what TDD is to code
- Tested at IKEA Digital in production

### Strong Alternatives Per Slot

| Time | Alternative | Room | Why Consider |
|---|---|---|---|
| 9:00-10:20am | Agentic Search for Context Engineering | Wordsworth | Context-first approach to Day 1 |
| 9:00-10:20am | Codex and Subagents | Westminster | Hands-on with coding agents specifically |
| 10:40am-12:00pm | Skills at Scale | Abbey | Writing portable skills for Claude Code, Cursor, Codex |
| 10:40am-12:00pm | Playground in Prod (Samuel Colvin) | Westminster | Optimizing agents live in production |
| 1:00-3:00pm | Ralph Loops: Build Dumb AI Loops That Ship | Abbey | Simple but effective agent loops, less coverage elsewhere |
| 3:30-5:30pm | Ship Real Agents: Evals for Agentic Apps | Westminster | Eval pipeline using Claude Agent SDK |

---

## Day 2 - April 9 (Talks - Mixed Track Hopping)

Context Engineering and Harness Engineering run in parallel. Recommended schedule hops between the two rooms.

### Recommended Schedule

| Time | Session | Room | Track |
|---|---|---|---|
| 11:15-11:40am | **Harness Engineering AMA** (Ryan Lopopolo) | Westminster | Harness |
| 11:40am-12:00pm | **Nuno Campos** (Track Keynote, TBA) | St. James | Context |
| 12:00-12:20pm | **Hierarchical Memory: Context Management in Agents** (Sally-Ann Delucia) | St. James | Context |
| 12:20-12:40pm | **Building a Chess Coach** (Anant Dole, Asbjorn Steinskog) | Westminster | Harness |
| 12:40-1:00pm | **Building the Justice AI Unit** (Dan James) | Westminster | Harness |
| *Lunch* | | | |
| 2:30-2:50pm | **Harnesses in AI: A Deep Dive** (Tejas Kumar) | Westminster | Harness |
| 2:50-3:10pm | **Why Your AI UX Is Broken** (Mike Christensen) | Westminster | Harness |
| 3:10-3:30pm | **Self-Evolving AI Agents** (Alexey Ostrikov) | Westminster | Harness |
| 3:45-4:03pm | **RAG is dead, right??** (Expo Session) | Abbey | Expo |

Only 2 room changes required (both in the morning). Entire afternoon stays in Westminster.

### Session Highlights

**Hierarchical Memory** - Unix philosophy applied to agent memory. Composable primitives that make 200k tokens feel like 200 trillion.

**Self-Evolving AI Agents** - Meta-agent loop that autonomously rewrote its own system prompt over 80 generations. Won 1st place in international agent competition.

**Why Your AI UX Is Broken** - Durable sessions, resumable streaming, interruption patterns. The transport layer problem most teams are solving with fragile plumbing.

### 3:10pm Dilemma

Two strong talks compete at 3:10pm:
- **Self-Evolving AI Agents** (Ostrikov, Westminster) - Unique meta-agent pattern, nowhere else in conference
- **Combine Skills and MCP to Close the Context Gap** (Pedro Rodrigues, St. James) - Follows up his Day 1 Supabase workshop with benchmark data

Recommendation: Ostrikov, since Pedro's Day 1 workshop already covers the hands-on side.

---

## Day 3 - April 10 (Coding Agents Track)

Full day in the Coding Agents track (Fleming room). No hopping needed.

### Schedule

| Time | Session | Speaker(s) |
|---|---|---|
| 11:15-11:40am | **Replacing 12K LoC with a 200 LoC Skill** | David Gomes |
| 11:40am-12:00pm | **A Piece of PI - Embedding The OpenClaw Coding Agent In Your Product** | Matthias Luebken |
| 12:00-12:20pm | **The Year of Latency Debt (And How Big Tech Is Paying It Down)** | Sarah Chieng |
| 12:20-12:40pm | **Fighting AI with AI** | Lawrence Jones |
| 12:40-1:00pm | **Factory Missions - Super Long Running Agents** | Matan Grinberg, Luke Alvoeiro |
| *Lunch* | | |
| 2:30-2:50pm | **Your Coding Agent Should Do AI System Engineering** | Ben Burtenshaw |
| 2:50-3:10pm | **Let's Talk About FOMAT - Fear of Missing Agent Time** | Michael Richman |
| 3:10-3:30pm | **Cooking with Agents in VS Code** | Liam Hampton |

### Session Highlights

**Replacing 12K LoC with a 200 LoC Skill** - Skills as extreme leverage for coding agents.

**Fighting AI with AI** (Lawrence Jones, incident.io) - Using agents to debug agents at scale. Filesystem downloads for trace inspection, 25 parallel agents for analysis, AI-powered feedback loops.

**Your Coding Agent Should Do AI System Engineering** (Ben Burtenshaw, Hugging Face) - Agent-written CUDA kernels hitting 1.88x speedups on H100s. HF teams running 1000+ ML experiments daily without writing training scripts.

**The Year of Latency Debt** - 1000+ tok/s changes everything. Practical playbook for smaller diffs, automated feedback loops, and faster iteration.

---

## Key Concepts

### Harness Engineering vs Context Engineering

**Harness Engineering** = how the agent thinks and acts
- Agent loop structure (single loop, multi-agent, event-sourced)
- Tool execution (parallel, sequential, retries)
- State management across long-running tasks
- Evaluation and debugging (traces, evals)

**Context Engineering** = what the agent knows and sees
- System prompts, skills, CLAUDE.md files
- Retrieval (RAG, agentic search, MCP)
- Knowledge structure and curation
- Context discovery (demand-driven vs top-down)

They're complementary: a well-engineered harness enables better context engineering (e.g., sub-agents for context curation, structured handoffs carrying only relevant context).
