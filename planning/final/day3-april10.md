# Day 3 — April 10 (Friday)

**Conference:** AI Engineer Europe 2026
**Venue:** Queen Elizabeth II Centre, London, UK

> **Day 3 thesis.** Days 1–2 built the foundations: harness/skills/context-engine workshops, the Lopopolo keynote + AMA, hierarchical memory, Skills+MCP, measurement, and the full daily workflow. Day 3 fills the remaining gaps — **long-running durability, latency-driven workflow shifts, production case studies at scale, agent-on-agent debugging, and the closing human-judgment frame.** Filter every alternative through: does it tell me something I haven't already heard from Werry, Walsenuk, Lopopolo, Klingen, Pedro Rodrigues, Snyder, or the Anthropic harness papers?
>
> **Abstract-risk inventory (CHOSEN/SUGGESTED slots only).** Eight slots have a "TBA / TODO / no abstract" status in `aie` and are picks-by-default with the risk acknowledged. Treat the framing in those rows as published-research-derived, not promised-by-the-talk:
>
> 1. **Soria Parra** (9:20 keynote, CHOSEN) — `aie` description literally "Session title and abstract to be finalized"
> 2. **Building AI Systems That Ship** (10:30 Wesley, SUGGESTED add-on) — no speaker listed in `aie`; content inferred from Case/WorkOS CLI references in the abstract
> 3. **Gomes** (11:15 Fleming, alternative) — David Gomes is a 9/10 speaker but the abstract is literally "TODO"; "60x reduction" framing inferred from the title
> 4. **Factory Missions** (12:40 Fleming, CHOSEN) — speakers confirmed (Grinberg + Alvoeiro), `aie` returns no description; content inferred from Factory's published docs
> 5. **Benchmarking semantic code retrieval** (4:05 Wordsworth, SUGGESTED) — abstract exists but explicitly says "small set of representative tasks" — already downgraded in row
> 6. **Gergely + Artman fireside** (4:30 keynote, CHOSEN) — `aie` returns title only, no description
> 7. **Lauritzen — Agents need more than a chat** (5:00 keynote, SKIP/decompress) — `aie` returns title only; flagged in row as "stay seated if Lauritzen surfaces something concrete"
> 8. **Kalbir Sohi** (5:40 keynote, SKIP unless surfaces) — `aie` returns "(TBA)"

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
>
> **Caveat:** AIE abstract still TBA — framing is based on Soria Parra's published 2026 MCP roadmap, not the talk itself. If the slot turns into a release/news announcement, the playbook value is lower than expected.

### 9:40 - 10:00am | What Do Models Still Suck At?

| | |
|---|---|
| **Speaker** | Peter Gostev |
| **Company** | Arena.ai (AI Capability Lead) |
| **Type** | Keynote |
| **Status** | **CHOSEN** |

> **Why attend:** Hashimoto's "negative space" insight made concrete. The objective filter is "results on real code or it didn't happen" — the inverse is just as important: knowing where models reliably fail tells you what NOT to delegate. Arena data on real failure modes is the rawest input for that. Connects to Day 2's Danilo Campos failure-modes talk and Drew Breunig's four context-failure modes. This is the talk that updates your AGENTS.md "do not delegate" list.

### 10:10 - 10:30am | Building pi in a World of Slop

| | |
|---|---|
| **Speaker** | Mario Zechner |
| **Type** | Keynote |
| **Status** | **CHOSEN** |

> **Why attend:** "A deliberately simple coding agent built on a small set of powerful primitives." Counter-narrative to complexity — Mario's published work includes the MCP-vs-CLI benchmark (hard cost/speed numbers showing CLI often wins) and "What if you don't need MCP at all?". Pair with Soria Parra's MCP keynote 50 minutes earlier — together they bracket the entire "how much protocol do I actually need" question.
>
> **What the abstract actually promises:** more cultural commentary than benchmark deep-dive. Mario's published framing is "a plea to slow the fuck down" and "how agents are destroying OSS" — pi got absorbed into OpenClaw and this talk is partly about that. The minimal-primitives architectural argument is *implicit* in the framing rather than the central deliverable. Still worth attending (he's 9/10 in speakers.md), but go in expecting the cultural/architectural argument *behind* the benchmark, not the benchmark numbers themselves.

