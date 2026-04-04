# Harness Engineering References

A curated collection of the most influential sources on harness engineering, the emerging discipline of designing the environment, constraints, and feedback loops around AI agents. The original six entries were collected from [Harness Engineering: The Skill That Will Define 2026 for Solo Devs](https://www.youtube.com/watch?v=DN2mhf0b02s) by Solo Swift Crafter. This expanded list incorporates additional foundational work, major guides, academic research, and practitioner commentary.

---

## Foundational Sources

The origin articles that coined the term, defined the practice, or established key principles.

- **Mitchell Hashimoto — "My AI Adoption Journey"** — [mitchellh.com/writing/my-ai-adoption-journey](https://mitchellh.com/writing/my-ai-adoption-journey)
  Creator of Terraform and Ghostty. Coined "Engineer the Harness" as a practice. His formulation -- "every time the agent makes a mistake, engineer the environment so it can't make that mistake again" -- is why the term stuck.

- **OpenAI — "Harness engineering: leveraging Codex in an agent-first world"** — [openai.com/index/harness-engineering/](https://openai.com/index/harness-engineering/)
  Defines harness engineering and documents how OpenAI shipped ~1M LoC with zero human-written code using Codex. The harness (environment, constraints, feedback loops) matters more than the model.

- **Vercel — "We removed 80% of our agent's tools"** — [vercel.com/blog/we-removed-80-percent-of-our-agents-tools](https://vercel.com/blog/we-removed-80-percent-of-our-agents-tools)
  Text-to-SQL agent went from 80% to 100% accuracy by stripping specialized tools and giving the agent bash + file access. 40% fewer tokens, 3.5x faster. A landmark case for "simplify the harness" thinking.

- **Manus — "Context Engineering for AI Agents: Lessons from Building Manus"** — [manus.im/blog/Context-Engineering-for-AI-Agents-Lessons-from-Building-Manus](https://manus.im/blog/Context-Engineering-for-AI-Agents-Lessons-from-Building-Manus)
  Rebuilt their agent framework 5 times in 6 months. Biggest gains came from removing features, not adding them. File system as external memory, simple structured handoffs over complex routing.

- **Richard Sutton — "The Bitter Lesson" (2019)** — [incompleteideas.net/IncIdeas/BitterLesson.html](http://www.incompleteideas.net/IncIdeas/BitterLesson.html)
  Methods that scale with compute always beat hand-engineered knowledge. Applied to agents: as models get smarter, your harness should get simpler, not more complex.

---

## Guides & Frameworks

Detailed how-to guides and conceptual frameworks from major organizations and practitioners.

- **Anthropic — "Effective harnesses for long-running agents"** — [anthropic.com/engineering/effective-harnesses-for-long-running-agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)
  Bridging context windows across sessions using progress files, structured environments, and incremental feature-by-feature work.

- **Anthropic — "Harness design for long-running application development"** — [anthropic.com/engineering/harness-design-long-running-apps](https://www.anthropic.com/engineering/harness-design-long-running-apps)
  Companion to the first Anthropic guide. Focuses on harness design patterns for sustained application development workflows.

- **OpenAI — "Unlocking the Codex harness: how we built the App Server"** — [openai.com/index/unlocking-the-codex-harness/](https://openai.com/index/unlocking-the-codex-harness/)
  Technical companion to the main harness engineering post. Details the JSON-RPC protocol underpinning all Codex surfaces.

- **OpenAI — "Unrolling the Codex agent loop"** — [openai.com/index/unrolling-the-codex-agent-loop/](https://openai.com/index/unrolling-the-codex-agent-loop/)
  Detailed walkthrough of the Codex agent execution loop internals. Shows how harness design translates into actual agent behavior at runtime.

- **Martin Fowler / Birgitta Boeckeler — "Harness engineering for coding agent users"** — [martinfowler.com/articles/exploring-gen-ai/harness-engineering.html](https://martinfowler.com/articles/exploring-gen-ai/harness-engineering.html)
  Part of the "Exploring Gen AI" series. Defines Agent = Model + Harness. Introduces the guides/sensors framework (feedforward vs feedback controls). Enormous reach in the enterprise engineering community.

- **LangChain — "The Anatomy of an Agent Harness"** — [blog.langchain.com/the-anatomy-of-an-agent-harness/](https://blog.langchain.com/the-anatomy-of-an-agent-harness/)
  March 2026. Deconstructs harness components from first principles: planning, self-verification, hooks/middleware, skills, subagents, memory.

- **swyx — "Agent Engineering" keynote + IMPACT framework** — [latent.space/p/agent](https://www.latent.space/p/agent)
  Coined "agent engineering" at AI Engineer Summit 2025. Defined the IMPACT framework (Intent, Memory, Planning, Authority, Control Flow, Tools). Predates "harness engineering" but provided much of its conceptual scaffolding.

---

## Benchmarks

- **APEX-Agents** — Frontier models complete only ~24% of real professional tasks (consultants, lawyers, analysts), climbing to ~40% after 8 attempts. Tasks take a human 1-2 hours each.
  - [Paper (arXiv)](https://arxiv.org/abs/2601.14242)
  - [Leaderboard (Mercor)](https://www.mercor.com/apex/apex-agents-leaderboard/)

---

## Analysis & Commentary

Practitioner analysis, definitions, and commentary that sharpen the field's vocabulary.

- **HumanLayer / Dex Horthy — "Skill Issue: Harness Engineering for Coding Agents"** — [humanlayer.dev/blog/skill-issue-harness-engineering-for-coding-agents](https://www.humanlayer.dev/blog/skill-issue-harness-engineering-for-coding-agents)
  Defines harness engineering as "the subset of context engineering which primarily involves leveraging harness configuration points." Also author of the "No Vibes Allowed" talk.

- **Simon Willison — "How coding agents work" (Agentic Engineering Patterns)** — [simonwillison.net/guides/agentic-engineering-patterns/how-coding-agents-work/](https://simonwillison.net/guides/agentic-engineering-patterns/how-coding-agents-work/)
  Defines "a coding agent as a piece of software that acts as a harness for an LLM." Clear, practical framing from one of the most trusted voices in the developer tooling space.

- **Phil Schmid (Hugging Face) — "The importance of Agent Harness in 2026"** — [philschmid.de/agent-harness-2026](https://www.philschmid.de/agent-harness-2026)
  Hugging Face's perspective on why harness design has become a first-class concern for agent developers in 2026.

- **Louis Bouchard — "Harness Engineering: The Missing Layer Behind AI Agents"** — [louisbouchard.ai/harness-engineering/](https://www.louisbouchard.ai/harness-engineering/)
  Clearest distinction in the space: "Prompt engineering is what to ask. Context engineering is what to send. Harness engineering is how the whole thing operates."

---

## Academic Papers

Peer-reviewed and preprint research formalizing harness engineering concepts.

- **AutoHarness** (Google DeepMind) — [arxiv.org/abs/2603.03329](https://arxiv.org/abs/2603.03329)
  March 2026. Shows a smaller model with a synthesized harness beats larger models on 145 TextArena games. Accepted at ICLR 2026 workshop.

- **OPENDEV** — [arxiv.org/abs/2603.05344](https://arxiv.org/abs/2603.05344)
  March 2026. Introduces an open-source CLI coding agent. Serves as a practical guide to harness architecture.

- **Natural-Language Agent Harnesses** — [arxiv.org/abs/2603.25723](https://arxiv.org/abs/2603.25723)
  March 2026. First paper to treat harness design as a portable, studyable artifact independent of any particular agent.

- **Meta-Harness** — [arxiv.org/abs/2603.28052](https://arxiv.org/abs/2603.28052)
  March 2026. Outer-loop harness optimization. Improves over SOTA context management by 7.7 points using 4x fewer tokens.

---

## Where the Field Is Heading

Harness engineering is converging from multiple directions -- practitioner blog posts, enterprise frameworks, and now academic papers -- into a recognizable discipline. The trend is clear: as models grow more capable, the differentiator shifts from what you prompt to how you structure the entire system around the model. Expect harness design to become as standard a software engineering concern as API design or CI/CD pipeline architecture.
