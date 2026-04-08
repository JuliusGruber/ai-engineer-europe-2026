# Day 2 — April 9 (Wednesday) — St. James Anchor Strategy

**Conference:** AI Engineer Europe 2026
**Venue:** Queen Elizabeth II Centre, London, UK

---

## Why this document exists

Companion to `day2-april9-moore-anchor.md`. Same overbooked-conference constraint: room changes risk losing your seat, so the strategy is to anchor in one track room for the entire afternoon block.

The Moore anchor wins when Primary Goal #3 (measurement — *"Learn how to measure whether my coding agent harness is actually producing better code"*) is non-negotiable.

**This document is for the case where measurement/evals is de-prioritized** and the weight shifts to:
- Primary Goal #1 — harness engineering as the Lopopolo/Hashimoto discipline
- Context engineering — skills, MCP, memory structure, what to give agents
- Coding agents in practice — daily workflow, Skills+MCP+harness as a stack

Once evals is stripped out, **St. James (Context Engineering) becomes the strongest anchor** — not Westminster, which is surprising but structural.

---

## Hit rate against objectives (evals objective removed)

| Slot | **St. James** (Context Engineering) | **Westminster** (Harness Engineering) | **Moore** (Evals & Observability) |
|---|---|---|---|
| 11:15 | Appleton — multi-agent coord (MH) | **Lopopolo + Sapra AMA (H)** | Hetzel — eval platforms (L) |
| 11:40 | Nuno — spreadsheets (L) | Ruiz — tldraw (L) | Danilo — codegen fails (MH) |
| 12:00 | **Sally-Ann — hierarchical memory (H)** | Swanepoel + Schmid lightning (MH) | Labonne — small models (L) |
| 12:20 | Verma — personalization (L) | Chess Coach (L) | Klingen — Skill Issue (H) |
| 12:40 | Bilge — sovereignty (L) | Dan James — Justice AI (L) | Chen — benchmarking (L) |
| 2:30 | Chin — context graphs (M) | **Tejas — Harnesses deep dive (H)** | Ara Khan — Evals Are Broken (L) |
| 2:50 | Kollegger — context graphs (M) | Christensen — AI UX (L) | **Snyder — Self Driving Products (H)** |
| 3:10 | **Pedro — Skills+MCP (H)** | Ostrikov — self-evolving (L) | Badertdinov — SWE-rebench (L) |

- **St. James: 2 H + 1 MH + 2 M + 3 L**
- **Westminster: 2 H + 1 MH + 0 M + 5 L**
- **Moore: 2 H + 1 MH + 0 M + 5 L**

All three rooms tie on peak count (2 HIGH each), but **St. James is the only room with no afternoon "desert"** — the two MEDIUM context-graphs sessions keep you on-topic through the afternoon block instead of crashing into LOW content.

---

## Why St. James beats Westminster specifically

You'd expect Westminster (literally named the "Harness Engineering" track) to win the harness objective. It doesn't. Four structural reasons:

1. **Pedro Rodrigues at 3:10 is Tier 1 on a named objective question.** `objectives.md` L35: *"When should context live in a skill vs. behind an MCP server? What does the data show about using both together vs. either alone?"* — that is literally Pedro's talk title. And L64: *"Skills, MCP, and harness engineering as a stack."* The main plan's own note: "**Do not miss this one.**" Westminster's 3:10 is Ostrikov on a competition win — off-objective.

2. **Tejas Kumar is confirmation, not new material.** The main plan flags it: *"likely offers a different angle on the same topic... does Tejas present patterns you haven't seen, or does he confirm the Fowler/OpenAI/Anthropic convergence?"* You've read the Fowler article, the Lopopolo post, the Anthropic harness posts, the LangChain Anatomy post, and Hashimoto. Tejas can't tell you much you don't already know.

3. **Sally-Ann Delucia's memory hierarchy is the direct hit on `objectives.md` L38-41** (*"How should agent memory and context be structured? What patterns exist for organizing what agents know and when they know it?"*). Westminster has no equivalent at 12:00 — Swanepoel + Schmid is a valuable MH lightning combo on patterns across Harvey/Cursor/Manus/OpenAI, but it's breadth over depth.