#### Other keynote-stage sessions in this block (SKIP)

| Time | Session | Speaker | Why skip |
|---|---|---|---|
| 9:00 - 9:20am | Gemma, DeepMind's Family of Open Models | Omar Sanseviero | Open-models / Sovereign AI focus — off-objective. Use the time for coffee and to settle in |
| 10:00 - 10:10am | AgentCraft: Putting the Orc in Agent Orchestration | Ido Salomon | 10-min slot. Salomon is the MCP-UI / GitMCP author (8/10 in speakers.md), but the talk is about RTS-style agent orchestration — interesting but not on the harness path. Stay seated since Zechner is up next |

---

## Expo Session (10:30 - 10:48am)

### CHOSEN: 10:30 - 10:48am | Wesley

**Building AI Systems That Ship**

| | |
|---|---|
| **Speaker** | (no speaker listed in aie — abstract names *Case* and the *WorkOS CLI*; could be Nisi, Proser, or another Case/WorkOS team member) |
| **Type** | Expo Session |
| **Status** | **CHOSEN** (flows directly into Allam at 10:50 in the same room) |

> **Why:** Case is Nick Nisi's published harness work (10/10 in speakers.md, *Case Statement: Building a Harness — 6-agent deterministic pipeline*). Abstract: *"agent-ready means a codebase agents can safely change, and a product agents can reliably use… clear constraints, machine-friendly interfaces, and feedback loops that compound over time."* Direct hit on the harness-engineering objective and the cheapest addition on Day 3 — Zechner ends at 10:30, this starts at 10:30 in Wesley, ends at 10:48, and Allam starts at 10:50 in the same room. Walk straight from the Keynote Stage to Wesley after Zechner and stay there for the next 38 minutes.
>
> **Caveats:** (1) `aie` lists no speaker for this slot — the Nisi attribution is inferred from the abstract's references to Case + WorkOS CLI. The abstract uses singular "**I'll** walk through," so it is one speaker, not the Nisi+Proser workshop pairing — likely Nisi *or* Proser *or* another single Case/WorkOS team member. (2) If the speaker turns out to be Nisi and they cover the same Case material from the Day 1 Skills at Scale workshop you're already attending, this is a partial repeat. Listen for whether the "WorkOS CLI as a product agents can reliably use" angle is new.

#### Alternatives in this slot

| Room | Talk | Speaker | Relevance |
|---|---|---|---|
| Wordsworth | Can LLMs generate Enterprise Quality Code? | — | Benchmark of 50+ LLMs on code-quality dimensions paired with deterministic static analysis. Marginal-but-on-objective for the "results on real code" filter. Skip if you're going to Wesley for Nisi |
| Shelley | Does GenAI "belong" to data scientists? | Phil Hetzel | Org/ownership framing for GenAI work. Off-objective — skip |

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
| Shelley | Spec-Driven Testing for Agents With A Brain the Size of A Planet | — | Specs/red-team/gold-team/fuzzing for agents. Adjacent to objectives — relevant only if you treat skill/agent test specs as a measurement layer |
| Wordsworth | How to talk to statues | — | ElevenLabs voice-AI demo (museum/CV/voice). Off-objective — skip |

---

## Track Sessions — Slot 1 (11:15 - 11:40am)

### CHOSEN: 11:15 - 11:40am | Westminster

**Context Is the New Code**

| | |
|---|---|
| **Speaker** | Patrick Debois |
| **Company** | Tessl |
| **Type** | Track Keynote |
| **Track** | AI Architects |
| **Status** | **CHOSEN** |

