# Context Engineering References

A curated collection of the most influential sources on context engineering for AI coding agents -- the discipline of dynamically constructing the right information, tools, and guidance to give an LLM everything it needs to accomplish coding tasks reliably. Sources are organized by category and ordered by influence within each category.

---

## Origin Sources

The tweets and posts that named and popularized "context engineering" during its crystallization week in June 2025.

- **Dex Horthy / HumanLayer -- 12-Factor Agents** (April 2025) -- [github.com/humanlayer/12-factor-agents](https://github.com/humanlayer/12-factor-agents)
  Earliest known use of the term as a named practice. "LLMs are stateless functions. Everything is context engineering. Own your state and control flow." The AI Engineer conference later credited Horthy as the coiner. Source: [x.com/aiDotEngineer/status/1940876485939564586](https://x.com/aiDotEngineer/status/1940876485939564586)

- **Tobi Lutke (Shopify) -- X post** (June 19, 2025) -- [x.com/tobi/status/1935533422589399127](https://x.com/tobi/status/1935533422589399127)
  The catalytic moment. "I really like the term 'context engineering' over prompt engineering. It describes the core skill better: the art of providing all the context for the task to be plausibly solvable by the LLM." Later endorsed DSPy as his "context engineering tool of choice."

- **Andrej Karpathy -- X post** (June 25, 2025) -- [x.com/karpathy/status/1937902205765607626](https://x.com/karpathy/status/1937902205765607626)
  Gave the term technical legitimacy: "+1 for 'context engineering' over 'prompt engineering'... the delicate art and science of filling the context window with just the right information for the next step." From the person who coined "vibe coding" months earlier.

- **Simon Willison -- "Context engineering"** (June 27, 2025) -- [simonwillison.net/2025/jun/27/context-engineering/](https://simonwillison.net/2025/jun/27/context-engineering/)
  Argued the term would stick because its inferred definition matches its intended meaning, unlike "prompt engineering." Picked up by Techmeme.

- **swyx / AI News -- "Context Engineering: Much More than Prompts"** (June 25, 2025) -- [news.smol.ai/issues/25-06-25-context-eng](https://news.smol.ai/issues/25-06-25-context-eng)
  Synthesized the emerging discourse with quotes from Karpathy, Harrison Chase, Lance Martin, and Tobi Lutke.

---

## Foundational Guides

The articles that defined the practice, provided frameworks, and established the field's vocabulary.

- **Phil Schmid (Hugging Face) -- "The New Skill in AI is Not Prompting, It's Context Engineering"** (June 30, 2025) -- [philschmid.de/context-engineering](https://www.philschmid.de/context-engineering)
  Most widely cited definition and seven-component framework (system prompt, user prompt, state/history, long-term memory, RAG, tools, structured output). 915 points on Hacker News, 518 comments -- the breakout moment.

- **LangChain / Harrison Chase -- "The Rise of Context Engineering"** (June 23, 2025) -- [blog.langchain.com/the-rise-of-context-engineering/](https://blog.langchain.com/the-rise-of-context-engineering/)
  First systematic industry framework. Positioned prompt engineering as "a subset of context engineering." Credits Tobi Lutke, Ankur Goyal, Walden Yan, and Dex Horthy.

- **LangChain -- "Context Engineering for Agents"** (July 2, 2025, updated October 19, 2025) -- [blog.langchain.com/context-engineering-for-agents/](https://blog.langchain.com/context-engineering-for-agents/)
  The most detailed technical framework. Introduced the **write/select/compress/isolate** taxonomy that became the standard vocabulary. 11-minute read.

- **Lance Martin / LangChain -- "Context Engineering for Agents"** (June 23, 2025) -- [rlancemartin.github.io/2025/06/23/context_engineering/](https://rlancemartin.github.io/2025/06/23/context_engineering/)
  Grouped context engineering strategies across popular agents. 117 points on Hacker News. Also appeared on the Latent Space podcast and ran a community meetup (December 2025).

- **Anthropic -- "Effective context engineering for AI agents"** (September 29, 2025) -- [anthropic.com/engineering/effective-context-engineering-for-ai-agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)
  The field's most comprehensive technical guide. ~500K views. Introduced finite attention budget, hybrid loading (upfront + just-in-time + demand-driven), progressive disclosure, sub-agent isolation, scratchpad note-taking, and compaction. 148 points on Hacker News.

- **Manus / Yichao "Peak" Ji -- "Context Engineering for AI Agents: Lessons from Building Manus"** (July 18, 2025) -- [manus.im/blog/Context-Engineering-for-AI-Agents-Lessons-from-Building-Manus](https://manus.im/blog/Context-Engineering-for-AI-Agents-Lessons-from-Building-Manus)
  The most technically detailed practitioner post. Six core lessons: KV-cache optimization (100:1 input-to-output ratio), tool masking via logits, file system as external memory, attention recitation via todo.md, error preservation in context, avoiding few-shot brittleness. Meta's ~$2B acquisition validated the thesis. 120 HN points.

- **Martin Fowler / Birgitta Boeckeler -- "Context Engineering for Coding Agents"** (February 5, 2026) -- [martinfowler.com/articles/exploring-gen-ai/context-engineering-coding-agents.html](https://martinfowler.com/articles/exploring-gen-ai/context-engineering-coding-agents.html)
  Structural vocabulary for coding agents: instructions vs. guidance, context interfaces, demand-driven loading. Warns of the "illusion of control": "There are no unit tests for context engineering." Enormous reach in the enterprise engineering community.

- **Addy Osmani -- "Context Engineering: Bringing Engineering Discipline to Prompts"** (July 13, 2025) -- [addyo.substack.com/p/context-engineering-bringing-engineering](https://addyo.substack.com/p/context-engineering-bringing-engineering)
  Later republished by O'Reilly in three parts. Three-facet model (instructional, knowledge, tools context). Directly addresses the "is this just rebranded prompt engineering?" critique.

---

## Context Failure and Optimization

Sources that define how context goes wrong and how to fix it.

- **Drew Breunig -- "How Long Contexts Fail"** (June 22, 2025) -- [dbreunig.com/2025/06/22/how-contexts-fail-and-how-to-fix-them.html](https://www.dbreunig.com/2025/06/22/how-contexts-fail-and-how-to-fix-them.html)
  Four failure modes: context poisoning, distraction, confusion, and clash. Referenced by Simon Willison in the Phil Schmid HN thread. Essential reading.

- **Drew Breunig -- "How to Fix Your Context"** (June 26, 2025) -- [dbreunig.com/2025/06/26/how-to-fix-your-context.html](https://www.dbreunig.com/2025/06/26/how-to-fix-your-context.html)
  Six remediation tactics including Tool Loadout, Context Quarantine, and Context Offloading. LangChain created a companion repo: [github.com/langchain-ai/how_to_fix_your_context](https://github.com/langchain-ai/how_to_fix_your_context).

- **Vercel -- "We removed 80% of our agent's tools"** (December 22, 2025) -- [vercel.com/blog/we-removed-80-percent-of-our-agents-tools](https://vercel.com/blog/we-removed-80-percent-of-our-agents-tools)
  Canonical "less is more" case study. Text-to-SQL agent went from 80% to 100% accuracy by stripping tools. 3.5x faster, 40% fewer tokens. "Don't fight gravity. File systems are an incredibly powerful abstraction."

- **Dex Horthy / HumanLayer -- Advanced Context Engineering** -- [github.com/humanlayer/advanced-context-engineering-for-coding-agents](https://github.com/humanlayer/advanced-context-engineering-for-coding-agents)
  Identified the "dumb zone" (40-60% of context window) where model recall degrades. Research-plan-implement workflow for coding agents.

---

## Production Case Studies

How organizations apply context engineering for coding agents at scale.

- **Spotify -- "Background Coding Agents: Context Engineering (Honk, Part 2)"** (November 24, 2025) -- [engineering.atspotify.com/2025/11/context-engineering-background-coding-agents-part-2](https://engineering.atspotify.com/2025/11/context-engineering-background-coding-agents-part-2)
  1,500+ merged PRs using Claude Code across ~50 migrations. Six context engineering principles: tailor to agent type, state preconditions, use concrete examples, define verifiable goals, single changes per prompt, request agent feedback. "Claude Code does better with prompts that describe the end state and leave room for figuring out how to get there."

- **Spotify -- "1,500+ PRs Later" (Honk, Part 1)** (November 2025) -- [engineering.atspotify.com/2025/11/spotifys-background-coding-agent-part-1](https://engineering.atspotify.com/2025/11/spotifys-background-coding-agent-part-1)
  System architecture and journey from homegrown agents to Claude Code as top-performing agent.

- **Spotify -- "Predictable Results Through Strong Feedback Loops (Honk, Part 3)"** (December 2025) -- [engineering.atspotify.com/2025/12/feedback-loops-background-coding-agents-part-3](https://engineering.atspotify.com/2025/12/feedback-loops-background-coding-agents-part-3)
  How feedback loops complement context engineering to improve agent reliability over time.

- **Supabase / Pedro Rodrigues -- "Combine Skills and MCP to Close the Context Gap"** -- AI Engineer Europe 2026 (talk April 9 + workshop April 8)
  Skills don't replace MCP -- they amplify it. Poorly designed or untested Skills can degrade performance. Eval methodology using Braintrust.

---

## Standards and Protocols

The open standards through which context engineering is practiced.

- **Anthropic -- "Equipping Agents for the Real World with Agent Skills"** (October 16, 2025) -- [claude.com/blog/equipping-agents-for-the-real-world-with-agent-skills](https://claude.com/blog/equipping-agents-for-the-real-world-with-agent-skills)
  By Barry Zhang, Keith Lazuka, Mahesh Murag. Describes the three-level progressive disclosure architecture that makes Skills a context engineering mechanism. Released as open standard December 18, 2025.

- **Anthropic -- Agent Skills (open standard)** (December 18, 2025) -- [platform.claude.com/docs/en/agents-and-tools/agent-skills/overview](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview)
  Markdown + YAML frontmatter. Platform reads only name and description at startup (~80 tokens); full body loads on demand (275-8,000 tokens). Adopted by OpenAI, Google, GitHub, and Cursor within weeks. [VentureBeat coverage](https://venturebeat.com/ai/anthropic-launches-enterprise-agent-skills-and-opens-the-standard).

- **Anthropic -- Model Context Protocol (MCP)** (November 2024, donated December 2025) -- [modelcontextprotocol.io](https://modelcontextprotocol.io/)
  Open standard for connecting agents to external data sources and tools. 6,400+ registered servers as of early 2026. Donated to Agentic AI Foundation under Linux Foundation. Created by David Soria Parra and Justin Spahr-Summers.

- **AGENTS.md** -- [agents.md](https://agents.md/)
  Open, tool-agnostic convention for repository-level agent instructions. 20,000+ GitHub repos. Stewarded by Agentic AI Foundation. GitHub blog: [How to write a great agents.md](https://github.blog/ai-and-ml/github-copilot/how-to-write-a-great-agents-md-lessons-from-over-2500-repositories/).

- **DSPy (Stanford NLP)** -- [github.com/stanfordnlp/dspy](https://github.com/stanfordnlp/dspy)
  Framework for programming (not prompting) language models. Tobi Lutke called DSPy his "context engineering tool of choice." Automates context optimization through compilation.

---

## Analysis & Commentary

- **MIT Technology Review -- "From vibe coding to context engineering: 2025 in software development"** (November 5, 2025) -- [technologyreview.com/2025/11/05/1127477/...](https://www.technologyreview.com/2025/11/05/1127477/from-vibe-coding-to-context-engineering-2025-in-software-development/)
  Mainstream validation. Published by Birgitta Boeckeler (Thoughtworks). Traces the shift from ad-hoc "vibe coding" to systematic context management.

- **Zep -- "What is Context Engineering, Anyway?"** -- [blog.getzep.com/what-is-context-engineering/](https://blog.getzep.com/what-is-context-engineering/)
  Clear definition and key distinction: "RAG is one flavor of context engineering." Memory management, tool integration, and session state are equally important.

- **Aurimas Griciuinas -- "State of Context Engineering in 2026"** -- [newsletter.swirlai.com/p/state-of-context-engineering-in-2026](https://www.newsletter.swirlai.com/p/state-of-context-engineering-in-2026)
  Current state assessment. Skills format adoption timeline and industry impact.

- **Neo4j / Andreas Kollegger -- "Context Graphs & Agentic Decisions"** (January 2026) -- [medium.com/neo4j/context-graphs-agentic-decisions-9a125f22f411](https://medium.com/neo4j/context-graphs-agentic-decisions-9a125f22f411)
  Context graphs as knowledge graphs for decision traces. Structured, multi-hop reasoning over persistent context.

- **Elvis Saravia (DAIR.AI) -- "Context Engineering Guide"** (July 5, 2025) -- [nlp.elvissaravia.com/p/context-engineering-guide](https://nlp.elvissaravia.com/p/context-engineering-guide)
  From the author of the Prompt Engineering Guide. Practical guide. 81 HN points.

- **Phil Schmid -- "Context Engineering for AI Agents: Part 2"** (December 4, 2025) -- [philschmid.de/context-engineering-part-2](https://www.philschmid.de/context-engineering-part-2)
  Follow-up to the breakout post. Performance degrades around <256K tokens even with 1M windows. Recommends hierarchical action spaces. "Biggest gains came from removing things."

- **ETH Zurich -- AGENTbench study** (March 2026) -- [infoq.com/news/2026/03/agents-context-file-value-review/](https://www.infoq.com/news/2026/03/agents-context-file-value-review/)
  138 real-world Python tasks. LLM-generated context files *reduced* success by ~3% and increased costs by 20%+. Human-written files: only +4% success. Critical finding: context must be measured, not assumed.

- **HumanLayer / Kyle -- "Skill Issue: Harness Engineering for Coding Agents"** (March 12, 2026) -- [humanlayer.dev/blog/skill-issue-harness-engineering-for-coding-agents](https://www.humanlayer.dev/blog/skill-issue-harness-engineering-for-coding-agents)
  Explicitly frames harness engineering as a subset of context engineering. Bridges the two disciplines.

---

## Precursor Documents

Work that established the patterns before the term existed.

- **Anthropic -- "Building Effective Agents"** (December 20, 2024) -- [anthropic.com/research/building-effective-agents](https://www.anthropic.com/research/building-effective-agents)
  Workflows vs agents distinction. Simple, composable patterns over complex frameworks. The intellectual precursor to context engineering discourse.

- **Richard Sutton -- "The Bitter Lesson" (2019)** -- [incompleteideas.net/IncIdeas/BitterLesson.html](http://www.incompleteideas.net/IncIdeas/BitterLesson.html)
  General methods leveraging computation always win over hand-engineered knowledge. Applied to context engineering: as models get more capable, simpler context strategies should beat complex ones.

---

## Benchmarks

- **SWE-ContextBench** -- [arxiv.org/abs/2602.08316](https://arxiv.org/abs/2602.08316)
  February 2026. First benchmark evaluating context reuse across coding tasks. Tests whether agents retain, adapt, and reuse experience.

- **Context-Bench (Letta)** (October 30, 2025) -- [letta.com/blog/context-bench](https://www.letta.com/blog/context-bench)
  Evaluates agentic context engineering: chaining file ops, tracing relationships, multi-step retrieval. Top results: Claude Sonnet 4.5 at 74.0% ($24.58), GPT-5 at 72.67% ($43.56). Even top performers miss 25-30%.

- **APEX-Agents** -- [arxiv.org/abs/2601.14242](https://arxiv.org/abs/2601.14242) | [Leaderboard](https://www.mercor.com/apex/apex-agents-leaderboard/)
  Frontier models complete ~24% of real professional tasks, climbing to ~40% after 8 attempts.

- **SWE-bench Verified** -- [swebench.com](https://www.swebench.com/)
  Standard benchmark for coding agents. Performance correlates heavily with context engineering quality.

---

## Academic Papers

| arXiv ID | Title | Date | Key Contribution |
|----------|-------|------|-----------------|
| **2510.04618** | Agentic Context Engineering: Evolving Contexts for Self-Improving Language Models | Oct 2025 | ACE framework: contexts as evolving playbooks. +10.6% on agent benchmarks. Open-sourced at github.com/ace-agent/ace. |
| **2510.21413** | Context Engineering for AI Agents in Open-Source Software | Oct 2025 | First empirical study of AI config files (CLAUDE.md, .cursorrules) in open-source. |
| **2602.05447** | Structured Context Engineering for File-Native Agentic Systems | Feb 2026 | 9,649 experiments across 11 models, 4 formats. File-based context +2.7% for frontier models. |
| **2602.14690** | Configuring Agentic AI Coding Tools: An Exploratory Study | Feb 2026 | 2,923 GitHub repos. 8 config mechanisms. AGENTS.md emerging as interoperable standard. |
| **2602.05447** | Structured Context Engineering for File-Native Agentic Systems | Feb 2026 | 9,649 experiments across 11 models, 4 formats. File-based context retrieval improves frontier model accuracy by +2.7%. |
| **2602.14690** | Configuring Agentic AI Coding Tools: An Exploratory Study | Feb 2026 | 2,923 GitHub repos analyzed. 8 configuration mechanisms identified. AGENTS.md emerging as interoperable standard. |
| **2602.20478** | Codified Context: Infrastructure for AI Agents in a Complex Codebase | Feb 2026 | Three-component infrastructure for 108K-line C# system: hot-memory, 19 specialist agents, 34 spec documents. |
| **2603.05344** | Building Effective AI Coding Agents for the Terminal | Mar 2026 | OPENDEV terminal agent. Context Engineering Layer with 4 subsystems: System Reminders, Prompt Composer, Memory, Compaction. |
| **2512.05470** | Everything is Context: Agentic File System Abstraction for Context Engineering | Dec 2025 | Unix-inspired file-system abstraction for managing heterogeneous context artifacts. |
| **2603.09619** | Context Engineering: From Prompts to Corporate Multi-Agent Architecture | Mar 2026 | Frames context engineering as standalone discipline for multi-agent information environments. |

---

## Hacker News Engagement

Top stories by points:

| Points | Comments | Date | Title |
|--------|----------|------|-------|
| 915 | 518 | Jun 30, 2025 | The new skill in AI is not prompting, it's context engineering (philschmid.de) |
| 473 | 255 | Mar 17, 2026 | Get Shit Done: A meta-prompting, context engineering and spec-driven dev system |
| 278 | 92 | Jul 31, 2025 | Gemini Embedding: Powering RAG and context engineering (Google) |
| 177 | 68 | Oct 23, 2025 | Context engineering is sleeping on the humble hyperlink |
| 148 | 32 | Sep 29, 2025 | Effective context engineering for AI agents (Anthropic) |
| 120 | 4 | Sep 23, 2025 | Context Engineering for AI Agents: Lessons (Manus) |
| 117 | 35 | Jul 1, 2025 | Context Engineering for Agents (Lance Martin) |
| 98 | 65 | Nov 2, 2025 | Context engineering (Chris Loy) |
| 81 | 28 | Jul 9, 2025 | Context Engineering Guide (Elvis Saravia) |

The term is firmly established in HN vocabulary, appearing in job listings and casual developer discourse.

---

## Community Tools and Awesome-Lists

| Repository | Description |
|------------|-------------|
| [Meirtz/Awesome-Context-Engineering](https://github.com/Meirtz/Awesome-Context-Engineering) | Comprehensive survey: hundreds of papers, frameworks, guides |
| [yzfly/awesome-context-engineering](https://github.com/yzfly/awesome-context-engineering) | Curated resources, papers, tools, best practices |
| [Agent-Skills-for-Context-Engineering](https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering) | Claude Code plugin marketplace. 2.3K stars in first week. |
| [context-engineering-kit](https://github.com/NeoLabHQ/context-engineering-kit) | Hand-crafted Claude Code skills for quality improvement |
| [awesome-agent-skills](https://github.com/skillmatic-ai/awesome-agent-skills) | Definitive resource for Agent Skills across platforms |
| [claude-skills](https://github.com/alirezarezvani/claude-skills) | 220+ skills for Claude Code, Codex, Gemini CLI, Cursor |
| [humanlayer/advanced-context-engineering-for-coding-agents](https://github.com/humanlayer/advanced-context-engineering-for-coding-agents) | Advanced techniques, "dumb zone" research |
| [davidkimai/Context-Engineering](https://github.com/davidkimai/Context-Engineering) | First-principles handbook inspired by Karpathy |
| [ace-agent/ace](https://github.com/ace-agent/ace) | ACE framework from Stanford/SambaNova paper |

---

## Key Practitioners

| Person | Affiliation | Key Contribution |
|--------|-------------|-----------------|
| **Dex Horthy** | HumanLayer | Coined "context engineering" (April 2025). 12-Factor Agents. "Dumb zone" research. |
| **Andrej Karpathy** | ex-OpenAI/Tesla | Popularized the term to mass audience (June 2025). Previously coined "vibe coding." |
| **Tobi Lutke** | Shopify | Catalyzed mainstream adoption (June 19, 2025). Endorsed DSPy. |
| **Phil Schmid** | ex-Hugging Face | Most viral article (915 HN points). Canonical 7-component definition. |
| **Harrison Chase** | LangChain | First systematic industry definition. Built LangGraph/LangSmith as CE infrastructure. |
| **Lance Martin** | LangChain | Write/select/compress/isolate taxonomy. Podcast, meetup, blog. |
| **Yichao "Peak" Ji** | Manus | Most technically detailed practitioner account. KV-cache optimization, attention recitation. |
| **Simon Willison** | Independent | Influential endorsement. Predicted the term would stick. |
| **Drew Breunig** | Independent | Context failure taxonomy (poisoning, distraction, confusion, clash). |
| **Birgitta Boeckeler** | Thoughtworks | Martin Fowler site treatment. Enterprise vocabulary. "Illusion of control" warning. |
| **Addy Osmani** | Google | Three-facet model. O'Reilly republication. |
| **swyx (Shawn Wang)** | AI Engineer, Latent Space | Founded AI Engineer conference series. IMPACT framework. "Agent engineering." |
| **Anthropic Applied AI** | Anthropic | Authoritative guide (Sept 2025). Built MCP and Skills standard. |

---

## Where the Field Is Heading

Context engineering has evolved from a naming debate (June 2025) to a recognized discipline with foundational literature, open standards, academic research, dedicated conference tracks, and production deployments at companies like Spotify, Supabase, and Shopify. Gartner has identified "context engineers" as a new specialized role for 2026.

Key trends:
- **Skills as the dominant context delivery mechanism** -- absorbing rules, slash commands, and static guidance into lazy-loaded, measurable packages
- **MCP ecosystem growth** -- 6,400+ servers and expanding; the standardized plumbing for agent-to-world context access
- **Eval-driven context design** -- Supabase and others showing context choices must be validated through benchmarks, not intuition
- **Context graphs** -- Neo4j and others extending beyond flat retrieval to structured, multi-hop reasoning over persistent knowledge
- **Convergence with harness engineering** -- the two disciplines are deeply intertwined; the harness enables context delivery, context quality determines harness effectiveness