4. **Afternoon coverage:** St. James 2:30/2:50/3:10 is Chin (M) → Kollegger (M) → Pedro (H). Westminster 2:30/2:50/3:10 is Tejas (H) → Christensen (L) → Ostrikov (L). St. James is strictly more informative per slot across the afternoon.

---

## The day's shape

| Time | Room | Notes |
|---|---|---|
| 9:00 - 10:30am | Keynote Stage | Morning keynotes — all attend, no room risk |
| 10:30 - 11:08am | Wordsworth | Expo: Stop Babysitting Your Agents (Walsenuk). Walk to St. James early. |
| **11:15am - 3:30pm** | **St. James** | **Anchor. Do not leave.** Eight consecutive slots. |
| 3:30 - 4:30pm | Expo / break | Anchor broken only for the scheduled break |
| 4:30 - 6:00pm | Keynote Stage | Afternoon keynotes — all attend, no room risk |

**Total room moves during track sessions: 0.**

---

## Morning keynotes (Keynote Stage — all attend)

### 9:00 - 9:10am | Opening Address

### 9:10 - 9:30am | The New Application Layer
**Malte Ubl** — CEO @ Vercel

### 9:30 - 9:50am | Frontier AI and the Future of Intelligence
**Raia Hadsell**

### 9:50 - 10:10am | Harness Engineering: How to Build Software When Humans Steer and Agents Execute
**Ryan Lopopolo** — Member of Technical Staff @ OpenAI

> **Critical:** This keynote is the reason the St. James anchor strategy works. Lopopolo delivers the core harness-engineering content here in 20 minutes. The Westminster AMA at 11:15 is additive (Q&A + Symphony context) — valuable, but not irreplaceable. You've already read the entire harness-engineering post; the morning keynote closes the loop on harness theory and frees you to spend the afternoon on context engineering.

### 10:10 - 10:30am | OpenClaw Update
**Peter Steinberger**

---

## Expo (10:30 - 11:08am)

### 10:30 - 10:48am | Wordsworth — Stop Babysitting Your Agents: Building a Context Engine for Mergeable Code
**Brandon Walsenuk**

> Catch this, then walk to St. James. Get there by 11:00 at the latest. **Your seat in St. James is your entire afternoon's logistics budget — do not gamble it.**

---

## St. James anchor — 11:15am to 3:30pm

### 11:15 - 11:40am | St. James — One Developer, Two Dozen Agents, Zero Alignment: Why We Need Collaborative AI Engineering
**Maggie Appleton**

| | |
|---|---|
| **Type** | Track Keynote |
| **Track** | Context Engineering |
| **Status** | **ANCHOR — CHOSEN** |

> **Why:** Multi-agent coordination is the gap in your current thinking. Your reading list covers single-agent harness theory (Lopopolo, Fowler, Anthropic) and context structuring (LangChain, Manus, Spotify) — but you have very little on what happens when multiple agents work the same codebase. Appleton is a strong thinker on information architecture and collaborative sense-making. **Listen for: what breaks when agents don't share mental models, and what protocols/artifacts keep them aligned.** This is the novel content of the day for you.
>
> **What you're giving up:** Lopopolo + Sapra AMA in Westminster. You'll have seen Lopopolo's full keynote 85 minutes earlier. DM your prepared Symphony question to both speakers post-conference.

### 11:40am - 12:00pm | St. James — Teaching Coding Agents to Do Spreadsheets
**Nuno Campos** — LangChain co-founder

| | |
|---|---|
| **Type** | Track Keynote |
| **Track** | Context Engineering |
| **Status** | **SOFT SLOT — stay seated, do not leave** |

