# Harness Engineering: A Definition from Primary Sources

This document synthesizes a definition of harness engineering from its foundational sources. Every claim is traceable to the sources listed at the end.

---

## What Harness Engineering Is

Harness engineering is the discipline of designing the systems, constraints, feedback loops, and operational infrastructure that wrap around an AI model to make an agent reliable in production.

The foundational equation:

> **Agent = Model + Harness**

The harness is everything in an AI agent except the model itself. It is not the agent. It is the software system that governs how the agent operates: the tools it can access, the guardrails that keep it safe, the feedback loops that help it self-correct, the state management that lets it persist across sessions, and the verification systems that catch errors before they ship.

Martin Fowler's team provides the most precise structural definition: the harness encompasses both the agent builder's internal harness (the orchestration code, tool definitions, execution logic) and the user's outer harness (the documentation, tests, linters, and repository configuration that a human sets up for their specific use case). For coding agents, both layers matter.

Louis Bouchard draws the clearest distinction between adjacent concepts:

> "Prompt engineering is what to ask. Context engineering is what to send the model so that it can answer confidently. Harness engineering is how the whole thing operates."

---

## Core Principles

The following principles appear across multiple independent sources. They represent the emerging consensus.

### 1. Engineer the Environment, Not the Model

Every source agrees on this fundamental shift. Rather than waiting for better models, harness engineers design the environment so the agent cannot make the same class of mistake twice. Mitchell Hashimoto's formulation is the most direct: "Every time you discover an agent has made a mistake, you take the time to engineer a solution so that it can never make that mistake again."

OpenAI's Codex team demonstrated this at scale: a small team produced roughly one million lines of production code without manually writing source code. The engineers did not write code. They designed constraints, feedback loops, documentation, and lifecycle management -- the harness.

### 2. Enforce Invariants, Not Instructions

OpenAI's key rule of thumb: enforce invariants rather than micromanage implementations. Their Codex agents were required to parse data shapes at boundaries, but the team did not specify which library to use. The harness defines the "what" and the boundaries, not the "how."

This principle appears in Anthropic's work as clean state discipline (each session must end with properly documented, tested, committed code) and in Fowler's framing as guides and sensors rather than step-by-step procedures.

### 3. The Repository Is the Source of Truth

OpenAI states this bluntly: "Slack discussions, Google Docs, and tacit human knowledge are invisible to agents -- if it isn't discoverable in the repo, it effectively doesn't exist for the agent." Documentation must be machine-readable and co-located with code. Fowler's team calls these "machine-readable artifacts" -- scaffolding, constraints, and specifications encoded into files that agents can consume and execute.

### 4. Corrections Are Cheap, Waiting Is Expensive

When agents can generate and test changes faster than humans can review them, the bottleneck moves from code production to code approval. This requires redesigning the pipeline for throughput, not gatekeeping. OpenAI pushed almost all code review to agent-to-agent loops, escalating to humans only when judgment was required.

### 5. Start Simple, Add Complexity Only When Agents Fail

Every source converges here. Vercel removed 80% of their agent's tools and went from 80% to 100% accuracy, 3.5x faster execution, and 37% fewer tokens. Manus rebuilt their agent framework five times in six months; the biggest gains came from removing features, not adding them. HumanLayer's practical guidance: "Start simple. Add configuration only when agents demonstrably fail."

### 6. Incremental Over Comprehensive

Anthropic found that agents' tendency to "one-shot" entire applications caused failures. The solution: work feature-by-feature rather than attempting full implementation in single sessions. Each session ends in a clean, mergeable state. LangChain calls this the filesystem as the "most foundational harness primitive" because it enables work persistence across sessions.

### 7. Progressive Disclosure of Information and Tools

HumanLayer describes this as revealing capabilities only when needed: "Rather than overwhelming agents with all tools simultaneously, information and functionality activate based on task requirements." OpenAI frames it as "give the agent a map, not a 1,000-page instruction manual" -- context is a scarce resource, and a giant instruction file crowds out the task.

