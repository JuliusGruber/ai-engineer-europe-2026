# Day 3 — April 10 (Friday)

**Conference:** AI Engineer Europe 2026
**Venue:** Queen Elizabeth II Centre, London, UK

> **Day 3 thesis.** Days 1–2 built the foundations: harness/skills/context-engine workshops, the Lopopolo keynote + AMA, hierarchical memory, Skills+MCP, measurement, and the full daily workflow. Day 3 fills the remaining gaps — **long-running durability, latency-driven workflow shifts, production case studies at scale, agent-on-agent debugging, and the closing human-judgment frame.** Filter every alternative through: does it tell me something I haven't already heard from Werry, Walsenuk, Lopopolo, Klingen, Pedro Rodrigues, Snyder, or the Anthropic harness papers?

---

## Morning Keynotes (Keynote Stage — all attend)

### 9:20 - 9:40am | The Future of MCP

| | |
|---|---|
| **Speaker** | David Soria Parra |
| **Role** | MCP Co-creator @ Anthropic |
| **Type** | Keynote |
| **Status** | **CHOSEN** |

> **Why attend:** MCP is the protocol layer underneath every Skills + MCP decision Pedro Rodrigues framed on Day 2. David is the co-creator and authored the 2026 MCP roadmap (enterprise readiness, Tasks primitive, agent-to-agent communication). Listen for: what's the protocol-level direction that determines whether your harness should bet on MCP for tool delivery, or stick with skills/CLI? This sets the bounds on every "skill vs MCP server" decision you'll make for the next year.

### 9:40 - 10:00am | What Do Models Still Suck At?

| | |
|---|---|
| **Speaker** | Peter Gostev |
| **Type** | Keynote |
| **Status** | **CHOSEN** |

> **Why attend:** Hashimoto's "negative space" insight made concrete. The objective filter is "results on real code or it didn't happen" — the inverse is just as important: knowing where models reliably fail tells you what NOT to delegate. Arena data on real failure modes is the rawest input for that. Connects to Day 2's Danilo Campos failure-modes talk and Drew Breunig's four context-failure modes. This is the talk that updates your AGENTS.md "do not delegate" list.

### 10:10 - 10:30am | Building pi in a World of Slop

| | |
|---|---|
| **Speaker** | Mario Zechner |
| **Type** | Keynote |
| **Status** | **CHOSEN** |

> **Why attend:** "A deliberately simple coding agent built on a small set of powerful primitives." Counter-narrative to complexity — Mario's published work includes the MCP-vs-CLI benchmark (hard cost/speed numbers showing CLI often wins) and "What if you don't need MCP at all?". This is the Vercel "we removed 80% of tools" thesis applied to harness design from first principles. Pair with Soria Parra's MCP keynote 50 minutes earlier — together they bracket the entire "how much protocol do I actually need" question.

---

## Expo Session (10:50 - 11:08am)

### 10:50 - 11:08am | Wesley

**Two Roads to Durable Agents: Replay vs. Snapshot**

| | |
|---|---|
| **Speaker** | Eric Allam |
| **Company** | Trigger.dev |
| **Type** | Expo Session |
| **Status** | **CHOSEN** |

> **Why:** This fills a Day 1–2 gap. Day 1's Anthropic workshop covered building hours-long agents; Day 2's Lopopolo keynote covered the Codex App Server architecture. Neither went deep on the replay-vs-snapshot trade-off — and that single architectural choice determines whether "always have an agent running" (Hashimoto step 6) actually works in your setup. Eric ships durable agent infrastructure for a living (CRIU checkpoint/restore, waitpoints, MCP server). Listen for: which approach survives network drops, context switches, and hour-long sessions without losing progress, and what the cost/complexity trade-off looks like.

#### Alternatives in this slot

| Room | Talk | Speaker | Relevance |
|---|---|---|---|
| Wordsworth | (TBA expo) | — | Check on the day if Allam moves |

---

## Track Sessions — Slot 1 (11:15 - 11:40am)

### CHOSEN: 11:15 - 11:40am | Fleming

**Replacing 12K LoC with a 200 LoC Skill**

| | |
|---|---|
| **Speaker** | David Gomes |
| **Company** | Cursor |
| **Type** | Track Keynote |
| **Track** | Coding Agents |
| **Status** | **CHOSEN** |