> **Why this is a soft slot:** Nuno's confirmed title is narrower than the LangChain harness-architecture deep dive originally hoped for. Spreadsheets as structured data is a niche application. However, LangChain's depth on context engineering might still surface — **listen specifically for** how he treats spreadsheet cells as retrievable context units, and whether the pattern generalizes back to codebases (files, functions, call graphs as the code equivalent of cells).
>
> **Do not leave:** the walk to Moore for Danilo Campos's codegen fails talk costs you your St. James seat — and the next slot is Sally-Ann Delucia, which you absolutely cannot miss. Sit through Nuno, take what's useful, and stay put.

### 12:00 - 12:20pm | St. James — Hierarchical Memory: Context Management in Agents
**Sally-Ann Delucia** — Arize

| | |
|---|---|
| **Type** | Talk |
| **Track** | Context Engineering |
| **Status** | **ANCHOR — CHOSEN** |

> **Why:** Direct hit on `objectives.md` L38-41: *"How should agent memory and context be structured? What patterns exist for organizing what agents know and when they know it?"* Unix-philosophy memory hierarchy ("small, focused tools that do one thing well and compose infinitely") with new findings from thousands of deployed agents. You've read Anthropic's context engineering post, Manus's lessons from Manus, and LangChain's framework — Sally-Ann likely synthesizes these into a practical taxonomy. **Listen for: what percentage of memory operations are which type in production, and what fails.** The concrete numbers are what the blog posts leave out.

### 12:20 - 12:40pm | St. James — Personalization in the Era of LLMs
**Shivam Verma**

| | |
|---|---|
| **Type** | Talk |
| **Status** | **SOFT SLOT — stay seated** |

> **Why this is a soft slot:** Personalization is off-objective for coding agents. Use the time to: review Sally-Ann's memory hierarchy against your reading, draft questions for Pedro Rodrigues at 3:10, or think about how personalization patterns (per-user state management, preference learning) might map to per-project harness configuration.
>
> **Do not leave:** the walk to Moore costs the anchor. The next St. James slot is Bilge on sovereignty — also soft — but you need to protect the seat for the 2:30–3:30 afternoon block where St. James pulls ahead of the other rooms.

### 12:40 - 1:00pm | St. James — What Breaks When You Build AI Under Sovereignty Constraints
**Bilge Yücel**

| | |
|---|---|
| **Type** | Talk |
| **Status** | **SOFT SLOT — stay seated** |

> **Why this is a soft slot:** Regulatory/sovereignty constraints on AI architecture aren't on your objective list. But this is the third soft slot in a row in the St. James anchor — the 11:40–1:00 stretch is the weakness of this strategy. **Mitigation:** Use this 20 minutes to eat a snack and prepare for the afternoon block. You've got a three-slot sag but you're still in the seat that unlocks Pedro at 3:10.

---

## Lunch (1:00 - 2:30pm)

**Stay near St. James.** Same discipline as the Moore anchor: don't venture to the expo floor, don't chain expo sessions, don't gamble the seat.

**Suggested lunch play:**
- Grab food quickly near St. James
- Return to the St. James lobby by 2:00pm
- Sit outside the door if necessary

**If you must catch one expo:** The 1:45 Shelley "BDD, ADR, PRD, WTF: Capturing Decisions for Humans and AI Alike" is the highest-value expo of the day for the harness objective (capturing decisions for humans and agents). It ends at 2:03pm, which gives you 27 minutes to sprint back to St. James. Plausible but risky.

---

## St. James anchor — afternoon (2:30 - 3:30pm)

### 2:30 - 2:50pm | St. James — Connecting the Dots with Context Graphs
**Stephen Chin**

| | |
|---|---|
| **Type** | Talk |
| **Track** | Context Engineering |
| **Status** | **ANCHOR — CHOSEN (MEDIUM)** |

> **Why:** Alternative context paradigm — graph-structured rather than file-based. Your reading is heavily file/filesystem-biased (Manus, Anthropic, LangChain all converge on filesystem-as-externalized-memory), so graph structures are the first time you'll see a serious alternative. **Listen for:** where graphs beat filesystems (navigating relationships across files, cross-references), and where they lose (write amplification, lookup cost). This is not a replacement for your current model but a useful contrast for thinking about the limits of file-based context.

