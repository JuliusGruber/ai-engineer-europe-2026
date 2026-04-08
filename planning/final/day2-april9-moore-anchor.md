# Day 2 — April 9 (Wednesday) — Moore Anchor Strategy

**Conference:** AI Engineer Europe 2026
**Venue:** Queen Elizabeth II Centre, London, UK

---

## Why this document exists

The conference is overbooked. Changing rooms mid-track means surrendering a guaranteed seat in the room you're leaving for a speculative seat in the room you're entering. The `day2-april9.md` chosen path requires **three** room-change risks (Westminster→Moore, St. James→Moore, Moore→St. James), each of which could strand you in a hallway.

This document is the alternative: **pick one track room and stay in it for the entire afternoon block.** The trade-off analysis below shows Moore (Evals & Observability) is the clear anchor — it has the highest concentration of sessions that map directly to the `objectives.md` primary goals, particularly Goal #3 (measuring whether the harness is actually working).

---

## Hit rate against objectives, per MCP data

| Slot | **Moore** (Evals & Observability) | **Westminster** (Harness Engineering) | **St. James** (Context Engineering) |
|---|---|---|---|
| 11:15 | Hetzel — eval platforms (M) | **Lopopolo AMA (H)** | Appleton — multi-agent (M) |
| 11:40 | **Danilo Campos — codegen fails (H)** | Steve Ruiz — tldraw (L) | Nuno — spreadsheets (L) |
| 12:00 | Labonne — small models (L) | Swanepoel — agent patterns (M) | **Sally-Ann — memory (H)** |
| 12:20 | **Klingen — Skill Issue (H)** | Chess Coach (L) | Verma — personalization (L) |
| 12:40 | **Vincent Chen — benchmarking (H)** | Dan James — Justice AI (L) | Bilge — sovereignty (L) |
| 2:30 | **Ara Khan — Evals Are Broken (H)** | Tejas — harness deep dive (M) | Stephen Chin — context graphs (M) |
| 2:50 | **Snyder — Self Driving Products (H)** | Christensen — AI UX (L) | Kollegger — context graphs (M) |
| 3:10 | **Badertdinov — SWE-rebench (H)** | Ostrikov — self-evolving (L) | **Pedro — Skills+MCP (H)** |

- **Moore: 6 HIGH / 1 MEDIUM / 1 LOW** → 6/8 direct hits
- **Westminster: 1 HIGH / 2 MEDIUM / 5 LOW** → 1/8
- **St. James: 2 HIGH / 3 MEDIUM / 3 LOW** → 2/8

Moore is the room for `objectives.md` Primary Goal #3: *"Learn how to measure whether my coding agent harness is actually producing better code — merge rate, token cost, review cycles."*

---

## The day's shape

| Time | Room | Notes |
|---|---|---|
| 9:00 - 10:30am | Keynote Stage | Morning keynotes — all attend, no room risk |
| 10:30 - 11:08am | Wordsworth | Expo session: Stop Babysitting Your Agents (Walsenuk). Then walk to Moore early. |
| **11:15am - 3:30pm** | **Moore** | **Anchor. Do not leave.** Eight consecutive slots. |
| 3:30 - 4:30pm | Expo / break | Anchor broken only for the scheduled break |
| 4:30 - 6:00pm | Keynote Stage | Afternoon keynotes — all attend, no room risk |

**Total room moves during track sessions: 0.** Compare to the `day2-april9.md` chosen path's three high-risk walks.

---

## Morning keynotes (Keynote Stage — all attend)

### 9:00 - 9:10am | Opening Address

### 9:10 - 9:30am | The New Application Layer
**Malte Ubl** — CEO @ Vercel

### 9:30 - 9:50am | Frontier AI and the Future of Intelligence
**Raia Hadsell**

### 9:50 - 10:10am | Harness Engineering: How to Build Software When Humans Steer and Agents Execute
**Ryan Lopopolo** — Member of Technical Staff @ OpenAI

> **Critical:** This keynote is the reason the Moore anchor strategy works. Lopopolo delivers the core harness-engineering content here in 20 minutes. The Westminster AMA at 11:15 is additive (Q&A + Symphony context) — valuable, but not irreplaceable. You've already read the entire harness-engineering post; the morning keynote closes the loop.

### 10:10 - 10:30am | OpenClaw Update
**Peter Steinberger**

---

## Expo (10:30 - 11:08am)

### 10:30 - 10:48am | Wordsworth — Stop Babysitting Your Agents: Building a Context Engine for Mergeable Code
**Brandon Walsenuk**

> Catch this, then walk straight to Moore. Get to Moore by 11:00 at the latest to claim a seat before the 11:15 track session begins. **Your seat in Moore is your entire afternoon's logistics budget — do not gamble it on any other room.**