> **Why this is the pick:** This is the single sharpest "results on real code or it didn't happen" data point on Day 3. A 60x code reduction via one skill is the most concrete progressive-disclosure proof point at the conference. David also wrote "Your API is not an MCP" and ran the eval study where MCP server quality went from 60% to 100% from description changes alone — he understands both sides of the skill/MCP boundary that Pedro Rodrigues opened on Day 2. Listen for: what made *this* skill replace 12K LoC where most don't, and how does he know it's still working?
>
> **Hardest call of Day 3.** Patrick Debois (Westminster, AI Architects track keynote — see alternatives) is the strongest competing pick. Debois invented DevOps and his Context Development Lifecycle / CI/CD-for-Context material is the operational frame nobody else at the conference offers. **Choose Debois if** you're confident Days 1–2 already saturated your skills understanding (Werry workshop, Nisi/Proser, Klingen, Pedro Rodrigues, Walsenuk) and you'd rather hear the lifecycle/governance angle. **Stay with Gomes if** you want one more concrete, measurable proof point on skills at scale before betting your harness on them.

#### Alternatives in this slot

| Room | Talk | Speaker | Track | Relevance |
|---|---|---|---|---|
| Westminster | **Context Is the New Code** | Patrick Debois (Tessl) | AI Architects | **Strongest alternative.** 10/10 speaker. Context Development Lifecycle, CI/CD for context, eval gates, error budgets, self-tuning context. The operational/governance view of context as managed infrastructure — an angle no other speaker covers. The closest match to "context is more important than any individual context artifact." |
| St. James | Every API Is a Tool for Agents | Matt Carey (Cloudflare) | MCP | "Code Mode": give agents an entire API in 1,000 tokens. Relevant if you're designing MCP tools at scale — but you got the production version of this from Hablich at 11:40am and from Pedro Rodrigues on Day 2 |

---

## Track Sessions — Slot 2 (11:40am - 12:00pm)

### CHOSEN: 11:40am - 12:00pm | St. James

**Building Agent Interfaces: Lessons from Chrome DevTools MCP for Agents**

| | |
|---|---|
| **Speaker** | Michael Hablich |
| **Company** | Google |
| **Type** | Talk |
| **Track** | MCP |
| **Status** | **CHOSEN** |

> **Why:** Production lessons from shipping a real MCP server *wrong*, then fixing it (33K-star repo). The story is the lessons: monolithic tool → 26 composable tools, error messages rewritten 3x for agent self-recovery, token efficiency as a core requirement rather than an optimization. This is Fowler's "positive prompt injection" and "sensors" concepts in practice, and the most actionable MCP-design talk of the conference. Pair it with Pedro Rodrigues from Day 2: Pedro framed *when* skills vs MCP, Hablich shows *how* to build the MCP side so agents actually consume it well. Direct input for any MCP server you maintain or evaluate.

#### Alternatives in this slot

| Room | Talk | Speaker | Track | Relevance |
|---|---|---|---|---|
| Fleming | A Piece of PI — Embedding the OpenClaw Coding Agent in Your Product | Matthias Luebken (TAVON.ai) | Coding Agents | Internals of a coding agent's composable primitives. Less directly applicable than Hablich unless you're embedding pi specifically |

---

## Track Sessions — Slot 3 (12:00 - 12:20pm)

### CHOSEN: 12:00 - 12:20pm | Fleming

**The Year of Latency Debt (And How Big Tech Is Paying It Down)**

| | |
|---|---|
| **Speaker** | Sarah Chieng |
| **Type** | Talk |
| **Track** | Coding Agents |
| **Status** | **CHOSEN** |

> **Why:** This is "corrections are cheap, waiting is expensive" (OpenAI harness engineering, Lopopolo Day 2 keynote) taken to its logical conclusion. At 1,000+ tokens/sec the workflow inverts: smaller diffs, automated feedback loops, stop auto-accepting large code changes. Most "best practices" in your current harness assume the slow-inference world. This talk is the recalibration. Practical playbook, directly applicable to daily workflow design — the kind of "change I can make when I get home" the objectives demand.

#### Alternatives in this slot

| Room | Talk | Speaker | Track | Relevance |
|---|---|---|---|---|
| Westminster | (TBA AI Architects slot) | — | AI Architects | Check on the day |

---

## Track Sessions — Slot 4 (12:20 - 12:40pm)

### CHOSEN: 12:20 - 12:40pm | Fleming

**Fighting AI with AI**

| | |
|---|---|
| **Speaker** | Lawrence Jones |
| **Company** | incident.io |
| **Type** | Talk |
| **Track** | Coding Agents |
| **Status** | **CHOSEN** |

