# Conference Objectives

What I want to learn and take home from AI Engineer Europe 2026.

**Scope:** Everything here is about being a better *user* of coding agents — improving my harness, context, and workflow so agents produce mergeable code in real codebases. I am not building agent-based applications for end users.

## Primary Goals

- Learn the entire discipline of making agents produce reliable code in real production codebases — harness engineering as defined by Lopopolo and Hashimoto: progressive disclosure, mechanical enforcement, feedback loops, garbage collection, and repository as single source of truth.
  - [OpenAI — "Harness engineering: leveraging Codex in an agent-first world"](https://openai.com/index/harness-engineering/)
  - [Mitchell Hashimoto — "My AI Adoption Journey"](https://mitchellh.com/writing/my-ai-adoption-journey)
- Results on real code or it didn't happen — filter every talk or workshop through: does this work on a production codebase with history, tech debt, and scale?
  - [Spotify — "Background Coding Agents: Context Engineering (Honk, Part 2)"](https://engineering.atspotify.com/2025/11/context-engineering-background-coding-agents-part-2)
- Learn how to measure whether my coding agent harness is actually producing better code — merge rate, first-pass acceptance, token efficiency — not building eval pipelines for agent products I ship to others.
  - [ETH Zurich AGENTbench study — context must be measured, not assumed](https://www.infoq.com/news/2026/03/agents-context-file-value-review/)
  - [APEX-Agents benchmark — frontier models complete only ~24% of real professional tasks](https://arxiv.org/abs/2601.14242)

## Priority Ranking

When sessions conflict, choose by this order:

1. **Harness Engineering** — this IS the discipline of getting results from agents in messy real codebases
2. **Coding Agents in Practice** — how teams apply harness engineering in production
3. **Context Engineering** — a critical subset of harness engineering, but a subset
4. **Measurement** — knowing if harness/context changes actually improve my coding agent's output (not eval frameworks for agent products)
5. **Meta** — interesting but won't change what you do Monday morning

## Context Engineering

- How to write, evaluate, and iterate on Agent Skills effectively
  - [Anthropic — Agent Skills open standard](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview)
  - [Anthropic — "Equipping Agents for the Real World with Agent Skills"](https://claude.com/blog/equipping-agents-for-the-real-world-with-agent-skills)
- Demand-driven context discovery: letting agents surface what context is missing instead of guessing what to curate
  - [Anthropic — "Effective context engineering for AI agents"](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)
- How skills and MCP combine in production — what the benchmarks actually show
  - [Anthropic — Agent Skills open standard](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview)
  - [Model Context Protocol](https://modelcontextprotocol.io/)
- Hierarchical memory and context management patterns (composable primitives for agent knowledge)
  - [Anthropic — "Effective context engineering for AI agents"](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)
  - [LangChain — "Context Engineering for Agents"](https://blog.langchain.com/context-engineering-for-agents/)
  - [Manus — "Context Engineering for AI Agents"](https://manus.im/blog/Context-Engineering-for-AI-Agents-Lessons-from-Building-Manus)
- How a context engine makes the difference between mergeable-on-first-pass and hours of wasted tokens
  - [Drew Breunig — "How Long Contexts Fail"](https://www.dbreunig.com/2025/06/22/how-contexts-fail-and-how-to-fix-them.html)
  - [Vercel — "We removed 80% of our agent's tools"](https://vercel.com/blog/we-removed-80-percent-of-our-agents-tools)

## Harness Engineering

- What a well-structured agent harness looks like (event sourcing, structured handoffs, parallel tool execution)
  - [LangChain — "The Anatomy of an Agent Harness"](https://blog.langchain.com/the-anatomy-of-an-agent-harness/)
  - [Martin Fowler — "Harness engineering for coding agent users"](https://martinfowler.com/articles/exploring-gen-ai/harness-engineering.html)
  - [OpenAI — "Unrolling the Codex agent loop"](https://openai.com/index/unrolling-the-codex-agent-loop/)
- How to manage state and debug long-running agents (traces as the primary debugging loop)
  - [Anthropic — "Effective harnesses for long-running agents"](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)
  - [Anthropic — "Harness design for long-running application development"](https://www.anthropic.com/engineering/harness-design-long-running-apps)
- Agent UX patterns: durable sessions, resumable streaming, interruption handling
  - [OpenAI — "Unlocking the Codex harness: how we built the App Server"](https://openai.com/index/unlocking-the-codex-harness/)
- Where harness engineering and context engineering meet — how a good harness enables better context delivery
  - [Martin Fowler — "Harness engineering for coding agent users"](https://martinfowler.com/articles/exploring-gen-ai/harness-engineering.html)

## Coding Agents in Practice

- Skills, MCP, and harness engineering as a stack
  - [Anthropic — Agent Skills open standard](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview)
- How production teams actually use coding agents at scale
  - [Spotify — "Background Coding Agents: Context Engineering (Honk, Part 2)"](https://engineering.atspotify.com/2025/11/context-engineering-background-coding-agents-part-2)
- Evaluation pipelines for agentic coding workflows — how to know if improvements actually work?
  - [Dex Horthy — Advanced Context Engineering for Coding Agents](https://github.com/humanlayer/advanced-context-engineering-for-coding-agents)
  - [ETH Zurich AGENTbench study — context must be measured, not assumed](https://www.infoq.com/news/2026/03/agents-context-file-value-review/)
  - [SWE-ContextBench — first benchmark for context reuse in coding agents](https://arxiv.org/abs/2602.08316)
  - [Spotify — "Predictable Results Through Strong Feedback Loops (Honk, Part 3)"](https://engineering.atspotify.com/2025/12/feedback-loops-background-coding-agents-part-3)


