# Conference Objectives

What I want to learn and take home from AI Engineer Europe 2026.

**Scope:** Everything here is about being a better *user* of coding agents — improving my harness, context, and workflow so agents produce mergeable code in real codebases. I am not building agent-based applications for end users.

## Primary Goals

- Learn the entire discipline of making agents produce reliable code in real production codebases — harness engineering as defined by Lopopolo and Hashimoto: progressive disclosure, mechanical enforcement, feedback loops, garbage collection, and repository as single source of truth.
  - [OpenAI — "Harness engineering: leveraging Codex in an agent-first world"](https://openai.com/index/harness-engineering/)
  - [Mitchell Hashimoto — "My AI Adoption Journey"](https://mitchellh.com/writing/my-ai-adoption-journey)
- Results on real code or it didn't happen — filter every talk or workshop through: does this work on a production codebase with history, tech debt, and scale?
  - [Spotify — "Background Coding Agents: Context Engineering (Honk, Part 2)"](https://engineering.atspotify.com/2025/11/context-engineering-background-coding-agents-part-2)
- Learn how to measure whether my coding agent harness is actually producing better code — merge rate, token cost, review cycles — not building eval pipelines for agent products I ship to others.
  - [ETH Zurich AGENTbench study — context must be measured, not assumed](https://www.infoq.com/news/2026/03/agents-context-file-value-review/)

## What to Look For

When choosing between sessions, ask:

- **Does it work on a real codebase?** Techniques must transfer to repos with history, tech debt, and scale — not clean demos on greenfield code.
- **Can I apply this when I get home?** Not theory — a change I can make to my harness, context setup, or workflow immediately.
- **Is the speaker running this in production?** Prioritize teams shipping with coding agents at scale over prototypes and research-only results.
- **Does it improve how I steer agents or what agents see?** The techniques that move merge rate give agents better guardrails, better information, or both.
- **Can I measure the improvement?** If a change doesn't show up in merge rate, review cycles, or token cost — it's vibes.
- **Is it about using coding agents, not building agent apps?** Filter out sessions about shipping AI products to end users or eval frameworks for agent applications.

## Context Engineering

- How do I get good at writing skills? What makes a skill effective vs. bloated, and how do I know when one needs rework?
  - [Anthropic — Agent Skills open standard](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview)
  - [Anthropic — "Equipping Agents for the Real World with Agent Skills"](https://claude.com/blog/equipping-agents-for-the-real-world-with-agent-skills)
- How do I stop guessing what context to give agents and let them tell me what's missing?
  - [Anthropic — "Effective context engineering for AI agents"](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)
- How do skills and MCP work together in practice, and what does the data say about the combination?
  - [Anthropic — Agent Skills open standard](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview)
  - [Model Context Protocol](https://modelcontextprotocol.io/)
- How should agent memory and context be structured? What patterns exist for organizing what agents know and when they know it?
  - [Anthropic — "Effective context engineering for AI agents"](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)
  - [LangChain — "Context Engineering for Agents"](https://blog.langchain.com/context-engineering-for-agents/)
  - [Manus — "Context Engineering for AI Agents"](https://manus.im/blog/Context-Engineering-for-AI-Agents-Lessons-from-Building-Manus)
- What makes the difference between an agent that produces mergeable code on the first try and one that burns through tokens going in circles?
  - [Drew Breunig — "How Long Contexts Fail"](https://www.dbreunig.com/2025/06/22/how-contexts-fail-and-how-to-fix-them.html)
  - [Vercel — "We removed 80% of our agent's tools"](https://vercel.com/blog/we-removed-80-percent-of-our-agents-tools)

## Harness Engineering

- What does a well-designed harness actually look like? What are the architectural patterns that make agents reliable?
  - [LangChain — "The Anatomy of an Agent Harness"](https://blog.langchain.com/the-anatomy-of-an-agent-harness/)
  - [Martin Fowler — "Harness engineering for coding agent users"](https://martinfowler.com/articles/exploring-gen-ai/harness-engineering.html)
  - [OpenAI — "Unrolling the Codex agent loop"](https://openai.com/index/unrolling-the-codex-agent-loop/)
- How do I debug agents that run for hours? What's the equivalent of a stack trace when the failure happened 45 minutes ago?
  - [Anthropic — "Effective harnesses for long-running agents"](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)
  - [Anthropic — "Harness design for long-running application development"](https://www.anthropic.com/engineering/harness-design-long-running-apps)
- How should agent sessions handle real-world interruptions — network drops, user pauses, context switches — without losing progress?
  - [OpenAI — "Unlocking the Codex harness: how we built the App Server"](https://openai.com/index/unlocking-the-codex-harness/)
- How does the way I design my codebase affect how effective agents are at working in it?
  - [Martin Fowler — "Harness engineering for coding agent users"](https://martinfowler.com/articles/exploring-gen-ai/harness-engineering.html)
- Where harness engineering and context engineering meet — how a good harness enables better context delivery
  - [Martin Fowler — "Harness engineering for coding agent users"](https://martinfowler.com/articles/exploring-gen-ai/harness-engineering.html)

## Coding Agents in Practice

- Skills, MCP, and harness engineering as a stack
  - [Anthropic — Agent Skills open standard](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview)
- How production teams actually use coding agents at scale
  - [Spotify — "Background Coding Agents: Context Engineering (Honk, Part 2)"](https://engineering.atspotify.com/2025/11/context-engineering-background-coding-agents-part-2)
- What does the full daily workflow look like — from a vague requirement to merged code — when coding agents do the implementation? Where do humans add the most value in that loop?
  - [Mitchell Hashimoto — "My AI Adoption Journey"](https://mitchellh.com/writing/my-ai-adoption-journey)
- How do I know if changes to my harness or context setup are actually making things better, or if I'm just chasing vibes?
  - [Dex Horthy — Advanced Context Engineering for Coding Agents](https://github.com/humanlayer/advanced-context-engineering-for-coding-agents)
  - [ETH Zurich AGENTbench study — context must be measured, not assumed](https://www.infoq.com/news/2026/03/agents-context-file-value-review/)
  - [SWE-ContextBench — first benchmark for context reuse in coding agents](https://arxiv.org/abs/2602.08316)
  - [Spotify — "Predictable Results Through Strong Feedback Loops (Honk, Part 3)"](https://engineering.atspotify.com/2025/12/feedback-loops-background-coding-agents-part-3)