> **Why this is the strongest case study of Day 3:** Lawrence's team built a production system where AI agents debug other AI agents (~90% RCA quality, 50B+ tokens/month on AI tooling). Four Lopopolo principles operate together in this one talk:
> 1. **Verification as the lever** — evals run as a CLI runbook so agents can follow the process
> 2. **Filesystem serialization of agent traces** — preserve failure as evidence (Manus principle)
> 3. **25 parallel agents doing analysis then clustering results** — corrections cheap, waiting expensive
> 4. **Agents dogfooding their own tools** — the most powerful feedback loop
>
> Directly answers your "how do I debug long-running agent sessions?" objective. Real production codebase, real failure modes, real numbers. Do not skip.

#### Alternatives in this slot

| Room | Talk | Speaker | Track | Relevance |
|---|---|---|---|---|
| Westminster | (TBA AI Architects slot) | — | AI Architects | Check on the day |

---

## Track Sessions — Slot 5 (12:40 - 1:00pm)

### CHOSEN: 12:40 - 1:00pm | Fleming

**Factory Missions — Super Long Running Agents**

| | |
|---|---|
| **Speakers** | Matan Grinberg, Luke Alvoeiro |
| **Company** | Factory |
| **Type** | Talk |
| **Track** | Coding Agents |
| **Status** | **CHOSEN** |

> **Why:** Extends the Anthropic long-running agents workshop you took on Day 1 into production patterns: initializer/coder split, git-as-state, milestone-based validation, TDD cycles, progress artifacts, autonomy ratio metrics. Factory ships this for a living and publishes architecture details. Directly answers "how should agent sessions handle real-world interruptions without losing progress?" and connects to Eric Allam's replay-vs-snapshot expo session two hours earlier (you'll be primed to hear which architecture they chose and why). Bonus: you stay in Fleming for four straight Coding Agents talks — minimal context-switching during the densest hour of the day.

#### Alternatives in this slot

| Room | Talk | Speaker | Track | Relevance |
|---|---|---|---|---|
| Westminster | CI/CD Is Dead, Agents Need Continuous Compute and Computers | Hugo Santos, Madison Faulkner (Namespace) | AI Architects | The infrastructure bottleneck when agents open hundreds of PRs: runner saturation, cache thrash, test explosion. **Strong alternative** if you're running into CI capacity limits with parallel agents. Less applicable if you're a solo operator |

---

## Lunch (1:00 - 2:30pm)

### Expo Sessions Worth Catching

#### 1:25 - 1:43pm | Wesley — SKIP

**Stop babysitting your agents: building a context engine for mergeable code** (Brandon Walsenuk)

> **Why skip:** You already attended this on Day 2 (10:30am Wordsworth, marked CHOSEN). The Day 3 slot is a repeat of the same expo session. Use the time for the Sentry talk or actual lunch.

#### CHOSEN: 1:45 - 2:03pm | Shelley

**Comprehend First, Code Later**

| | |
|---|---|
| **Speaker** | Priscila Andre de Oliveira |
| **Company** | Sentry |
| **Type** | Expo Session |
| **Status** | **CHOSEN** |

> **Why:** 239 real engineering messages analyzed showing comprehension — not generation — is the dominant AI use in large codebases. This is Hashimoto's "negative space" thesis with hard data: knowing what agents are *bad* at and avoiding those tasks produces outsized efficiency gains. Pairs with Peter Gostev's morning keynote (where models fail) and Armin Ronacher's closing keynote (the friction is your judgment). Sentry runs a production codebase at scale, so the data isn't from a clean demo.

---

## Track Sessions — Slot 6 (2:30 - 2:50pm)

### CHOSEN: 2:30 - 2:50pm | Fleming

**Your Coding Agent Should Do AI System Engineering**

| | |
|---|---|
| **Speaker** | Ben Burtenshaw |
| **Company** | Hugging Face |
| **Type** | Talk |
| **Track** | Coding Agents |
| **Status** | **CHOSEN** |

> **Why:** Skills in production at HuggingFace: 1,000+ ML experiments daily, custom CUDA kernels via skills hitting 1.88x speedups on H100s, six-model benchmark across coding agents, live demo, concrete playbook for when to trust agent output. This is the hardest technical domain (GPU kernels) being addressed by skills — if it works there, it works in your codebase. Ben also publishes the `huggingface/skills` repo (10K+ stars) and the AGENTS.md operating contract for `multiautoresearch`. Direct extension of Day 2's Marc Klingen "Skill Issue" talk, with a more demanding domain. The "Skills are not docs — skills for hard problems only" framing is the discipline you've been building toward.