### 2:50 - 3:10pm | St. James — Context Graphs for Explainable, Decision-Aware AI Agents
**Andreas Kollegger, Zaid Zaim**

| | |
|---|---|
| **Type** | Talk |
| **Track** | Context Engineering |
| **Status** | **ANCHOR — CHOSEN (MEDIUM)** |

> **Why:** Second context graphs talk in a row — Neo4j-backed this time. The back-to-back pairing is either redundant or complementary; Chin's talk will probably frame the "why graphs" case and Kollegger/Zaim will cover the "how" with production details. **Listen for:** whether they cite concrete merge-rate or task-success numbers for graph-backed context vs. filesystem context. If neither talk has production data, graph-context remains theoretical and you should weight your notes accordingly.

### 3:10 - 3:30pm | St. James — Combine Skills and MCP to Close the Context Gap
**Pedro Rodrigues**

| | |
|---|---|
| **Type** | Talk |
| **Track** | Context Engineering |
| **Status** | **ANCHOR — CHOSEN — TIER 1** |

> **Why:** This is the reason the St. James anchor exists. Direct hit on `objectives.md` L35 (*"When should context live in a skill vs. behind an MCP server?"*) and L64 (*"Skills, MCP, and harness engineering as a stack"*). The Spotify Honk posts showed they prefer MCP for verification tools (because they work across thousands of repos) but static prompts for context. The HumanLayer post showed MCP can duplicate CLI functionality poorly. The Manus post showed why dynamic tool changes break KV-cache. Pedro likely has a framework for when to use which — and the main plan's note is categorical: **"Do not miss this one."**
>
> **Listen for:** concrete decision criteria (latency, repo coverage, cache hit rate) for choosing skill vs. MCP, and whether he has production data on the two used together vs. either alone. If he covers the static-vs-dynamic context distinction and the KV-cache stability story, you're watching the talk that closes the loop on your context-engineering reading list.
>
> **The anchor discipline pays off here.** Moore's 3:10 is Badertdinov on SWE-rebench (evals-heavy) — not on your prioritized list once you've stripped measurement. Westminster's 3:10 is Ostrikov on self-evolving agents (competition results). Pedro is the only Tier-1 session in the 3:10 slot once evals is out of the picture.

---

## Expo break (3:30 - 4:30pm)

Leave St. James at 3:30. The anchor obligation ends. Use the expo block for food, water, or one expo session if energy permits:

- **3:45 - 4:03pm | Shelley** — Phil Hetzel "How Agent O11y Differs from Traditional O11y" (less relevant with evals de-prioritized, but still touches on rich execution traces as context material)
- **3:45 - 4:03pm | Wordsworth** — Daniel Szoke "Why Rust is the Ideal Language for Vibe-Coding" (previews Matt Pocock's 5:20pm keynote on software fundamentals — Fowler's *harnessability* thesis)

Neither is required. Recovery matters more going into the afternoon keynotes.

---

## Afternoon keynotes (Keynote Stage — all attend)

### 4:30 - 5:00pm | Software Engineering + AI = ?
**Gergely Orosz, swyx**

> Gergely brings the skeptical senior-engineer perspective. swyx's IMPACT framework frames "Authority" as the oldest unsolved problem in agents. Connects to Hashimoto's skill formation concerns and Fowler's insight that the human's implicit harness (absorbed conventions, aesthetic judgment, organizational memory) is irreplaceable.

### 5:00 - 5:20pm | Keynote (title TBA)
**Kitze**

### 5:20 - 5:40pm | It Ain't Broke: Why Software Fundamentals Matter More Than Ever
**Matt Pocock**

> Counter-narrative to the "agents write all code" thesis. Fowler's article emphasized *harnessability* — strong typing and clearly definable module boundaries make harnesses possible. Pocock likely argues software fundamentals are the prerequisite for effective agent use, not a relic.

### 5:40 - 6:00pm | Keynote (title TBA)
**Sunil Pai**

---

## Summary: St. James Anchor Path