> **Why this is the pick:** Debois invented DevOps and is the only speaker on Day 3 (and arguably the conference) treating context as managed infrastructure with a full lifecycle. Published abstract is explicit: Context Development Lifecycle (Generate → Evaluate → Distribute → Observe), version control / peer review / CI-CD pipelines for context, eval gates, error budgets, the context flywheel as a moat. This is the closest match to your *measurement* objective ("how do I know if changes to my harness or context setup are actually making things better, or if I'm just chasing vibes?") — every other talk covers a *piece* of skills/context, this covers the lifecycle that wraps around them. 10/10 speaker.
>
> **Why this beats Gomes (the previous default).** Three converging reasons: (1) **Abstract certainty** — Debois has a fully published abstract; Gomes's abstract is literally "TODO" in `aie`, so the "60x code reduction" framing is inferred from the title. (2) **Day 3 thesis filter** — your own filter is "does it tell me something I haven't already heard from Werry, Walsenuk, Lopopolo, Klingen, Pedro Rodrigues, Snyder, or the Anthropic harness papers?" Debois passes cleanly; one more skills proof point doesn't. (3) **Marginal value** — by 11:15am Day 3 you've already had Werry's workshop, Nisi/Proser Skills at Scale, Klingen's Skill Issue, Pedro Rodrigues's Skills+MCP, Walsenuk's context engine, and Burtenshaw is *still ahead* of you at 2:30pm. The marginal value of one more skills demo is low; the marginal value of the only governance/CI-CD-for-context talk is high.

#### Alternatives in this slot

| Room | Talk | Speaker | Track | Relevance |
|---|---|---|---|---|
| Fleming | **Replacing 12K LoC with a 200 LoC Skill** | David Gomes (Cursor) | Coding Agents | **Strongest alternative — and the previous default pick.** A 60x code reduction via one skill would be the most concrete progressive-disclosure proof point at the conference *if the title delivers*. Gomes also wrote "Your API is not an MCP" and ran the eval study where MCP server quality went from 60% to 100% from description changes alone. **Risk:** AIE abstract is currently "TODO" — the framing is inferred from the title and Gomes's prior Neon work, not promised by the talk. **Switch to Gomes if** you finish Days 1–2 still hungry for one more concrete skills proof point and you're willing to take the abstract risk |
| St. James | Every API Is a Tool for Agents | Matt Carey (Cloudflare) | MCP | "Code Mode": give agents an entire API in 1,000 tokens. Relevant if you're designing MCP tools at scale — but you got the production version of this from Hablich at 11:40am and from Pedro Rodrigues on Day 2 |
| Abbey | One Login to Rule Them All: Cross-App Access for MCP | Garrett Galow (WorkOS) | GPUs & LLM Infra | MCP enterprise auth — XAA, Pipes MCP, session-scoped authorization for agents. 8/10 speaker. Niche fit: only relevant if you're going to operate MCP servers across organisations or care about agent auth boundaries |

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
| Westminster | Rewiring the State | Eoin Mulgrew | AI Architects | UK No 10 government tech rebuild — call to arms for engineers to join. Off-objective for harness work — skip |
| Abbey | Scaling Reinforcement Learning: Lessons from Trillion-Token Deployments at Fortune 500s | Jullien Launay | GPUs & LLM Infra | Fortune-500 RL post-training at scale. Off-objective for coding-agent harness work — skip |

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
>
> **Vendor caveat:** Sarah is Head of DevX at **Cerebras**, and the talk is grounded in "Codex Spark" — Cerebras-hosted Codex at 1000+ tok/s. Technically a vendor talk. The playbook on smaller diffs / no-auto-accept / automated feedback loops generalizes regardless of whose silicon serves the inference, so the substance still holds.

#### Alternatives in this slot

