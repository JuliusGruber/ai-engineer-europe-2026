# AI Engineer Europe 2026 - Personal Schedule

**Conference:** AI Engineer Europe 2026
**Dates:** April 8-10, 2026
**Venue:** Queen Elizabeth II Centre, London, UK
**Website:** https://ai.engineer/europe

---

## April 8 (Tuesday)

### 9:00 - 10:20am | St. James

**How to Build Agents That Run for Hours (Without Losing the Plot)**

| | |
|---|---|
| **Speakers** | Ash Prabaker, Andrew Wilson |
| **Company** | Anthropic |
| **Type** | Workshop |

---

### 10:40am - 12:00pm | Abbey

**Skills at Scale**

| | |
|---|---|
| **Speakers** | Nick Nisi, Zack Proser |
| **Type** | Workshop |

---

### 1:00 - 3:00pm | Wordsworth

**Mergeable by default: Building the context engine to save time and tokens**

| | |
|---|---|
| **Speaker** | Peter Werry |
| **Company** | Unblocked |
| **Type** | Workshop |

---

### 3:30 - 5:30pm | St. James (alt: Shelley)

**AI Coding For Real Engineers** (alt: Build Your First Demand-Driven Context Base)

| | |
|---|---|
| **Speaker** | Matt Pocock (alt: Raj Navakoti, IKEA Digital) |
| **Type** | Workshop |

---

## April 9 (Wednesday)

### 9:50 - 10:10am | Keynote Stage

**Harness Engineering: How to Build Software When Humans Steer and Agents Execute**