---

## Moore anchor — 11:15am to 3:30pm

### 11:15 - 11:40am | Moore — Why Building Eval Platforms Is Hard
**Phil Hetzel**

| | |
|---|---|
| **Type** | Talk |
| **Track** | Evals & Observability |
| **Status** | **ANCHOR — CHOSEN** |

> **Why:** This is the cost of admission. Hetzel is MEDIUM fit at best — he's building eval platforms as a product, not specifically measuring coding-agent harness health — but the seat you claim here unlocks the next **seven** sessions in Moore. Think of 11:15 as logistics, not content. Take notes on what he considers "hard" in eval platform construction; filter for which problems apply to internal harness measurement even though he's pitched at product builders.
>
> **What you're giving up:** Lopopolo + Sapra AMA in Westminster. You'll have seen Lopopolo's full keynote 85 minutes earlier and you've read the entire harness-engineering post. DM your prepared questions (especially the Symphony one) to both speakers on Twitter after the conference.

### 11:40am - 12:00pm | Moore — LLM Codegen Fails and How to Stop 'Em
**Danilo Campos**

| | |
|---|---|
| **Type** | Talk |
| **Track** | Evals & Observability |
| **Status** | **ANCHOR — CHOSEN** |

> **Why:** Score 9. PostHog wizard at 5K users/month, isolated failure modes + mitigation playbook from hundreds of iterations. Direct hit on *"what separates an agent run that ships clean code from one that spirals through tokens and corrections"* (`objectives.md` L43). The Anthropic long-running agents post catalogs the failure modes theoretically; Danilo has the PostHog production data. **Listen for: which failure modes are context problems vs. task-decomposition problems vs. guardrail problems.**

### 12:00 - 12:20pm | Moore — Everything I Learned Training Frontier Small Models
**Maxime Labonne**

| | |
|---|---|
| **Type** | Talk |
| **Status** | **SOFT SLOT — stay seated, do not leave** |

> **Why this is the soft slot:** Labonne's topic (training small models) is off-objective. This is the ONE slot in Moore that isn't directly on-thesis. **Use it:** eat a snack, review notes from Danilo Campos, draft questions for the Klingen session coming up, plan which reading you want to revisit tonight. **Do not leave Moore** — the walk to St. James to catch Sally-Ann Delucia costs you your Moore seat, and Klingen at 12:20 is too valuable to lose.
>
> **What you're giving up:** Sally-Ann Delucia's "Hierarchical Memory: Context Management in Agents" in St. James. Manus ("Context Engineering for AI Agents"), LangChain ("Context Engineering for Agents"), and Anthropic ("Effective context engineering for AI agents") in your reading list cover the memory-hierarchy taxonomy — you can reconstruct most of Sally-Ann's likely framework from your notes.

### 12:20 - 12:40pm | Moore — Skill Issue: Lessons from Skilling Up Coding Agents to Use Langfuse
**Marc Klingen** — Langfuse

| | |
|---|---|
| **Type** | Talk |
| **Track** | Evals & Observability |
| **Status** | **ANCHOR — CHOSEN** |

> **Why:** Direct hit on `objectives.md` L30: *"How do I get good at writing skills? What makes a skill effective vs. bloated, and how do I know when one needs rework?"* Marc ships skills at Langfuse regularly. HumanLayer's "Skill Issue" post described the "dumb zone" (too many tools → degraded performance); ETH Zurich AGENTbench showed LLM-generated context files hurt. Marc likely has real data on what makes a skill worth writing. **Listen for: concrete metrics on skill performance, and how he decides when to rework vs. deprecate.**

### 12:40 - 1:00pm | Moore — The Art & Science of Benchmarking Agents
**Vincent Chen** — Snorkel

| | |
|---|---|
| **Type** | Talk |
| **Track** | Evals & Observability |
| **Status** | **ANCHOR — CHOSEN** |

> **Why:** Direct hit on `objectives.md` L70: *"How do I know if changes to my harness or context setup are actually making things better, or if I'm just chasing vibes?"* Public abstract pitches "agentic AI" generically, but Chen's Snorkel work is heavily coding-agent specific: **Snorkel Agentic Coding Benchmark** (100 multi-step tasks), **SlopCodeBench** (measuring code erosion as agents iterate), and the paper *"Coding Agents Don't Need to Be Perfect, They Need to Recover."* Bring those to Q&A if he doesn't surface them on stage.

---

## Lunch (1:00 - 2:30pm)

