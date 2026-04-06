# Day 2 — April 9 (Wednesday)

**Conference:** AI Engineer Europe 2026
**Venue:** Queen Elizabeth II Centre, London, UK

---

## Morning Keynotes (Keynote Stage — all attend)

### 9:00 - 9:10am | Opening Address

### 9:10 - 9:30am | The New Application Layer

| | |
|---|---|
| **Speaker** | Malte Ubl |
| **Role** | CEO @ Vercel |
| **Type** | Keynote |

> **Why attend:** Vercel's own journey removing 80% of their agent's tools (d0 analytics agent) is one of the sharpest examples of "less tooling = more reliability." Malte will likely frame AI engineering as the successor discipline to web development. Listen for whether he talks about the prerequisite of a well-documented data layer — the Vercel blog showed that their tool removal only worked because the semantic layer was already legible.

### 9:30 - 9:50am | Keynote (title TBA)

| | |
|---|---|
| **Speaker** | Raia Hadsell |
| **Type** | Keynote |

### 9:50 - 10:10am | Harness Engineering: How to Build Software When Humans Steer and Agents Execute

| | |
|---|---|
| **Speaker** | Ryan Lopopolo |
| **Role** | Member of Technical Staff @ OpenAI |
| **Type** | Keynote |
| **Status** | **CHOSEN** |
| **Links** | [Twitter](https://x.com/_lopopolo) · [LinkedIn](https://www.linkedin.com/in/ryanlopopolo/) · [GitHub](https://github.com/lopopolo) |

> **Prepared context:** You've read the full OpenAI harness engineering post. Key concepts to listen for: the Types→Config→Repo→Service→Runtime→UI layering, AGENTS.md as ~100-line map (not manual), doc-gardening agents, entropy management / "garbage collection," and "corrections are cheap, waiting is expensive." The 5-month zero-handwritten-code case study (1M lines, ~1500 PRs, 3.5 PRs/engineer/day) is the grounding for everything. Ask yourself: does this generalize beyond OpenAI's internal product to a team shipping on existing codebases with tech debt?

### 10:10 - 10:30am | OpenClaw Update

| | |
|---|---|
| **Speaker** | Peter Steinberger |
| **Type** | Keynote |

---

## Break / Expo Sessions (10:30 - 11:08am)

### 10:30 - 10:48am | Wordsworth

**Stop Babysitting Your Agents: Building a Context Engine for Mergeable Code**

| | |
|---|---|
| **Speaker** | Brandon Walsenuk |
| **Type** | Expo Session |
| **Status** | **CHOSEN** |

> **Why:** The title is your entire thesis — context engines for mergeable code. Maps directly to your objective of making agents produce mergeable code in real codebases. Worth catching before the tracks begin.

---

## Track Sessions — Slot 1 (11:15 - 11:40am)

### SUGGESTED: 11:15 - 11:40am | Westminster — Harness Engineering AMA

| | |
|---|---|
| **Speaker** | Ryan Lopopolo |
| **Role** | Member of Technical Staff @ OpenAI |
| **Type** | Track Keynote |
| **Track** | Harness Engineering |
| **Status** | **SUGGESTED** |
| **Links** | [Twitter](https://x.com/_lopopolo) · [LinkedIn](https://www.linkedin.com/in/ryanlopopolo/) · [GitHub](https://github.com/lopopolo) |

> **Prepared questions from reading:**
> 1. The OpenAI post says AGENTS.md should be ~100 lines as a map. The ETH Zurich AGENTbench study found human-written context files help only ~4% and increase token cost by ~19%. How do you reconcile this — is the value in the file itself or in the progressive disclosure structure it points to?
> 2. "Corrections are cheap, waiting is expensive" works at 3.5 PRs/engineer/day. What's the minimum throughput where this philosophy becomes responsible vs. reckless?
> 3. The Codex agent loop article shows prompt construction with 5 ordered layers and prefix stability for cache hits. How much of the merge rate improvement comes from the harness architecture vs. from prompt caching reducing cost enough to run more iterations?
> 4. Doc-gardening agents for entropy management — what's the failure rate? Do they ever introduce drift themselves?
> 5. Your team favored "boring, composable" dependencies well-represented in training data. How do you handle proprietary internal libraries that aren't in training data?

#### Alternatives in this slot

| Room | Talk | Speaker | Track | Relevance |
|---|---|---|---|---|
| St. James | (title TBA) | Maggie Appleton | Context Engineering | Could be excellent — Maggie is a strong thinker on information architecture |
| Moore | Why building eval platforms is hard | Phil Hetzel | Evals & Observability | Relevant to measuring improvement, but you'll see Hetzel in expo sessions too |

---

## Track Sessions — Slot 2 (11:40am - 12:00pm)

### SUGGESTED: 11:40am - 12:00pm | Moore

**LLM Codegen Fails and How to Stop 'Em**

| | |
|---|---|
| **Speaker** | Danilo Campos |
| **Type** | Talk |
| **Track** | Evals & Observability |
| **Status** | **SUGGESTED** |

> **Why:** This directly answers your question "What separates an agent run that ships clean code from one that spirals?" The Anthropic long-running agents post cataloged the exact failure modes (over-ambition, premature completion, testing gaps). Manus showed that errors left in context outperform clean retries. Breunig's four context failure modes (poisoning, distraction, confusion, clash) are the theoretical frame. Danilo likely has practical countermeasures. Filter through: does he show real codebase results or clean demos?

#### Alternatives in this slot

| Room | Talk | Speaker | Track | Relevance |
|---|---|---|---|---|
| St. James | (title TBA) | Nuno Campos | Context Engineering | LangChain co-founder. Given their "Anatomy of an Agent Harness" post (Ralph Loop, filesystem as primitive, context rot countermeasures), likely a deep technical talk. **Strong alternative.** |

---

## Track Sessions — Slot 3 (12:00 - 12:20pm)

### SUGGESTED: 12:00 - 12:20pm | St. James

**Hierarchical Memory: Context Management in Agents**

| | |
|---|---|
| **Speaker** | Sally-Ann Delucia |
| **Type** | Talk |
| **Track** | Context Engineering |
| **Status** | **SUGGESTED** |

> **Why:** Directly maps to your objective: "How should agent memory and context be structured?" You've now seen multiple memory patterns — Manus's todo-list recitation against lost-in-the-middle, Anthropic's `claude-progress.txt` for cross-session handoff, LangChain's write/select/compress/isolate framework, the filesystem as externalized memory. Sally-Ann's "bottom-up composable" framing suggests a practical taxonomy. Listen for: does the hierarchy map onto your harness (what lives in skills, what lives in AGENTS.md, what lives in agent-managed files)?

#### Alternatives in this slot

| Room | Talk | Speaker | Track | Relevance |
|---|---|---|---|---|
| Westminster | What the Best Agents Share (lightning) + Why (Senior) Engineers Struggle to Build AI Agents (lightning) | Mardu Swanepoel + Philipp Schmid | Harness Engineering | Two talks in 20 min. Swanepoel covers patterns across Harvey, Cursor, Manus, OpenAI. Schmid is AWS/HuggingFace. **Good if you want breadth over depth.** |

---

## Track Sessions — Slot 4 (12:20 - 12:40pm)

### SUGGESTED: 12:20 - 12:40pm | Moore

**Skill Issue: Lessons from Skilling Up Coding Agents to Use Langfuse**

| | |
|---|---|
| **Speaker** | Marc Klingen |
| **Type** | Talk |
| **Track** | Evals & Observability |
| **Status** | **SUGGESTED** |

> **Why:** This is the most direct answer to your objective: "How do I get good at writing skills? What makes a skill effective vs. bloated?" Marc runs Langfuse and ships skills regularly. The HumanLayer "Skill Issue" post described progressive disclosure via skills and the "dumb zone" — too many tools push you into degraded performance. The ETH Zurich study showed LLM-generated context files hurt. Marc likely has real data on what makes skills work. Also maps to: "Skills, MCP, and harness engineering as a stack."

#### Alternatives in this slot

| Room | Talk | Speaker | Track | Relevance |
|---|---|---|---|---|
| Fleming | Lobster Trap: OpenClaw in Containers from Local to K8s | Sally Ann O'Malley | Claws & Personal Agents | Containerizing agent setups — relevant if you want reproducible harness environments |

---

## Track Sessions — Slot 5 (12:40 - 1:00pm)

### SUGGESTED: 12:40 - 1:00pm | Moore

**The Art & Science of Benchmarking Agents**

| | |
|---|---|
| **Speaker** | Vincent Chen |
| **Type** | Talk |
| **Track** | Evals & Observability |
| **Status** | **SUGGESTED** |

> **Why:** Maps to your objective: "How do I know if changes to my harness or context setup are actually making things better, or if I'm just chasing vibes?" The ETH Zurich AGENTbench study showed that the gap between recommendations and measured outcomes is real. The Meta-Harness paper demonstrated a 6x performance gap from harness changes alone. You need a framework for measuring merge rate, token cost, and review cycles — not building eval pipelines for products you ship. Listen for: does this cover coding agent benchmarks specifically, or is it general agent eval?

#### Alternatives in this slot

| Room | Talk | Speaker | Track | Relevance |
|---|---|---|---|---|
| Westminster | Building the Justice AI Unit: Shipping Production AI Inside Government | Dan James | Harness Engineering | Production AI at scale in government — interesting but about building AI products for citizens, not using coding agents |
| St. James | What Breaks When You Build AI Under Sovereignty Constraints | Bilge Yücel | Context Engineering | Regulatory constraints on AI architecture — not directly relevant |

---

## Lunch (1:00 - 2:30pm)

### Expo Sessions Worth Catching

#### SUGGESTED: 1:05 - 1:23pm | Wordsworth

**The Maturity Phases of Running Evals**

| | |
|---|---|
| **Speaker** | Phil Hetzel |
| **Type** | Expo Session |
| **Status** | **SUGGESTED** |

> **Why:** Complements the benchmarking talk. Maps to measuring improvement. Phil also speaks about eval platforms in the morning slot — this is the practical how-to version.

#### CHOSEN: 1:25 - 1:43pm | Wesley

**Untethered Productivity**

| | |
|---|---|
| **Type** | Expo Session |
| **Status** | **CHOSEN** |

> **Why:** The single most on-objective expo session of the day for the "daily workflow with coding agents" goal. The speaker rebuilt their workflow around voice-dictating briefs at 179 WPM, dispatching agents to isolated git worktrees, walking away from the laptop, and reviewing diffs through a hardened CI pipeline that catches agent mistakes before merge. This is the personal-workflow version of what Joshua Snyder describes at the systems level later in the day. Maps directly to: "What does the full daily workflow look like — from a vague requirement to merged code." Spotify Honk-flavored (worktrees + hardened CI as the verification gate) and the operational expression of Hashimoto's "always have an agent running."

#### 1:45 - 2:03pm | Shelley

**BDD, ADR, PRD, WTF: Capturing Decisions for Humans and AI Alike**

| | |
|---|---|
| **Type** | Expo Session |
| **Status** | **CHOSEN** |

> **Why:** Directly about making Codex and Claude Code productive by capturing architectural decisions. Maps to Lopopolo's `docs/` structure (design-docs, exec-plans) and Fowler's "guides as feedforward." The title suggests practical patterns for decision artifacts that serve both human and agent consumption.

---

## Track Sessions — Slot 6 (2:30 - 2:50pm)

### SUGGESTED: 2:30 - 2:50pm | Westminster

**Harnesses in AI: A Deep Dive**

| | |
|---|---|
| **Speaker** | Tejas Kumar |
| **Type** | Talk |
| **Track** | Harness Engineering |
| **Status** | **SUGGESTED** |

> **Why:** By this point you've seen Lopopolo's keynote + AMA. Tejas likely offers a different angle on the same topic. Cross-reference with Fowler's taxonomy (guides vs. sensors, computational vs. inferential, three harness types) and Anthropic's GAN-inspired generator/evaluator split. Listen for: does Tejas present patterns you haven't seen, or does he confirm the Fowler/OpenAI/Anthropic convergence?

#### Alternatives in this slot

| Room | Talk | Speaker | Track | Relevance |
|---|---|---|---|---|
| St. James | Connecting the Dots with Context Graphs | Stephen Chin | Context Engineering | Graph-structured context — different paradigm from file-based. Worth it if you want to explore beyond filesystem-as-context |
| Moore | Evals Are Broken, Use Them Anyway | Ara Khan | Evals & Observability | Pragmatic eval guidance. **Strong alternative** if the morning benchmarking talk left you wanting more on measurement |

---

## Track Sessions — Slot 7 (2:50 - 3:10pm)

### SUGGESTED: 2:50 - 3:10pm | Moore

**Self Driving Products: Engineering the Pipeline from Product Signals to Pull Requests**

| | |
|---|---|
| **Speaker** | Joshua Snyder |
| **Type** | Talk |
| **Track** | Evals & Observability |
| **Status** | **SUGGESTED** |

> **Why:** Maps directly to your objective: "What does the full daily workflow look like — from a vague requirement to merged code — when coding agents do the implementation?" This talk covers the end-to-end pipeline from product signals (rage-clicks, error spikes, experiment results) to automated PRs. Hashimoto's journey ended at "always have an agent running" — Snyder seems to be describing the infrastructure that makes that possible. Listen for: is this running on production codebases with real tech debt?

#### Alternatives in this slot

| Room | Talk | Speaker | Track | Relevance |
|---|---|---|---|---|
| Westminster | Why Your AI UX Is Broken | Mike Christensen | Harness Engineering | About AI interfaces. Less relevant — you're not building AI UX |
| St. James | Context Graphs for Explainable, Decision-Aware AI Agents | Andreas Kollegger, Zaid Zaim | Context Engineering | Neo4j-backed context. Interesting if context graphs appeal after Stephen Chin's talk |

---

## Track Sessions — Slot 8 (3:10 - 3:30pm)

### SUGGESTED: 3:10 - 3:30pm | St. James

**Combine Skills and MCP to Close the Context Gap**

| | |
|---|---|
| **Speaker** | Pedro Rodrigues |
| **Type** | Talk |
| **Track** | Context Engineering |
| **Status** | **SUGGESTED** |

> **Why:** This is the single most targeted talk for your objectives. You asked: "When should context live in a skill vs. behind an MCP server? What does the data show about using both together vs. either alone?" Pedro's talk is literally about combining skills and MCP. The Spotify Honk posts showed they prefer MCP for verification tools (because they work across thousands of repos) but static prompts for context. The HumanLayer post showed MCP can duplicate CLI functionality poorly. The Manus post showed why dynamic tool changes break KV-cache. Pedro likely has a framework for when to use which. **Do not miss this one.**

#### Alternatives in this slot

| Room | Talk | Speaker | Track | Relevance |
|---|---|---|---|---|
| Moore | SWE-rebench: Lessons from Evaluating Coding Agents on Real Software Engineering Tasks | Ibragim Badertdinov | Evals & Observability | Real-world coding agent evaluation. **Very strong alternative** — maps to measuring improvement. If you're confident on skills/MCP already, this may be higher value |
| Westminster | Self-Evolving AI Agents: Lessons from Winning an Agent Competition | Alex Ostrikov | Harness Engineering | Competition results — interesting but less applicable to production codebases |

---

## Expo Sessions (3:45 - 4:23pm)

### SUGGESTED: 3:45 - 4:03pm | Shelley

**How Agent O11y Differs from Traditional O11y**

| | |
|---|---|
| **Speaker** | Phil Hetzel |
| **Type** | Expo Session |

> **Why:** You want to measure whether your harness is working. Agent observability is the infrastructure for that. Connects to Anthropic's insight about needing rich execution traces (not summaries) and the Meta-Harness paper's finding that the proposer needs raw traces to do credit assignment.

#### Alternatives in this slot

| Room | Talk | Speaker | Relevance |
|---|---|---|---|
| Wordsworth | Why Rust is the Ideal Language for Vibe-Coding | Daniel Szoke (Sentry) | Maps to Fowler's *harnessability* thesis — strong typing and clearly definable module boundaries are what make mechanical verification (and therefore effective harnesses) possible. Previews Matt Pocock's 5:20pm keynote. Less directly actionable than Hetzel but conceptually load-bearing |
| Wesley | From Writing Code to Designing Systems: How the Developer Role Has Changed | (TBA) | Explicitly covers `agents.md`, GitHub Copilot CLI, structuring projects for agent-driven dev, and "how to ensure architectural consistency across dozens of moving parts." More practical than the title suggests — the developer-role-as-system-designer framing maps directly to your harness setup work |

---

## Afternoon Keynotes (Keynote Stage — all attend)

### 4:30 - 5:00pm | Software Engineering + AI = ?

| | |
|---|---|
| **Speakers** | Gergely Orosz, swyx |
| **Type** | Keynote |

> **Why attend:** Gergely (The Pragmatic Engineer) brings the skeptical senior-engineer perspective. swyx developed the IMPACT framework (Intent, Memory, Planning, Authority, Control flow, Tools) and frames "Authority" as the oldest unsolved problem in agents. This panel will likely address: where does human judgment add the most leverage? Connects to Hashimoto's skill formation concerns and Fowler's insight that the human's implicit harness (absorbed conventions, aesthetic judgment, organizational memory) is irreplaceable.

### 5:00 - 5:20pm | Keynote (title TBA)

| | |
|---|---|
| **Speaker** | Kitze |
| **Type** | Keynote |

### 5:20 - 5:40pm | It Ain't Broke: Why Software Fundamentals Matter More Than Ever

| | |
|---|---|
| **Speaker** | Matt Pocock |
| **Type** | Keynote |

> **Why attend:** Counter-narrative to the "agents write all code" thesis. Fowler's article emphasized "harnessability" — strong typing and clearly definable module boundaries make harnesses possible. Pocock (TypeScript educator) likely argues that software fundamentals are the prerequisite for effective agent use, not a relic. This is Hashimoto's "verification is the single biggest lever" from the language/framework angle.

### 5:40 - 6:00pm | Keynote (title TBA)

| | |
|---|---|
| **Speaker** | Sunil Pai |
| **Type** | Keynote |

---

## Summary: Your Day 2 Path

| Time | Room | Session | Status |
|---|---|---|---|
| 9:00-10:30am | Keynote | All morning keynotes (incl. Lopopolo) | **CHOSEN** |
| 10:30-10:48am | Wordsworth | Stop Babysitting Your Agents | **CHOSEN** |
| 11:15-11:40am | Westminster | Harness Engineering AMA (Lopopolo) | Suggested |
| 11:40-12:00pm | Moore | LLM Codegen Fails (Danilo Campos) | Suggested |
| 12:00-12:20pm | St. James | Hierarchical Memory (Sally-Ann Delucia) | Suggested |
| 12:20-12:40pm | Moore | Skill Issue (Marc Klingen) | Suggested |
| 12:40-1:00pm | Moore | Benchmarking Agents (Vincent Chen) | Suggested |
| 1:05-1:23pm | Wordsworth | Maturity Phases of Evals (Phil Hetzel) | Suggested |
| 1:25-1:43pm | Wesley | Untethered Productivity | **CHOSEN** |
| 1:45-2:03pm | Shelley | BDD, ADR, PRD, WTF | **CHOSEN** |
| 2:30-2:50pm | Westminster | Harnesses in AI (Tejas Kumar) | Suggested |
| 2:50-3:10pm | Moore | Self Driving Products (Joshua Snyder) | Suggested |
| 3:10-3:30pm | St. James | Skills + MCP (Pedro Rodrigues) | Suggested |
| 3:45-4:03pm | Shelley | Agent O11y (Phil Hetzel) | Suggested |
| 4:30-6:00pm | Keynote | All afternoon keynotes | All attend |

### Hardest trade-offs of the day

1. **3:10pm — Pedro Rodrigues vs. SWE-rebench (Badertdinov).** Pedro answers your skills/MCP question directly. SWE-rebench answers your measurement question. If you feel confident on skills/MCP from the Marc Klingen talk and reading, swap to SWE-rebench.

2. **11:40am — Danilo Campos vs. Nuno Campos.** Both are strong. Danilo is concrete failure modes; Nuno (LangChain) is likely deeper on context architecture. If Maggie Appleton's talk at 11:15 (which you'll miss for Lopopolo AMA) covered context engineering foundations, Nuno may be redundant.

3. **2:30pm — Tejas Kumar vs. Ara Khan.** If the morning sessions satisfied your harness curiosity, swap to Ara Khan's "Evals Are Broken, Use Them Anyway" for more measurement depth.
