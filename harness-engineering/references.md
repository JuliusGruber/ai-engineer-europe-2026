# Harness Engineering References

Key articles and papers on harness engineering, collected from [Harness Engineering: The Skill That Will Define 2026 for Solo Devs](https://www.youtube.com/watch?v=DN2mhf0b02s) by Solo Swift Crafter.

## Benchmarks

- **APEX-Agents** — Frontier models complete only ~24% of real professional tasks (consultants, lawyers, analysts), climbing to ~40% after 8 attempts. Tasks take a human 1-2 hours each.
  - [Paper (arXiv)](https://arxiv.org/abs/2601.14242)
  - [Leaderboard (Mercor)](https://www.mercor.com/apex/apex-agents-leaderboard/)

## Harness Engineering Guides

- **OpenAI — Harness Engineering** — Defines harness engineering and documents how OpenAI shipped ~1M LoC with zero human-written code using Codex. The harness (environment, constraints, feedback loops) matters more than the model.
  - [Harness engineering: leveraging Codex in an agent-first world](https://openai.com/index/harness-engineering/)

- **Anthropic — Effective Harnesses for Long-Running Agents** — Bridging context windows across sessions using progress files, structured environments, and incremental feature-by-feature work.
  - [Effective harnesses for long-running agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)

## Case Studies

- **Manus — Context Engineering Lessons** — Rebuilt their agent framework 5 times in 6 months. Biggest gains came from removing features, not adding them. File system as external memory, simple structured handoffs over complex routing.
  - [Context Engineering for AI Agents: Lessons from Building Manus](https://manus.im/blog/Context-Engineering-for-AI-Agents-Lessons-from-Building-Manus)

- **Vercel — We Removed 80% of Our Agent's Tools** — Text-to-SQL agent went from 80% to 100% accuracy by stripping specialized tools and giving the agent bash + file access. 40% fewer tokens, 3.5x faster.
  - [We removed 80% of our agent's tools](https://vercel.com/blog/we-removed-80-percent-of-our-agents-tools)

## Foundational Ideas

- **Richard Sutton — The Bitter Lesson (2019)** — Methods that scale with compute always beat hand-engineered knowledge. Applied to agents: as models get smarter, your harness should get simpler, not more complex.
  - [The Bitter Lesson](http://www.incompleteideas.net/IncIdeas/BitterLesson.html)