#### Alternatives in this slot

| Room | Talk | Speaker | Track | Relevance |
|---|---|---|---|---|
| Westminster | Software Engineering Is Becoming Plan and Review | Louis Knight-Webb (Vibe Kanban) | AI Architects | Plan/review as the new engineering job. Directly answers "where do humans add the most value in the loop?" **Strong alternative** if you feel skills-saturated by this point in the conference |

---

## Track Sessions — Slot 7 (2:50 - 3:10pm)

### SUGGESTED: 2:50 - 3:10pm | Fleming

**Let's Talk About FOMAT — Fear of Missing Agent Time**

| | |
|---|---|
| **Speaker** | Michael Richman |
| **Type** | Talk |
| **Track** | Coding Agents |
| **Status** | **SUGGESTED**  |

> **Why:** Practical tooling for Hashimoto's "always have an agent running" step. Monitor and interact with coding agents from phone/watch, works across Claude Code, Codex, Gemini CLI. The async control-plane pattern is a workflow multiplier that complements Day 2's Untethered Productivity (worktrees + voice dictation) and the morning's durability talk (Allam). Lighter talk — good for energy management late in the day. **Only suggested**, not chosen — if you're flagging, take the break instead.

#### Alternatives in this slot

| Room | Talk | Speaker | Track | Relevance |
|---|---|---|---|---|
| Hallway | Decompress | — | — | After four straight Fleming talks + Burtenshaw, a 20-minute reset may be the highest-value choice |

---

## Track Sessions — Slot 8 (3:10 - 3:30pm)

### CHOSEN: 3:10 - 3:30pm | Westminster

**Agents Don't Do Standups: Building the Post-Engineer Engineering Org**

| | |
|---|---|
| **Speaker** | Mike Spitz |
| **Type** | Talk |
| **Track** | AI Architects |
| **Status** | **CHOSEN** |

> **Why:** First public disclosure (per speakers.md) — production field report from a team that went all-in: 10x developer output, deploy cycles from 5 days to multiple per day, agent-on-agent review replacing human review gates, tiered human-in-the-loop for high-risk only. This is what "coding agents at scale" actually looks like organisationally. Maps to Fowler's three harness types (maintainability, architecture fitness, behavior). Pair with Lawrence Jones earlier in the day — together they bracket the technical and organizational sides of the same shift. Listen for: what stayed human, what went fully automated, and what broke when they crossed each threshold.

#### Alternatives in this slot

| Room | Talk | Speaker | Track | Relevance |
|---|---|---|---|---|
| Fleming | (TBA Coding Agents slot) | — | Coding Agents | Check on the day |

---

## Expo Session (4:05 - 4:23pm)

### SUGGESTED: 4:05 - 4:23pm | Wordsworth

**Benchmarking semantic code retrieval on Claude Code**

| | |
|---|---|
| **Type** | Expo Session |
| **Status** | **SUGGESTED** |

> **Why:** Claude Code plugin for semantic codebase search benchmarked against regex/glob/grep, with answer-quality and token-consumption numbers. If Claude Code is your daily driver, this directly affects the Guides layer of your harness. **Suggested rather than chosen** because the result depends on whether the benchmark was run on a real codebase with history and tech debt, or a clean demo — listen for the dataset before deciding it's actionable.

---

## Afternoon Keynotes (Keynote Stage — all attend)

### 4:30 - 4:50pm | Fireside Chat with Gergely Orosz and Tuomas Artman

| | |
|---|---|
| **Speakers** | Gergely Orosz, Tuomas Artman (Linear) |
| **Type** | Keynote |
| **Status** | **CHOSEN** |

> **Why attend:** Gergely is the most widely-read engineering voice on how teams actually ship; Tuomas runs engineering at Linear, which is both shipping agents (Linear Agent) AND dogfooding agents internally (75% adoption, "issue tracking is dead", Huginn coding agent). This is a candid take from a high-functioning team that has been forced to confront every harness/context/measurement question on your objective list. Connects directly back to Day 2's Gergely + swyx panel — Gergely will likely echo and update those points with Tuomas's specifics.

### 5:20 - 5:40pm | The Friction Is Your Judgment