| Time | Room | Session | Status |
|---|---|---|---|
| 9:00-10:30am | Keynote | All morning keynotes (incl. Lopopolo) | **CHOSEN** |
| 10:30-10:48am | Wordsworth | Stop Babysitting Your Agents (Walsenuk) | **CHOSEN** |
| 11:15-11:40am | **St. James** | One Developer, Two Dozen Agents (Appleton) | **ANCHOR** |
| 11:40am-12:00pm | **St. James** | Teaching Coding Agents to do Spreadsheets (Nuno) | **SOFT — stay seated** |
| 12:00-12:20pm | **St. James** | Hierarchical Memory (Sally-Ann Delucia) | **ANCHOR** |
| 12:20-12:40pm | **St. James** | Personalization (Verma) | **SOFT — stay seated** |
| 12:40-1:00pm | **St. James** | Sovereignty Constraints (Bilge Yücel) | **SOFT — stay seated** |
| 1:00-2:30pm | Lunch | Stay near St. James; optional 1:45 Shelley BDD/ADR/PRD if time permits | — |
| 2:30-2:50pm | **St. James** | Connecting the Dots with Context Graphs (Chin) | **ANCHOR (M)** |
| 2:50-3:10pm | **St. James** | Context Graphs for Explainable AI (Kollegger, Zaim) | **ANCHOR (M)** |
| 3:10-3:30pm | **St. James** | Combine Skills and MCP (Pedro Rodrigues) | **ANCHOR — TIER 1** |
| 3:30-4:30pm | Expo / break | Leave St. James, recover | — |
| 4:30-6:00pm | Keynote | All afternoon keynotes | All attend |

**Room moves during track sessions: 0.**

---

## What you give up — accept it or pick another plan

| Loss | Mitigation |
|---|---|
| **Lopopolo + Sapra AMA (11:15 Westminster)** | 20-min Lopopolo keynote at 9:50 + entire harness-engineering post + DM questions post-conference |
| **Tejas Kumar harness deep dive (2:30 Westminster)** | Likely confirmation of Fowler/OpenAI/Anthropic canon you've already read |
| **Marc Klingen Skill Issue (12:20 Moore)** | Real loss for the skills objective. Mitigation: HumanLayer "Skill Issue" post, Anthropic skills docs, and Pedro Rodrigues at 3:10 covers skills as part of the skills+MCP stack |
| **Danilo Campos LLM Codegen Fails (11:40 Moore)** | Anthropic's "long-running agents" post catalogs failure modes; Drew Breunig's "How Long Contexts Fail" is the theoretical frame |
| **Three soft slots 11:40–1:00pm** | Use them for reading review and question drafting; accept them as the price of the Pedro Rodrigues afternoon |

---

## Decision gate: which anchor?

Three documents now describe possible Day 2 plans. Pick one based on your objective weighting:

| Plan | Best for |
|---|---|
| **`day2-april9.md`** (chosen path) | You're willing to accept three room-change risks in exchange for breadth across harness, context, and measurement with multiple Tier-1 peaks (Lopopolo AMA + Pedro + Ara Khan) |
| **`day2-april9-moore-anchor.md`** | Measurement is non-negotiable. 6 HIGH fit sessions in one room. You're OK losing Pedro Rodrigues because SWE-rebench is a similarly-strong measurement pick |
| **`day2-april9-stjames-anchor.md`** (this file) | Measurement is de-prioritized. Context engineering + skills/MCP stack + Pedro Rodrigues as Tier 1 anchor. You're OK sitting through a three-slot sag in the middle of the day to guarantee the Sally-Ann Delucia + Pedro Rodrigues combo |

**The St. James anchor is the right choice when:** you've decided the Lopopolo harness canon is already internalized from reading, Tejas Kumar can't tell you anything new, and the single most important session of the day is Pedro Rodrigues answering your explicit question about when to use skills vs. MCP.

**The St. James anchor is the wrong choice when:** you think three soft slots in a row is too long to sit still, or you'd rather have the Klingen Skill Issue talk over the back-to-back context-graphs MEDIUM sessions in the afternoon. In that case, pick the Moore anchor.