| Room | Talk | Speaker | Track | Relevance |
|---|---|---|---|---|
| Westminster | Most Enterprise Agentic Projects Are Doomed — Here's Why | Jess Grogan-Avignon, Jack Wang | AI Architects | Field stories from agentic delivery in traditional large enterprise. Off-objective for your harness work — skip |
| St. James | MCP UI | Liad Yosef, Ido Salomon | MCP | UI components for MCP apps. Adjacent — only relevant if you build MCP-facing UIs |

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
| Abbey | **The Missing Primitive for Agent Swarms** | Chris Weichel (Ona) | GPUs & LLM Infra | **Strongest missed alternative of the slot.** Argues parallel agents need a platform primitive (identity, isolation, lifecycle, coordination) instead of being treated as application-level concerns — picks up directly on Lopopolo's Day 2 "corrections cheap, waiting expensive" thread and the same 25-parallel-agent pattern Lawrence Jones is presenting in this exact slot. Pick Weichel only if you've decided you'd rather hear the platform argument than the production case study; otherwise stay with Jones |
| Westminster | The Domain-Native AI Organization | Chris Lovejoy | AI Architects | Frameworks for embedding domain expertise (Oracle / Evaluator / Architect models). Off-objective for harness work — skip |
| St. James | Why MCP and ChatGPT Apps Use Double Iframes | Frédéric Barthelet | MCP | Sandboxing architecture / security policy deep dive. Niche — only relevant if you're shipping MCP-app UIs |

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

> **Why:** Extends the Anthropic long-running agents workshop you took on Day 1 into production patterns: initializer/coder split, git-as-state, milestone-based validation, TDD cycles, progress artifacts, autonomy ratio metrics. Factory ships this for a living and publishes architecture details. Directly answers "how should agent sessions handle real-world interruptions without losing progress?" and connects to Eric Allam's replay-vs-snapshot expo session two hours earlier (you'll be primed to hear which architecture they chose and why). Bonus: three Fleming Coding Agents talks back-to-back (Chieng → Jones → Factory Missions), then Burtenshaw after lunch in the same room — minimal context-switching during the densest hour of the day.
>
> **Caveat:** AIE abstract is not yet published — the architectural specifics above are inferred from Factory's published docs (SKILL.md system, DroidShield, milestone-based validation, autonomy ratio metrics) and speakers.md, not promised by the talk. Speakers are confirmed: Matan Grinberg (CEO @ Factory) and Luke Alvoeiro (Product/Tech Lead @ Factory).

#### Alternatives in this slot

| Room | Talk | Speaker | Track | Relevance |
|---|---|---|---|---|
| Westminster | CI/CD Is Dead, Agents Need Continuous Compute and Computers | Hugo Santos, Madison Faulkner (Namespace) | AI Architects | The infrastructure bottleneck when agents open hundreds of PRs: runner saturation, cache thrash, test explosion. **Strong alternative** if you're running into CI capacity limits with parallel agents. Less applicable if you're a solo operator |

---

## Lunch (1:00 - 2:30pm)

### Expo Sessions Worth Catching

#### 1:25 - 1:43pm | Wesley — SKIP

**Stop babysitting your agents: building a context engine for mergeable code** (Brandon Walsenuk)

> **Why skip:** You already attended this on Day 2 (10:30am Wordsworth, marked CHOSEN). The Day 3 slot is a repeat of the same expo session. Use the time for Task Fidelity Scaling Laws in Shelley instead.

#### CHOSEN: 1:25 - 1:43pm | Shelley

**Task Fidelity Scaling Laws**

| | |
|---|---|
| **Type** | Expo Session |
| **Status** | **CHOSEN** (paired with Comprehend First, back-to-back in Shelley — sandwich lunch) |

> **Why:** TerminalBench experiments showing fine-tuning on a small set of well-posed, non-trivial tasks dramatically outperforms training on more low-fidelity tasks with the same model and compute. *"Task fidelity behaves like a scaling law. Before increasing model size or RL budget, fix your tasks."* This is the "task spec quality dominates everything" thesis — directly applicable to how you write skills and AGENTS.md instructions. Pairs back-to-back with Comprehend First in the same room (Shelley) — the training-side data point complements the comprehension-side data point.