**Stay near Moore.** The temptation is to use lunch for other expo sessions (Phil Hetzel's Maturity Phases of Evals at 1:05 Wordsworth; Untethered Productivity at 1:25 Wesley; BDD/ADR/PRD at 1:45 Shelley). They're all legitimately valuable — but venturing to the expo floor during lunch means rejoining the Moore queue at 2:30 with no priority. **The anchor is only strong if you maintain physical proximity to Moore.**

**Suggested lunch play:**
- Grab food quickly near Moore
- Return to Moore lobby by 2:00pm
- Sit outside the door if necessary — the goal is to be first back in the room

**If you must catch one expo:** The 1:45 Shelley BDD/ADR/PRD session is the highest-value expo of the day for the harness objective (capturing decisions for humans and AI). It ends at 2:03pm, which gives you 27 minutes to sprint back to Moore. Risky but plausible. **Do not try to chain multiple expo sessions.**

---

## Moore anchor — afternoon (2:30 - 3:30pm)

### 2:30 - 2:50pm | Moore — Evals Are Broken, Use Them Anyway
**Ara Khan** — Cline

| | |
|---|---|
| **Type** | Talk |
| **Track** | Evals & Observability |
| **Status** | **ANCHOR — CHOSEN** |

> **Why:** Ara's published *A Practical Guide to Hill Climbing* documents Cline going from 47% → 57% on Terminal Bench through eval iteration — exactly the "results on real code" + "measure my harness changes" combination the objectives demand. Pair with her *3 Seductive Traps in Agent Building* and *AI Evals Are Broken* (non-static datasets, atomicity, model-specific tuning). **Listen for: what her hill-climbing loop looks like concretely, and how she parses agent task traces to build evals that actually move the number.**
>
> **Lower opportunity cost than it looks:** Ara also speaks on **Day 3 (April 10, 3:10pm Abbey)** — *Don't Build Slop (4 Levels of AI Agent Maturity)*. So even if the Moore anchor weren't in play, seeing her twice isn't wasteful.

### 2:50 - 3:10pm | Moore — Self Driving Products: Engineering the Pipeline from Product Signals to Pull Requests
**Joshua Snyder**

| | |
|---|---|
| **Type** | Talk |
| **Track** | Evals & Observability |
| **Status** | **ANCHOR — CHOSEN** |

> **Why:** Direct hit on `objectives.md` L68: *"What does the full daily workflow look like — from a vague requirement to merged code — when coding agents do the implementation?"* End-to-end pipeline from product signals (rage-clicks, error spikes, experiment results) to automated PRs. Hashimoto's journey ended at "always have an agent running" — Snyder describes the infrastructure that makes that possible. **Listen for: is this running on production codebases with real tech debt?**

### 3:10 - 3:30pm | Moore — SWE-rebench: Lessons from Evaluating Coding Agents on Real Software Engineering Tasks
**Ibragim Badertdinov**

| | |
|---|---|
| **Type** | Talk |
| **Track** | Evals & Observability |
| **Status** | **ANCHOR — CHOSEN — NON-NEGOTIABLE** |

> **Why:** The plan's `day2-april9.md` path calls for a walk from Moore → St. James at 3:10 to catch Pedro Rodrigues's "Combine Skills and MCP to Close the Context Gap." **Do not do the walk.** Reasoning:
>
> 1. **Seat economics:** after six consecutive Moore sessions your seat is effectively irreplaceable. A 20-minute walk that loses your seat before the final track block is the worst possible trade.
> 2. **Marginal information gain:** you already have more reading on Pedro's topic (Skills + MCP) than on Badertdinov's (real-world coding-agent evaluation). Spotify Honk Part 2 documented the Skills-vs-MCP split; HumanLayer covered progressive disclosure; Anthropic's skills docs cover the protocol. SWE-rebench is net-new territory.
> 3. **Objective fit:** *"Results on real code or it didn't happen"* (`objectives.md` L12) is Badertdinov's entire thesis. "Evaluating coding agents on real software engineering tasks" is as literal a hit as the conference offers.
> 4. **Pedro is recoverable:** his talk will likely be recorded, and the Spotify/Anthropic/HumanLayer material on skills+MCP is already well-documented publicly. Badertdinov's SWE-rebench methodology is less discoverable post-conference.
>
> **The rule:** once you pick the anchor, you honor it through the last session. The discipline is what makes the strategy work.

---

## Expo break (3:30 - 4:30pm)

Leave Moore at 3:30. The anchor obligation ends here. Use the expo block for food, water, or one last expo session if energy permits:

- **3:45 - 4:03pm | Shelley** — Phil Hetzel "How Agent O11y Differs from Traditional O11y" (second Hetzel touchpoint — diminishing returns but topically relevant)
- **3:45 - 4:03pm | Wordsworth** — Daniel Szoke "Why Rust is the Ideal Language for Vibe-Coding" (previews Matt Pocock's 5:20pm keynote on software fundamentals)

Neither is required. Recovery time matters more going into the afternoon keynotes.

---

## Afternoon keynotes (Keynote Stage — all attend)

### 4:30 - 5:00pm | Software Engineering + AI = ?
**Gergely Orosz, swyx**

> Gergely brings the skeptical senior-engineer perspective. swyx developed the IMPACT framework (Intent, Memory, Planning, Authority, Control flow, Tools) and frames "Authority" as the oldest unsolved problem in agents. Connects to Hashimoto's skill formation concerns and Fowler's insight that the human's implicit harness (absorbed conventions, aesthetic judgment, organizational memory) is irreplaceable.

### 5:00 - 5:20pm | Keynote (title TBA)
**Kitze**

### 5:20 - 5:40pm | It Ain't Broke: Why Software Fundamentals Matter More Than Ever
**Matt Pocock**

> Counter-narrative to the "agents write all code" thesis. Fowler's article emphasized *harnessability* — strong typing and clearly definable module boundaries make harnesses possible. Pocock likely argues software fundamentals are the prerequisite for effective agent use, not a relic. This is Hashimoto's "verification is the single biggest lever" from the language/framework angle.

### 5:40 - 6:00pm | Keynote (title TBA)
**Sunil Pai**

---

## Summary: Moore Anchor Path

| Time | Room | Session | Status |
|---|---|---|---|
| 9:00-10:30am | Keynote | All morning keynotes (incl. Lopopolo) | **CHOSEN** |
| 10:30-10:48am | Wordsworth | Stop Babysitting Your Agents (Walsenuk) | **CHOSEN** |
| 11:15-11:40am | **Moore** | Why Building Eval Platforms Is Hard (Hetzel) | **ANCHOR** |
| 11:40am-12:00pm | **Moore** | LLM Codegen Fails (Danilo Campos) | **ANCHOR** |
| 12:00-12:20pm | **Moore** | Training Frontier Small Models (Labonne) | **SOFT — stay seated** |
| 12:20-12:40pm | **Moore** | Skill Issue (Marc Klingen) | **ANCHOR** |
| 12:40-1:00pm | **Moore** | Benchmarking Agents (Vincent Chen) | **ANCHOR** |
| 1:00-2:30pm | Lunch | Stay near Moore; optional 1:45 Shelley BDD/ADR/PRD if time permits | — |
| 2:30-2:50pm | **Moore** | Evals Are Broken (Ara Khan) | **ANCHOR** |
| 2:50-3:10pm | **Moore** | Self Driving Products (Joshua Snyder) | **ANCHOR** |
| 3:10-3:30pm | **Moore** | SWE-rebench (Badertdinov) | **ANCHOR — NON-NEGOTIABLE** |
| 3:30-4:30pm | Expo / break | Leave Moore, recover | — |
| 4:30-6:00pm | Keynote | All afternoon keynotes | All attend |

**Room moves during track sessions: 0.** (Compared to 3 in the `day2-april9.md` chosen path.)

---

## What you give up — accept it or pick the other plan

| Loss | Mitigation |
|---|---|
| **Lopopolo + Sapra AMA (11:15 Westminster)** | 20-min Lopopolo keynote at 9:50 + the entire harness-engineering post + DM questions post-conference |
| **Sally-Ann Delucia memory (12:00 St. James)** | Manus, LangChain, Anthropic memory posts cover the taxonomy |
| **Pedro Rodrigues Skills+MCP (3:10 St. James)** | Spotify Honk Part 2, HumanLayer, Anthropic skills docs cover most of the territory |
| **Tejas Kumar harness deep dive (2:30 Westminster)** | Likely confirmation of Fowler/OpenAI/Anthropic convergence you've already read |

If any of these feel like unacceptable losses, the anchor strategy is not for you — go back to `day2-april9.md` and accept the three room-change risks.

---

## Decision gate

**Pick the Moore anchor if:**
- You value a guaranteed 6-session run on measurement / workflow / evals over a scattered path with a few Tier-1 peaks
- You're unwilling to lose a seat to a walk
- Primary Goal #3 (measurement) is the one you'd sacrifice the others to achieve
- You have high confidence in your existing reading on skills/MCP and memory patterns

**Stick with `day2-april9.md` chosen path if:**
- You believe Lopopolo + Pedro Rodrigues justify the room-change risk
- You think the seat situation will be manageable in practice
- You want more breadth across harness, context, and measurement rather than depth in one
- You're willing to accept that one of the three walks will probably fail