| | |
|---|---|
| **Speakers** | Armin Ronacher, Cristina Poncela Cubeiro |
| **Type** | Keynote |
| **Status** | **CHOSEN** |

> **Why attend:** Closing intellectual frame for the entire conference. Armin (Flask, Rye, uv, Sentry) is rated 10/10 in your speaker research — read everything from "We Can Just Measure Things" to "The Final Bottleneck" to "Some Things Just Take Time" and you'll see this talk coming. The thesis: the friction you feel reviewing agent output IS your engineering judgment — don't optimize it away. This is Hashimoto's negative space, Fowler's "human role" in harness engineering, and Pocock's Day 2 "It Ain't Broke" keynote rolled into one closing argument. The emotional and intellectual exit from three days of "agents do more, humans do less" — recalibrating which parts of "less" actually matter.

---

## Summary: Your Day 3 Path

| Time | Room | Session | Status |
|---|---|---|---|
| 9:00-10:30am | Keynote | Soria Parra (MCP) · Gostev (failure modes) · Zechner (pi) | **CHOSEN** |
| 10:50-11:08am | Wesley | Two Roads to Durable Agents (Eric Allam) | **CHOSEN** |
| 11:15-11:40am | Fleming | Replacing 12K LoC with a 200 LoC Skill (David Gomes) | **CHOSEN** |
| 11:40am-12:00pm | St. James | Chrome DevTools MCP Lessons (Michael Hablich) | **CHOSEN** |
| 12:00-12:20pm | Fleming | The Year of Latency Debt (Sarah Chieng) | **CHOSEN** |
| 12:20-12:40pm | Fleming | Fighting AI with AI (Lawrence Jones) | **CHOSEN** |
| 12:40-1:00pm | Fleming | Factory Missions (Grinberg, Alvoeiro) | **CHOSEN** |
| 1:25-1:43pm | Wesley | Stop babysitting your agents (repeat) | SKIP — seen Day 2 |
| 1:45-2:03pm | Shelley | Comprehend First, Code Later (Sentry) | **CHOSEN** |
| 2:30-2:50pm | Fleming | Your Coding Agent Should Do AI System Engineering (Burtenshaw, HF) | **CHOSEN** |
| 2:50-3:10pm | Fleming | FOMAT (Michael Richman) | Suggested |
| 3:10-3:30pm | Westminster | Agents Don't Do Standups (Mike Spitz) | **CHOSEN** |
| 4:05-4:23pm | Wordsworth | Benchmarking semantic code retrieval on Claude Code | Suggested |
| 4:30-4:50pm | Keynote | Fireside: Gergely Orosz + Tuomas Artman (Linear) | **CHOSEN** |
| 5:20-5:40pm | Keynote | The Friction Is Your Judgment (Armin Ronacher) | **CHOSEN** |

### Hardest trade-offs of the day

1. **11:15am — David Gomes (Cursor) vs. Patrick Debois (Tessl).** Both 10/10 speakers in adjacent rooms with non-overlapping content. Gomes = the sharpest concrete skills proof point at the conference (60x reduction). Debois = the only Context Development Lifecycle / CI/CD-for-context talk on the schedule and the operational frame nobody else offers. The pick depends on whether you feel skills-saturated after Days 1–2 or still hungry for one more concrete proof point. **Default: Gomes.** Switch to Debois if Werry, Klingen, Pedro Rodrigues, and Walsenuk already convinced you skills work and you want governance/lifecycle thinking instead.

2. **2:30pm — Ben Burtenshaw (HuggingFace) vs. Louis Knight-Webb (Vibe Kanban).** Burtenshaw = skills in the hardest technical domain (CUDA kernels, 1000+ daily ML experiments). Knight-Webb = "plan and review as the new engineering job" — directly answers "where do humans add the most value?". Default: Burtenshaw for the concrete production data. Switch to Knight-Webb if the morning already saturated your skills appetite.

3. **12:40pm — Factory Missions vs. CI/CD Is Dead.** Factory = long-running coding agent patterns extending Day 1's Anthropic workshop. CI/CD = the infrastructure bottleneck when agents open hundreds of PRs. Default: Factory — more directly applicable to your harness work. Switch if you're hitting CI capacity limits today and need the infra angle.

4. **2:50pm — FOMAT vs. break.** Four straight Fleming talks plus Burtenshaw is a long stretch. If you're flagging, the 20-minute hallway reset is higher value than another light talk. The morning of Day 3 is the densest hour of the entire conference; protect the afternoon energy for the closing keynotes.
