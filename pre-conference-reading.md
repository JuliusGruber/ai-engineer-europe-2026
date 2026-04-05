# Pre-Conference Reading

Read in this order. Each builds on the previous. The "look for" notes tell you what to extract that will make conference sessions more valuable.

| # | Source | Time | Look For |
|---|--------|------|----------|
| 1 | [Mitchell Hashimoto - My AI Adoption Journey](https://mitchellh.com/writing/my-ai-adoption-journey) | 20 min | The six-step progression: drop chatbot -> reproduce work -> end-of-day agents -> outsource slam dunks -> engineer the harness -> always running. Note "verification is the single biggest lever" and the negative space insight (knowing what NOT to delegate). |
| 2 | [OpenAI - Harness Engineering](https://openai.com/index/harness-engineering/) | 30 min | AGENTS.md as ~100 lines (a map, not a manual). The architectural layering (Types -> Config -> Repo -> Service -> Runtime -> UI). Doc-gardening agents. Entropy management ("garbage collection"). "Corrections are cheap, waiting is expensive." **This is what Lopopolo's keynote will expand on.** |
| 3 | [OpenAI - Unrolling the Codex Agent Loop](https://openai.com/index/unrolling-the-codex-agent-loop/) | 25 min | The five-stage loop. Prompt construction layers (system -> developer -> environment -> user). How prompt caching exploits prefix stability. Automatic compaction via `encrypted_content`. Why reasoning tokens persist within a turn but not across turns. **This gives you the technical depth for the AMA.** |
| 4 | [Anthropic - Effective Harnesses for Long-Running Agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents) | 25 min | Two-agent pattern: initializer + coding agent. The startup sequence (verify dir, read progress, review git, launch dev, run smoke tests). Feature lists with boolean completion status. Git as state management. |
| 5 | [Anthropic - Harness Design for Long-Running Apps](https://www.anthropic.com/engineering/harness-design-long-running-apps) | 25 min | The GAN-inspired generator/evaluator split. Sprint contracts. "Context anxiety" (Sonnet 4.5 prematurely wrapping up near perceived context limits). And critically: when Opus 4.6 arrived, they removed components -- "every component encodes an assumption about what the model can't do." |
| 6 | [Martin Fowler - Harness Engineering for Coding Agent Users](https://martinfowler.com/articles/exploring-gen-ai/harness-engineering.html) | 30 min | Agent = Model + Harness. Guides (feedforward) vs sensors (feedback). Computational vs inferential controls. "Positive prompt injection" (custom linter messages optimized for LLM consumption). Three harness types: maintainability, architecture fitness, behavior. The concept of "harnessability." Ashby's Law applied to agents. |
| 7 | [Vercel - We Removed 80% of Our Agent's Tools](https://vercel.com/blog/we-removed-80-percent-of-our-agents-tools) | 15 min | 80% -> 100% accuracy by removing tools. The critical prerequisite: well-documented data layer with consistent naming. Guardrails for weak models degrading strong model performance. |
| 8 | [Manus - Context Engineering for AI Agents](https://manus.im/blog/Context-Engineering-for-AI-Agents-Lessons-from-Building-Manus) | 25 min | KV-cache hit rate as #1 metric. Masking over removal. Todo-list recitation against lost-in-the-middle. Errors left in > clean retries. Filesystem as extended context. 100:1 input:output ratio. |

Total: ~3.5 hours. Read sources 1-3 before anything else -- they give you the vocabulary and the technical depth for Lopopolo's keynote and AMA.

**Optional deep reading** (if time allows):

| Source | Time | Why |
|--------|------|-----|
| [LangChain - Anatomy of an Agent Harness](https://blog.langchain.com/the-anatomy-of-an-agent-harness/) | 20 min | The Ralph Loop pattern. Filesystem as most foundational primitive. Context rot countermeasures. |
| [HumanLayer - Skill Issue](https://www.humanlayer.dev/blog/skill-issue-harness-engineering-for-coding-agents) | 20 min | Progressive disclosure via skills. Sub-agents as "context firewalls." The "dumb zone" concept. Back-pressure mechanisms. |
| [swyx - Agent Engineering / IMPACT](https://www.latent.space/p/agent) | 20 min | IMPACT framework (Intent, Memory, Planning, Authority, Control flow, Tools). Editable plans as sweet spot. Authority as the oldest unsolved problem. |
| [Meta-Harness paper](https://arxiv.org/abs/2603.28052) | 30 min | The 6x performance gap. Automated harness optimization. Why the proposer needs rich execution traces, not just summaries. |