#### CHOSEN: 1:45 - 2:03pm | Shelley

**Comprehend First, Code Later**

| | |
|---|---|
| **Speaker** | Priscila Andre de Oliveira |
| **Company** | Sentry |
| **Type** | Expo Session |
| **Status** | **CHOSEN** |

> **Why:** 239 real engineering messages analyzed showing comprehension — not generation — is the dominant AI use in large codebases. This is Hashimoto's "negative space" thesis with hard data: knowing what agents are *bad* at and avoiding those tasks produces outsized efficiency gains. Pairs with Peter Gostev's morning keynote (where models fail) and Armin Ronacher's closing keynote (the friction is your judgment). Sentry runs a production codebase at scale, so the data isn't from a clean demo.

#### Alternatives in this slot

| Room | Talk | Speaker | Relevance |
|---|---|---|---|
| Wordsworth (2:05-2:23pm) | Malleable Evals: Why Are We Still Evaluating Adaptive Systems with Static Tests? | — | Adjacent to your measurement objective. Skip — you'll want to be moving toward Burtenshaw at 2:30, but worth knowing it exists if Comprehend First runs short |

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
| St. James | **Lessons from Scaling GitHub's Remote MCP Server** | Sam Morrow (GitHub) | MCP | **Strongest alternative.** 9/10 speaker, MCP spec co-author. 4M+ downloads of the stdio server, the canonical large-scale MCP server case study. Pairs with Hablich (11:40 Chrome DevTools MCP) and Karan Sampath (3:10 Bringing MCPs to the Enterprise) as the **Day 3 production-MCP arc** in St. James: Hablich (11:40) → Morrow (2:30) → Sampath (3:10), bracketing the lunch break and the three Fleming Coding Agents picks. Taking Morrow naturally pulls Sampath at 3:10 over Spitz. Skip only if you've already decided MCP is downstream of skills for your harness |
| Westminster | Software Engineering Is Becoming Plan and Review | Louis Knight-Webb (Vibe Kanban) | AI Architects | Plan/review as the new engineering job. Directly answers "where do humans add the most value in the loop?" Strong alternative if you feel skills-saturated by this point in the conference. **Caveat:** Spitz at 3:10pm covers a strict superset of this ground (post-engineer org, what humans still do, planning/review surviving agile), so picking Knight-Webb here means partial overlap — strengthens the Burtenshaw default |

---

## Track Sessions — Slot 7 (2:50 - 3:10pm)

### CHOSEN: 2:50 - 3:10pm | Westminster

**How Building with AI Can Double the Throughput of Your Engineering Team**

| | |
|---|---|
| **Speaker** | Brian Scanlan |
| **Company** | Intercom |
| **Type** | Talk |
| **Track** | AI Architects |
| **Status** | **CHOSEN** |

> **Why:** One of the two production-at-scale field reports of Day 3 (the other is Spitz at 3:10 — same room, back-to-back). Intercom has been one of the loudest published voices on coding agents in production: 13 plugins, 100+ skills, hooks, ~90% of PRs authored by Claude Code, the explicit 2x throughput initiative. Scanlan publishes the "How we use Claude Code today at Intercom" piece that maps directly onto every layer of your harness. Filter from the Day 3 thesis: does it tell me something I haven't already heard from Werry, Walsenuk, Lopopolo, Klingen, Pedro Rodrigues, Snyder, or the Anthropic harness papers? **Yes** — Intercom is a peer org running this on a real SaaS codebase with history and tech debt, not a clean demo and not a vendor showing off their own tool.
>
> **Abstract caveat:** The published `aie` abstract is one short paragraph — Intercom's 2x goal and "lessons and learnings… what has and hasn't worked." None of the "13 plugins / 100+ skills / hooks / ~90% of PRs" specifics above are *promised* by the talk; they're inferred from Scanlan's published Intercom posts (`speakers.md`). Confidence is higher than for the Soria Parra / Gomes / Factory Missions slots because Scanlan's posts are recent and concrete, but the abstract itself doesn't commit to any of those numbers. Listen for whether he updates the published figures or stays at the "lessons learned" altitude.
>
> **Bonus structural win:** Westminster → Westminster from 2:50 → 3:10 (Scanlan → Spitz) is the cleanest room flow of the afternoon. Both production case studies, same room, no context-switching. The two talks together bracket the technical and organizational sides of "what does coding agents at scale actually look like."