Manus operationalizes this through logit masking (constraining action spaces without removing tools from context) and what they call "attention recitation" -- continuously rewriting task summaries to keep goals in recent context.

---

## Key Components of a Harness

Synthesized from all sources, a harness contains the following functional layers:

### Guides (Feedforward Controls)

Controls that anticipate the agent's behavior and steer it before it acts. The goal is to increase the probability of good output on the first attempt.

- **System prompts and instruction files** (CLAUDE.md, AGENTS.md, docs directories)
- **Code documentation** as structured, machine-readable artifacts
- **Architectural rules** encoded as dependency constraints (e.g., OpenAI's Types -> Config -> Repo -> Service -> Runtime -> UI flow)
- **Tool definitions** that shape available actions
- **Progressive context loading** -- short maps up front, deeper sources pulled in on demand

### Sensors (Feedback Controls)

Controls that observe after the agent acts and enable self-correction before human review.

- **Tests** (unit, integration, end-to-end, structural)
- **Linters and type checkers** -- computational, deterministic, cheap to run frequently
- **Build verification** -- the code must compile and pass CI
- **AI code review** -- inferential, semantic analysis by another model instance
- **Back-pressure mechanisms** -- surface only failures; success should remain silent to avoid polluting context

### Execution Infrastructure

The runtime environment that enables autonomous action.

- **Sandboxed code execution** (bash, language runtimes)
- **Filesystem access** for durable storage, progress tracking, and cross-session persistence
- **Browser automation** for end-to-end verification
- **Git integration** for versioning, diffing, and clean-state enforcement

### Memory and State Management

Mechanisms for persisting understanding beyond a single context window.

- **Progress files** (claude-progress.txt, todo.md) that document previous work
- **Git commit history** as a structured log of what happened and why
- **Feature lists with completion status** (JSON or markdown with boolean "passes" fields)
- **Session initialization rituals** -- read directory, review git logs, consult progress files, run sanity tests before starting new work
- **Context compaction** -- compression strategies that are "restorable," preserving paths and URLs while dropping content temporarily

### Orchestration Logic

How work gets decomposed and distributed.

- **Sub-agents as context firewalls** -- isolating discrete tasks to prevent intermediate noise from accumulating in parent sessions
- **Agent-to-agent review loops** -- models reviewing each other's output with human escalation only when judgment is required
- **Initializer agents** that run once to set up the foundational environment, distinct from coding agents that do subsequent work
- **Lifecycle hooks** for workflow management at key transitions

### Verification and Guardrails

Systems that validate outputs and enforce safety.

- **Structural tests** that enforce architectural invariants
- **Format verification** and output validation
- **Safety filters** and permission boundaries
- **Deterministic middleware** (compaction, verification hooks)
- **Observability** -- telemetry, logs, metrics, spans for monitoring and reproducing issues

---

## Relationship to Adjacent Concepts

### Harness Engineering vs. Prompt Engineering

Prompt engineering focuses on crafting individual instructions to a model. It operates at the level of a single interaction: word choice, formatting, few-shot examples, chain-of-thought elicitation. Harness engineering operates at the system level: it designs the entire operational environment across many interactions. A prompt is one input to one call; a harness governs hundreds of calls across sessions.

### Harness Engineering vs. Context Engineering

Context engineering (championed by Andrej Karpathy in 2025) focuses on dynamically constructing the right information to send to the model: retrieved documents, conversation history, memory, structured state. HumanLayer positions harness engineering as "a specialized subset of context engineering, focusing on how configuration points manage context windows in coding agents." Manus's context engineering principles (KV-cache optimization, externalized memory, attention recitation, preserving failure signals) are techniques that a harness implements.

The distinction: context engineering asks "what does the model need to know right now?" Harness engineering asks "how does the entire system operate over time?" Context engineering is a critical component within harness engineering, but the harness also includes execution infrastructure, verification loops, orchestration, and state management that go beyond context curation.

### Harness Engineering vs. Agent Architecture / Frameworks

Cobus Greyling draws a clear architectural distinction: SDKs, frameworks, and scaffolding answer "how you build" an AI agent. The harness answers "how the agent runs." You can construct a harness using any framework -- it is an additional operational layer, not a replacement for build tools.

Phil Schmid extends the computer analogy: the model is the CPU, the context window is RAM, and the harness is the operating system -- managing initialization sequences, providing standard drivers (tool handling), and curating what gets loaded into working memory.

### Harness Engineering and The Bitter Lesson

Richard Sutton's 2019 essay argues that general methods leveraging computation always outperform hand-engineered domain knowledge in the long run. Applied to harnesses: as models get more capable, the harness should get simpler, not more complex. Vercel's experience validates this -- removing 80% of their tools improved every metric. The harness should provide structure and feedback, not try to encode human expertise into elaborate tool chains.

However, this creates a productive tension. The bitter lesson suggests minimal intervention; production reality demands guardrails. The resolution, evident across sources, is that harnesses should enforce invariants and provide feedback rather than encode domain heuristics. Let the model reason; constrain the boundaries.

---

## Philosophies and Points of Disagreement

### Minimal Harness vs. Layered Harness

**The minimalist position** (Vercel, Manus, Sutton's influence): fewer tools, simpler abstractions, trust the model. Vercel: "The best agents might be the ones with the fewest tools. Every tool is a choice you're making for the model." Manus arrived at the same conclusion after five rebuilds. Give the model bash, file access, and well-structured information. Get out of the way.

**The layered position** (OpenAI, Fowler, Anthropic): production systems need structured controls at multiple levels. Fowler identifies three regulation categories -- maintainability, architecture fitness, and behavioral correctness -- each requiring its own harness layer. OpenAI encodes "golden principles" into the repository and runs structured cleanup processes. Anthropic requires initializer agents, progress files, and environmental orientation rituals.

**The resolution** most sources arrive at: start minimal, add layers only when agents demonstrably fail, and prefer invariant enforcement over behavioral prescription. The complexity of the harness should be proportional to the reliability requirements of the use case.

### Who Owns the Harness?

OpenAI and Fowler draw a distinction between the **inner harness** (built by the agent/platform developer) and the **outer harness** (built by the user for their specific codebase). This creates a question of responsibility: should the platform provide a comprehensive harness, or should users engineer their own?

The emerging answer is "both." The platform provides execution infrastructure, orchestration primitives, and verification hooks. The user provides repository documentation, architectural rules, test suites, and domain-specific constraints. The user's harness is where the most leverage lives for coding agents, because it encodes the specific context of their codebase.

### Computational vs. Inferential Controls

Fowler introduces a useful distinction. **Computational controls** (tests, linters, type checkers) are deterministic, CPU-based, milliseconds to seconds, and cheap to run frequently. **Inferential controls** (AI code review, semantic analysis) are non-deterministic, GPU-based, slower, more expensive, but better for complex judgment. The question of how much to rely on each is unresolved -- more capable models may shift the balance toward inferential controls over time.

### How Much Planning Should the Harness Do?

Manus and LangChain argue the harness should provide planning and decomposition capabilities, guiding models through structured task sequences. OpenAI's position is closer to "let the model plan, enforce the boundaries." Phil Schmid recommends starting simple and avoiding massive control flows, letting models plan but preparing to replace logic as new model releases change capabilities.

---

## Timeline: How the Term Emerged

### Prehistory: The Bitter Lesson (2019)

Richard Sutton publishes "The Bitter Lesson," arguing that general methods leveraging computation always win over hand-engineered knowledge. This becomes a foundational reference for minimalist harness design philosophy years later.

### 2024: Agent Scaffolding

The term "scaffolding" is widely used in the agent community to describe the code surrounding a model. Frameworks like LangChain, CrewAI, and AutoGen provide orchestration primitives. The concept exists but lacks a unified name or discipline.

### Early-Mid 2025: Context Engineering

Andrej Karpathy and others popularize "context engineering" as the practice of dynamically constructing the right information for model calls. The focus is on what reaches the model: RAG, memory, session history, structured state. Manus publishes "Context Engineering for AI Agents" documenting lessons from five framework rebuilds.

### Late 2025: Convergence on Harness Terminology

Multiple teams independently arrive at the realization that the infrastructure around the agent matters more than the agent itself. Anthropic publishes "Effective Harnesses for Long-Running Agents," introducing the term "harness" for the structured framework enabling agents to work across multiple context windows.

### Early 2026: The Term Crystallizes

**Mitchell Hashimoto** (creator of Terraform and Ghostty) uses the term "harness engineering" to describe the systematic process of building mechanisms that prevent repeated agent failures. His formulation spreads in the developer community.

**February 2026:** OpenAI publishes "Harness engineering: leveraging Codex in an agent-first world," documenting how a small team shipped ~1M lines of production code with zero human-written code. **Ryan Lopopolo** (OpenAI Codex team lead) states: "Agents aren't hard; the harness is hard." The OpenAI post establishes harness engineering as a named discipline with concrete principles.

**March 2026:** Martin Fowler's team publishes "Harness engineering for coding agent users," providing the `Agent = Model + Harness` equation and the guides/sensors framework. This gives the discipline its structural vocabulary.

**March-April 2026:** The term proliferates. LangChain publishes "The Anatomy of an Agent Harness." Phil Schmid (Hugging Face) publishes "The Importance of Agent Harness in 2026." Multiple conference tracks (including AI Engineer Europe 2026) organize around the concept. The community begins distinguishing harness engineering from context engineering and prompt engineering as a related but distinct discipline.

---

## Sources

### Primary Sources (Foundational)

1. **OpenAI** -- "Harness engineering: leveraging Codex in an agent-first world" (February 2026)
   https://openai.com/index/harness-engineering/

2. **Anthropic** -- "Effective harnesses for long-running agents" (Late 2025)
   https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents

3. **Manus** -- "Context Engineering for AI Agents: Lessons from Building Manus" (2025)
   https://manus.im/blog/Context-Engineering-for-AI-Agents-Lessons-from-Building-Manus

4. **Vercel** -- "We removed 80% of our agent's tools" (2025)
   https://vercel.com/blog/we-removed-80-percent-of-our-agents-tools

5. **Richard Sutton** -- "The Bitter Lesson" (2019)
   http://www.incompleteideas.net/IncIdeas/BitterLesson.html

6. **Martin Fowler / Thoughtworks** -- "Harness engineering for coding agent users" (March 2026)
   https://martinfowler.com/articles/exploring-gen-ai/harness-engineering.html

### Secondary Sources (Definition and Analysis)

7. **Phil Schmid (Hugging Face)** -- "The importance of Agent Harness in 2026"
   https://www.philschmid.de/agent-harness-2026

8. **HumanLayer** -- "Skill Issue: Harness Engineering for Coding Agents"
   https://www.humanlayer.dev/blog/skill-issue-harness-engineering-for-coding-agents

9. **Cobus Greyling** -- "The Rise of AI Harness Engineering" (March 2026)
   https://cobusgreyling.medium.com/the-rise-of-ai-harness-engineering-5f5220de393e

10. **Louis Bouchard** -- "Harness Engineering: The Missing Layer Behind AI Agents"
    https://www.louisbouchard.ai/harness-engineering/

11. **LangChain** -- "The Anatomy of an Agent Harness"
    https://blog.langchain.com/the-anatomy-of-an-agent-harness/

12. **Epsilla** -- "The Third Evolution: Why Harness Engineering Replaced Prompting in 2026"
    https://www.epsilla.com/blogs/harness-engineering-evolution-prompt-context-autonomous-agents

13. **Parallel Web Systems** -- "What is an agent harness in the context of large-language models?"
    https://parallel.ai/articles/what-is-an-agent-harness

14. **InfoQ** -- "OpenAI Introduces Harness Engineering: Codex Agents Power Large-Scale Software Development" (February 2026)
    https://www.infoq.com/news/2026/02/openai-harness-engineering-codex/