| | |
|---|---|
| **Speaker** | Ryan Lopopolo |
| **Role** | Member of Technical Staff @ OpenAI |
| **Type** | Keynote |
| **Links** | [Twitter](https://x.com/_lopopolo) · [LinkedIn](https://www.linkedin.com/in/ryanlopopolo/) · [GitHub](https://github.com/lopopolo) |

---

### 11:15 - 11:40am | Westminster

**Harness Engineering AMA**

| | |
|---|---|
| **Speaker** | Ryan Lopopolo |
| **Role** | Member of Technical Staff @ OpenAI |
| **Type** | Track Keynote |
| **Track** | Harness Engineering |
| **Links** | [Twitter](https://x.com/_lopopolo) · [LinkedIn](https://www.linkedin.com/in/ryanlopopolo/) · [GitHub](https://github.com/lopopolo) |

---

## April 10 (Thursday)

### 9:00 - 10:30am | Keynote Stage

**Morning Keynotes** (all on main stage)

| Time | Talk | Speaker | Why |
|------|------|---------|-----|
| 9:20-9:40am | **The Future of MCP** | David Soria Parra | MCP is a core primitive for context delivery to coding agents. Anthropic's MCP lead — expect protocol-level direction that shapes how skills and tools interact. |
| 9:40-10:00am | What Do Models Still Suck At? | Peter Gostev | Arena data on real failure modes. Knowing where models fail tells you what NOT to delegate (Hashimoto's negative space insight). |
| 10:10-10:30am | Building pi in a World of Slop | Mario Zechner | "A deliberately simple coding agent built on a small set of powerful primitives." Counter-narrative to complexity — connects to Vercel's "we removed 80% of tools" lesson. |

---

### 10:50 - 11:08am | Wesley (Expo Session)

**Two Roads to Durable Agents: Replay vs. Snapshot**

| | |
|---|---|
| **Speaker** | Eric Allam |
| **Type** | Expo Session |
| **Why** | Directly extends Anthropic's long-running harness papers from the reading list. Replay vs. snapshot is the architectural choice underlying session durability — the thing that makes "always have an agent running" (Hashimoto step 6) actually work. |

---

### 11:15 - 11:40am | Fleming

**Replacing 12K LoC with a 200 LoC Skill**

| | |
|---|---|
| **Speaker** | David Gomes |
| **Type** | Track Keynote |
| **Track** | Coding Agents |
| **Why** | Direct answer to "how do I get good at writing skills?" A 60x reduction in code via a single skill is the sharpest case study for progressive disclosure you'll see. Connects to HumanLayer's "skill issue" concept and Anthropic's Agent Skills standard. |

*Alt: Every API Is a Tool for Agents (Matt Carey, Cloudflare) in St. James — MCP tool discovery at scale, relevant to "when should context live in a skill vs. behind an MCP server"*

---

### 11:40am - 12:00pm | St. James

**Building Agent Interfaces: Lessons from Chrome DevTools MCP for Agents**

| | |
|---|---|
| **Speaker** | Michael Hablich |
| **Type** | Talk |
| **Track** | MCP |
| **Why** | Production lessons from shipping a real MCP server wrong, then fixing it. Monolithic tool → 26 composable tools. Error messages rewritten 3x for agent self-recovery. Token efficiency as core requirement, not optimization. Every lesson here is directly applicable to designing MCP tools that coding agents consume well — Fowler's "positive prompt injection" and "sensors" concepts in practice. |

---

### 12:00 - 12:20pm | Fleming

**The Year of Latency Debt (And How Big Tech Is Paying It Down)**

| | |
|---|---|
| **Speaker** | Sarah Chieng |
| **Type** | Talk |
| **Track** | Coding Agents |
| **Why** | 1,000+ tokens/sec changes the workflow. Practical playbook: smaller diffs, automated feedback loops, stop auto-accepting large code changes. This is the "corrections are cheap, waiting is expensive" principle (OpenAI harness engineering) taken to its logical conclusion. Directly addresses daily workflow design. |

---

### 12:20 - 12:40pm | Fleming

**Fighting AI with AI**

| | |
|---|---|
| **Speaker** | Lawrence Jones |
| **Company** | incident.io |
| **Type** | Talk |
| **Track** | Coding Agents |
| **Why** | They built a production system where AI agents debug other AI agents. The patterns transfer directly to coding agent harnesses: evals that work as a CLI runbook (agents can follow the process), filesystem serialization of agent traces for debugging, 25 parallel agents doing analysis then clustering results. Connects to "how do I debug long-running agent sessions?" and Manus's "preserve failure as evidence" principle. |

---

### 12:40 - 1:00pm | Fleming (alt: Westminster)

**Factory Missions — Super Long Running Agents** (alt: CI/CD Is Dead, Agents Need Continuous Compute)

| | |
|---|---|
| **Speakers** | Matan Grinberg, Luke Alvoeiro (alt: Hugo Santos, Madison Faulkner) |
| **Type** | Talk |
| **Track** | Coding Agents (alt: AI Architects) |
| **Why** | Factory Missions extends the Anthropic long-running agent patterns from the reading list — initializer/coder split, git as state, progress artifacts. The alt (CI/CD Is Dead) tackles the infrastructure bottleneck when agents open hundreds of PRs: runner saturation, cache thrash, test explosion. Both are real production concerns. Pick based on what felt underserved after the morning. |

---

### 1:25 - 1:43pm | Wesley (Expo Session)

**Stop babysitting your agents: building a context engine for mergeable code**

| | |
|---|---|
| **Speaker** | Brandon Walsenuk |
| **Type** | Expo Session |
| **Why** | **Do not miss this.** Hard numbers: same agent, same model — without organizational context took 2.5 hours and 20.9M tokens with multiple correction rounds; with context engine took 25 minutes and 10.8M tokens producing mergeable code first pass. This is the measurement objective made concrete. Directly answers "how do I know if changes to my harness are actually making things better?" with real merge rate and token cost data. |

---

### 2:30 - 2:50pm | Fleming (alt: Westminster)

**Your Coding Agent Should Do AI System Engineering** (alt: Software Engineering Is Becoming Plan and Review)

| | |
|---|---|
| **Speaker** | Ben Burtenshaw, HuggingFace (alt: Louis Knight-Webb) |
| **Type** | Talk |
| **Track** | Coding Agents (alt: AI Architects) |
| **Why** | Skills in production at HuggingFace: 1,000+ ML experiments daily, live demo of skill-augmented coding agents, benchmarks across six models, concrete playbook for when to trust agent output. Directly extends the skills thread from 11:15am. The alt addresses "where do humans add the most value in the loop?" — plan and review as the new engineering job. Choose based on whether you want deeper skills practice or the human-in-the-loop perspective. |

---

### 2:50 - 3:10pm | Fleming

**Let's Talk About FOMAT — Fear of Missing Agent Time**

| | |
|---|---|
| **Speaker** | Michael Richman |
| **Type** | Talk |
| **Track** | Coding Agents |
| **Why** | Practical tooling for Hashimoto's "always have an agent running" step. Monitor and interact with coding agents from phone/watch. Works with Claude Code, Codex, Gemini CLI. The control plane pattern for async agent management is a workflow multiplier. Lighter talk — good for energy management after a dense morning. |

---

### 3:10 - 3:30pm | Westminster

**Agents Don't Do Standups: Building the Post-Engineer Engineering Org**

| | |
|---|---|
| **Speaker** | Mike Spitz |
| **Type** | Talk |
| **Track** | AI Architects |
| **Why** | Production field report: 10x developer output, deploy cycles from 5 days to multiple daily. Agent-on-agent review replacing human review gates. Tiered human-in-the-loop for high-risk only. This is what "coding agents at scale" looks like when a team goes all-in. Guardrail architecture maps directly to Fowler's three harness types (maintainability, architecture fitness, behavior). |

---

### 4:05 - 4:23pm | Wordsworth (Expo Session)

**Benchmarking semantic code retrieval on Claude Code**

| | |
|---|---|
| **Type** | Expo Session |
| **Why** | Claude Code plugin for semantic codebase search, benchmarked against regex/glob/grep. Compares answer quality and token consumption with and without semantic retrieval. If you're using Claude Code daily, this directly affects your harness. |

---

### 4:30 - 4:50pm | Keynote Stage

**Fireside Chat with Gergely Orosz and Linear's Tuomas Artman**

| | |
|---|---|
| **Speakers** | Gergely Orosz, Tuomas Artman |
| **Type** | Keynote |
| **Why** | Gergely is the most widely-read engineering voice on how teams actually ship. Tuomas runs engineering at Linear, a tool company that dogfoods agents internally. Expect candid takes on what agent-assisted engineering looks like at a high-functioning team. |

---

### 5:20 - 5:40pm | Keynote Stage

**The Friction Is Your Judgment**

| | |
|---|---|
| **Speakers** | Armin Ronacher, Cristina Poncela Cubeiro |
| **Type** | Keynote |
| **Why** | Armin (creator of Flask, Rye, uv) is one of the most respected engineering minds in the ecosystem. The title says it: the friction you feel reviewing agent output IS your engineering judgment — don't optimize it away. This is the closing intellectual frame for everything you've learned: Hashimoto's negative space, Fowler's "human role" in harness engineering, and the question of where humans add the most value in the agent loop. |