#### Alternatives in this slot

| Room | Talk | Speaker | Track | Relevance |
|---|---|---|---|---|
| Fleming | Let's Talk About FOMAT — Fear of Missing Agent Time | Michael Richman | Coding Agents | Cmd+Ctrl: phone/watch control plane for Claude Code, Codex, Gemini CLI. Practical async-agent tooling that complements Day 2's Untethered Productivity and Allam's morning durability talk. Lighter demo talk — fine if you're flagging and Scanlan feels like another "agents at scale" beat after Burtenshaw |
| St. James | Your Agent Is an Infinite Canvas | RL Nabors | MCP | Argues chat is the wrong UI primitive for agents (terminal-as-canvas analogy). Agent-UX angle, not harness — defensible skip. **Tactical use:** if you switched to Morrow at 2:30, this keeps you in St. James for the production-MCP arc into Sampath at 3:10 (Morrow → Nabors → Sampath, all-St. James fallback) |
| Abbey | Beyond Code Coverage: Functionality Testing with Playwright | Marlene Mhangami (Microsoft) | GPUs & LLM Infra | LLM-generated unit tests pass code coverage but don't verify functionality — argues for Playwright + the new Playwright MCP server as the e2e check on agent-written code. Adjacent to "results on real code or it didn't happen" and your automated-feedback-loop objective. Skip unless your harness is missing a functional-test layer today |
| Hallway | Decompress | — | — | If you're flagging, a 20-min reset before the closing keynotes is still legitimate. But Scanlan + Spitz is the strongest 40-min block of the afternoon — protect this and decompress between Spitz and Gergely instead |

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
| St. James | **Bringing MCPs to the Enterprise** | Karan Sampath (Anthropic) | MCP | **Strongest alternative.** Anthropic FDE on solving MCP security, observability, and access-control at enterprise scale. Companion to Hablich's morning Chrome DevTools MCP talk and to Sam Morrow at 2:30pm — together they form the production-MCP arc of Day 3. 8/10 speaker. Pick only if you've decided MCP is the load-bearing layer of your harness |
| Fleming | Cooking with Agents in VS Code | Liam Hampton (Microsoft) | Coding Agents | Local / remote / worktree-based agent paths inside VS Code, demo-driven. Lightweight — fine if Westminster feels like one too many "agents at scale" beats |
| Abbey | Don't Build Slop (4 Levels of AI Agent Maturity) | Ara Khan (Cline) | GPUs & LLM Infra | You're already seeing Ara Khan on Day 2 (2:30pm Westminster, *Evals Are Broken*). This is a different topic — abstract is more about inference routing / cost napkin-math than the title suggests. Skip the speaker overlap |

---

## Expo Session (4:05 - 4:23pm)

### CHOSEN: 4:05 - 4:23pm | Wesley

**AMA: AI Engineer Europe with swyx**

| | |
|---|---|
| **Speaker** | swyx |
| **Type** | Expo Session |
| **Status** | **CHOSEN** |

> **Why:** Closing-context conference recap from the conference founder. Wide-angle synthesis before the closing keynotes — exactly the right context-load before Gergely + Ronacher. Picked over the semantic-retrieval benchmark because that talk has a demo-data flag in the abstract itself ("across a small set of representative tasks") — strongest possible small-N synthetic-task signal short of admitting it. The swyx AMA also gives you a chance to ask the founder a direct question during a low-pressure expo slot.

#### Alternatives in this slot (and the prior 3:45pm block)

| Room | Talk | Speaker | Relevance |
|---|---|---|---|
| Wordsworth | Benchmarking semantic code retrieval on Claude Code | — | Claude Code plugin for semantic codebase search benchmarked against regex/glob/grep. **Demo-data flag in the abstract:** literally says "across a small set of representative tasks." Skip — only worth showing up for the live demo of how the plugin slots into Claude Code |
| Wordsworth (3:45-4:03pm) | Stop Making Models Bigger. Make Them Behave | — | A 4B model fine-tuned via rLLM to beat a 235B model on real financial analysis tasks by enforcing tool discipline (schema exploration, output validation, retry instead of hallucinating). Strongest "behavior > size" data point on Day 3, paired with Gostev's morning keynote on where models fail. Likely a skip — you'll want to decompress before Gergely — but worth knowing it exists |
| Shelley (3:45-4:03pm) | Live Demo & Q&A with Zed | — | Sponsor demo, no abstract. Zed is one of the few editors with a real Claude-Code-style agent integration story — could be on-objective if they show their harness work, but sponsor-format risk is high. Skip by default |
| Shelley | Build an Aura Agent in 10 Minutes | — | Knowledge graphs over unstructured data. Off-objective — skip |

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

#### Other keynote-stage sessions in this block (SKIP / decompress)

| Time | Session | Speaker | Why skip |
|---|---|---|---|
| 5:00 - 5:20pm | Agents need more than a chat | Jacob Lauritzen (CTO, Legora — legal AI) | Sits between the Gergely fireside and Ronacher. No published material aligned to objectives, no abstract in `aie`. Legora is a legal-AI shop, so the talk *could* surface long-context / document-heavy patterns relevant to harness work — or be entirely product-side. Use as a 20-min decompress before the closing keynote, or stay seated if Lauritzen surfaces something concrete on agent UX |
| 5:40 - 6:00pm | (session TBA) | Kalbir Sohi | Closing slot, abstract not yet posted. Default: leave after Ronacher unless the title surfaces something objective-aligned |

---

## Summary: Your Day 3 Path

| Time | Room | Session | Status |
|---|---|---|---|
| 9:00-9:20am | Keynote | Sanseviero (Gemma open models) | SKIP — off-objective |
| 9:20-10:30am | Keynote | Soria Parra (MCP) · Gostev (failure modes) · Zechner (pi) | **CHOSEN** (Salomon AgentCraft 10:00 also off-objective) |
| 10:30-10:48am | Wesley | Building AI Systems That Ship (likely Nick Nisi / Case harness) | **CHOSEN** (flows into Allam) |
| 10:50-11:08am | Wesley | Two Roads to Durable Agents (Eric Allam) | **CHOSEN** |
| 11:15-11:40am | Westminster | Context Is the New Code (Patrick Debois, Tessl) | **CHOSEN** |
| 11:40am-12:00pm | St. James | Chrome DevTools MCP Lessons (Michael Hablich) | **CHOSEN** |
| 12:00-12:20pm | Fleming | The Year of Latency Debt (Sarah Chieng) | **CHOSEN** |
| 12:20-12:40pm | Fleming | Fighting AI with AI (Lawrence Jones) | **CHOSEN** |
| 12:40-1:00pm | Fleming | Factory Missions (Grinberg, Alvoeiro) | **CHOSEN** |
| 1:25-1:43pm | Shelley | Task Fidelity Scaling Laws | **CHOSEN** |
| 1:45-2:03pm | Shelley | Comprehend First, Code Later (Sentry) | **CHOSEN** |
| 2:30-2:50pm | Fleming | Your Coding Agent Should Do AI System Engineering (Burtenshaw, HF) | **CHOSEN** |
| 2:50-3:10pm | Westminster | How Building with AI Can Double Throughput (Brian Scanlan, Intercom) | **CHOSEN** |
| 3:10-3:30pm | Westminster | Agents Don't Do Standups (Mike Spitz) | **CHOSEN** |
| 4:05-4:23pm | Wesley | AMA: AI Engineer Europe with swyx | **CHOSEN** |
| 4:30-4:50pm | Keynote | Fireside: Gergely Orosz + Tuomas Artman (Linear) | **CHOSEN** |
| 5:00-5:20pm | Keynote | Agents need more than a chat (Jacob Lauritzen) | SKIP / decompress |
| 5:20-5:40pm | Keynote | The Friction Is Your Judgment (Armin Ronacher) | **CHOSEN** |
| 5:40-6:00pm | Keynote | (TBA — Kalbir Sohi) | SKIP unless abstract surfaces |

> **Room-flow note for the 11:15 → 12:00 block.** With Debois now the 11:15 pick, the path is **Westminster (Debois) → St. James (Hablich) → Fleming (Chieng)** — two room changes inside 45 minutes. Probably fine in the QEII Centre but worth knowing. Two zero-churn alternatives if the walks become a problem on the day: **all-Westminster** keeps you with Debois then Mulgrew (off-objective) then Grogan-Avignon/Wang (off-objective) — weak content; **all-St. James** is Carey → Hablich → MCP UI — pure MCP track but you lose Debois's measurement angle and Chieng's latency-debt playbook. The current Westminster → St. James → Fleming path is the strongest content path; the room cost is real but acceptable.

### Hardest trade-offs of the day

1. **11:15am — Patrick Debois (Tessl, 10/10) vs. David Gomes (Cursor, 9/10).** Both top-tier speakers in non-overlapping content. Debois = the only Context Development Lifecycle / CI/CD-for-context talk on the schedule and the operational frame nobody else offers; closest match to your *measurement* objective. Gomes = would be the sharpest concrete skills proof point of the conference (60x reduction) *if the title delivers*. **Default: Debois** — three converging reasons: (1) Debois has a fully published abstract while Gomes's is "TODO" in `aie`, (2) by 11:15am Day 3 you're skills-saturated after Werry/Nisi/Klingen/Pedro Rodrigues/Walsenuk and Burtenshaw is still ahead at 2:30pm, (3) the only "vibes vs. measurement" talk on the schedule is the higher-marginal-value pick. **Switch to Gomes** only if you finish Days 1–2 still hungry for one more concrete skills proof point and you accept the "TODO" abstract risk.

2. **2:30pm — Burtenshaw (HF) vs. Sam Morrow (GitHub) vs. Knight-Webb (Vibe Kanban).** A genuine three-way. Burtenshaw = skills in the hardest technical domain (CUDA kernels, 1000+ daily ML experiments). Morrow = the canonical large-scale MCP server case study (4M+ stdio downloads), production extension of Hablich's morning Chrome DevTools MCP talk. Knight-Webb = "plan and review as the new engineering job." **Default: Burtenshaw** for the concrete skills-in-production data. **Switch to Morrow** if you've decided MCP is more load-bearing for your harness than skills and you want to double down on the Hablich thread.

3. **12:40pm — Factory Missions vs. CI/CD Is Dead.** Factory = long-running coding agent patterns extending Day 1's Anthropic workshop. CI/CD = the infrastructure bottleneck when agents open hundreds of PRs. Default: Factory — more directly applicable to your harness work. Switch if you're hitting CI capacity limits today and need the infra angle.

4. **No real trade-off at 2:50pm.** Brian Scanlan at Westminster is the strongest pick by a wide margin (production case study from Intercom, peer org running Claude Code on a real SaaS codebase, ~90% of PRs by Claude Code). FOMAT is the fallback only if you're flagging and a phone-based control-plane demo feels like enough. Westminster also keeps you in the same room for Spitz at 3:10 — protect this 40-min block and decompress *between* Spitz and the Gergely fireside instead.
