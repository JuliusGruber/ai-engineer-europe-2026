# Context Engineering for Coding Agents: A Definition from Primary Sources

This document synthesizes a definition of context engineering as it applies to AI coding agents, drawn from its foundational sources. Every claim is traceable to the sources listed at the end.

---

## What Context Engineering Is

Context engineering is the discipline of designing and building dynamic systems that provide the right information and tools, in the right format, at the right time, to give an LLM everything it needs to accomplish a task.

The foundational insight:

> **Intelligence is not the bottleneck. Context is.**

A coding agent's performance depends less on the underlying model's raw capability and more on what information it has access to when it reasons and acts. The same model that fails at a task with a bare prompt can succeed when given the right codebase context, documentation, tool access, and structured guidance.

Phil Schmid (Hugging Face) provides the most widely cited formal definition:

> "Context Engineering is the discipline of designing and building dynamic systems that provides the right information and tools, in the right format, at the right time, to give a LLM everything it needs to accomplish a task."

LangChain's Harrison Chase distills the core challenge:

> "Building dynamic systems to provide the right information and tools in the right format such that the LLM can plausibly accomplish the task."

Andrej Karpathy, whose endorsement crystallized the term in June 2025, captures why it superseded "prompt engineering":

> "Context engineering is the delicate art and science of filling the context window with just the right information for the next step."

For coding agents specifically, Martin Fowler's team defines it as "curating what the model sees so that you get a better result" -- a seemingly simple statement that, in practice, encompasses a rapidly expanding landscape of configuration options, protocols, and runtime techniques.

---

## Why Context Engineering Matters for Coding Agents

Coding agents operate in uniquely context-hungry environments. A typical agentic coding task requires dozens of tool calls, each generating context that accumulates across the session. Manus reports that a typical agent task requires roughly 50 tool calls. Spotify found that their background coding agent (Honk) needed careful context engineering to produce reliable, mergeable pull requests across thousands of repositories.

The core problem: **coding agents need context that no model was trained on.** Every codebase has unique architectural decisions, naming conventions, dependency patterns, test frameworks, deployment constraints, and team norms. Claude, GPT, or Gemini have no way to know these unless they are explicitly provided. As Anthropic states: "Every organization has unique workflows, standards, and knowledge systems, and Claude does not inherently know any of these."

Context engineering for coding agents is therefore not about making the model "smarter." It is about giving a capable model the specific information it needs to produce code that is correct, consistent with the codebase, and mergeable on first review.

---

## Core Principles

The following principles emerge from multiple independent sources. They represent the practitioner consensus as of early 2026.

### 1. Context Is a Finite Resource with Diminishing Returns

Anthropic's guide introduces the concept of a "finite attention budget." Like humans with limited working memory, LLMs have constrained attention that degrades with excess tokens -- a phenomenon Drew Breunig terms "context rot." Just because a model has a million-token context window does not mean you should fill it. Dex Horthy's analysis of 100,000 developer sessions identified a "dumb zone" in the middle 40-60% of large context windows where model recall degrades and reasoning falters.

Anthropic's formulation: find the smallest possible set of high-signal tokens that maximizes desired outcomes. Not the shortest prompt -- the most signal-dense context.

### 2. System, Not String

Every major source agrees: context is not a static prompt template. It is the output of a dynamic system that assembles information from multiple sources at runtime. Phil Schmid emphasizes that context emerges from pre-processing systems, not from handwritten templates. LangChain frames this as: context aggregates from developers, users, prior interactions, tool calls, and external data sources, with assembly logic that adapts as pieces arrive.

For coding agents, this means the agent's context is constructed from CLAUDE.md files, skill definitions, MCP server responses, grep results, file reads, test output, git history, and user instructions -- all dynamically composed for each step.

### 3. Right Information, Right Format, Right Time

Anthropic describes three loading strategies: **upfront** (naively dropped into context, like CLAUDE.md files), **just-in-time** (retrieved via tools when the agent determines it needs them), and **demand-driven** (the agent itself discovers what it needs through exploration). The most effective coding agents use a hybrid: some information is always present, more is loaded on demand, and the agent can autonomously explore when neither is sufficient.

Martin Fowler's team categorizes context mechanisms by who decides when to load them: the agent software (path-triggered rules), the LLM itself (skill selection), or the human (slash commands, explicit instructions).

### 4. Less Is More

Vercel removed 80% of their agent's tools and went from 80% to 100% accuracy, 3.5x faster execution, and 37% fewer tokens. Manus rebuilt their framework five times; the biggest gains came from removing features. Drew Breunig documents four patterns of context failure -- poisoning, distraction, confusion, and clash -- all caused by excess or conflicting context.

For coding agents, the implication is clear: a carefully curated set of tools, instructions, and reference material outperforms a comprehensive dump of everything the agent might conceivably need.

### 5. Garbage In, Garbage Out

LangChain states this bluntly: "Garbage In, Garbage Out" applies to context engineering as much as to any data system. The quality of the agent's output is bounded by the quality of its input. Phil Schmid's corollary: summaries exceed raw data dumps. Format and presentation matter -- a well-structured code example teaches the model more than a wall of documentation.

### 6. The Codebase Is the Most Powerful Context

Martin Fowler's team observes that "an AI-friendly codebase" is the most powerful context engineering tool available. Well-structured code with clear naming, consistent patterns, and good test coverage provides implicit context that no amount of documentation can replace. Spotify found the same: Claude Code performs best with prompts that describe the end state and leave room for the agent to explore the codebase and figure out the implementation.

### 7. Start Simple, Measure, Add Complexity Only on Failure

Anthropic recommends starting with minimal prompts using the best available model, then adding instructions based on observed failures. Phil Schmid's framework begins with the strategic selection principle: provide only relevant knowledge and capabilities. Martin Fowler warns against overengineering configurations, noting the risk of inadvertent instruction conflicts in inherited setups. Supabase's Pedro Rodrigues demonstrates that "poorly designed or untested Skills can have little impact or even degrade performance."

An ETH Zurich study (2026) testing 138 real-world Python tasks found that LLM-generated context files actually *reduced* task success by ~3% and increased costs by over 20%, while human-written files provided only a 4% increase in success. The takeaway: context engineering must be measured, not assumed. Adding context without evaluation can make agents worse.

---

## Key Mechanisms and Techniques

Synthesized from all sources, context engineering for coding agents operates through four strategy categories (LangChain's framework) and a set of specific mechanisms.

### Write: Saving Context Outside the Window

Techniques for persisting information beyond the current context window so it can be retrieved later.

- **Scratchpads and progress files** -- Agents write notes to files (claude-progress.txt, todo.md) during long tasks, creating durable memory that survives context resets. Anthropic's multi-agent researcher saves plans to persist context.
- **Long-term memory** -- Information synthesized across sessions. Claude Code's memory system stores user preferences, project conventions, and feedback across conversations. Cursor, Windsurf, and ChatGPT all implement variants.
- **Git commit history** -- Structured, machine-readable logs of what changed and why. Functions as an automatic context persistence layer.

### Select: Pulling the Right Information In

Techniques for dynamically loading relevant information into the context window when needed.

- **Tool-based retrieval** -- Agents use grep, glob, file read, and code search tools to find relevant code on demand. Claude Code's hybrid model: CLAUDE.md is loaded upfront; everything else is retrieved just-in-time.
- **Skill activation** -- Skills are lazy-loaded context packages with a three-level progressive disclosure architecture: (1) metadata layer -- only YAML frontmatter loads at startup (~80-200 tokens per skill); (2) primary instructions -- the SKILL.md body loads when the model determines relevance (275-8,000 tokens); (3) supporting files -- additional references load only during execution. Anthropic reports this approach recovers roughly 15,000 tokens per session compared to always-on loading.
- **MCP server queries** -- Model Context Protocol servers provide structured access to external data sources through a standardized interface. Anthropic's code-execution approach to MCP presents servers as code APIs rather than tool definitions, allowing agents to discover tools dynamically and filter data before it reaches the model. This reduced token usage in one example from 150,000 tokens to 2,000 -- a 98.7% reduction.
- **Knowledge retrieval in code agents** -- Windsurf uses AST parsing, embedding search, grep/file search, knowledge graphs, and re-ranking. Production code retrieval is multi-technique, not single-strategy.
- **Tool selection via RAG** -- Applying retrieval-augmented generation to tool descriptions themselves. Recent papers show a 3-fold improvement in accuracy when agents select from large tool sets this way.

### Compress: Retaining Only Essential Tokens

Techniques for reducing context size while preserving critical information.

- **Context summarization** -- Claude Code uses "auto-compact" after exceeding 95% of the context window, producing compressed summaries that preserve architectural decisions and unresolved bugs while dropping content. Strategies include recursive, hierarchical, and boundary-targeted summarization.
- **Context trimming** -- Hard-coded heuristics removing older messages, or trained pruning models that identify dispensable tokens. Manus's "attention recitation" continuously rewrites task summaries to keep goals in recent context.
- **Tool result clearing** -- Lightweight compaction that removes verbose tool outputs after they've been processed, keeping only the conclusions.

### Isolate: Splitting Context Across Boundaries

Techniques for preventing context accumulation by distributing work across separate windows.

- **Sub-agent architectures** -- Specialized sub-agents handle focused tasks with clean context windows, returning condensed summaries (1,000-2,000 tokens) to parent agents. Anthropic reports this can use up to 15x more tokens than chat, but dramatically improves reliability on complex tasks.
- **Environment sandboxing** -- Running tool outputs in isolated environments so token-heavy artifacts (test output, build logs, images) don't pollute the LLM's context.
- **State schema management** -- Storing context in structured state fields and exposing only necessary information to the LLM at each step, rather than keeping everything in the conversation history.

---

## The Context Engineering Stack for Coding Agents

As of early 2026, a standard set of context delivery mechanisms has converged across coding agents.

### CLAUDE.md / AGENTS.md / .cursorrules

Repository-level markdown files that encode project-specific guidance for coding agents. CLAUDE.md is Claude Code's convention; AGENTS.md has emerged as the tool-agnostic open standard, now stewarded by the Agentic AI Foundation under the Linux Foundation and adopted by 20,000+ repositories. These files typically contain build commands, test commands, architectural rules, coding conventions, and constraints ("never commit secrets").

Martin Fowler distinguishes between **instructions** (prompts directing agents to perform specific tasks) and **guidance** (general conventions agents should follow across all work). Both live in these files.

### Agent Skills

Skills are the newest and most significant context engineering mechanism. Released as an open standard by Anthropic in December 2025, the format was adopted by OpenAI, Google, GitHub, and Cursor within weeks. A skill is a markdown file with YAML frontmatter, organized in a folder that may include reference materials and executable scripts.

Skills implement **progressive disclosure**: the platform loads only metadata at startup, the model activates relevant skills on demand, and supporting materials load only during execution. This keeps the always-on context budget low while making extensive domain knowledge available when needed.

Pedro Rodrigues (Supabase) demonstrates that "Skills don't replace MCP -- they amplify it," and that their effectiveness must be measured through evals, not assumed.

### Model Context Protocol (MCP)

MCP is Anthropic's open standard (announced November 2024, donated to the Agentic AI Foundation December 2025) for connecting AI agents to external data sources and tools through a standardized interface. As of early 2026, the official registry has over 6,400 MCP servers.

MCP is a context engineering mechanism because it provides the standardized plumbing through which agents access structured external context: database schemas, API documentation, live system state, and more. It enables agents to load tools on demand, filter data before it reaches the model, and execute complex logic in a single step.

### Rules and Path-Based Configuration

Rules are scoped guidance that activates based on file paths or patterns. For example, a rule might apply only to TypeScript files, or only to files in a test directory. This implements the "right time" principle: guidance loads only when the agent is working in a context where it applies.

### Hooks and Lifecycle Events

Deterministic scripts that execute at specific points in the agent's lifecycle (before/after tool calls, on session start, etc.). Hooks bridge the gap between probabilistic LLM behavior and deterministic requirements -- they are context engineering mechanisms that operate outside the model's reasoning.

---

## Context Failure Modes

Drew Breunig's taxonomy of how long contexts fail has become canonical in the field. Understanding these failure modes is essential for effective context engineering.

### Context Poisoning
A hallucination or error enters the context and is repeatedly referenced by subsequent reasoning steps, compounding the error.

### Context Distraction
The context grows so long that the model over-focuses on the context window contents, neglecting what it learned during training. The model becomes less capable, not more, with additional context.

### Context Confusion
Superfluous information in the context is incorporated into the model's reasoning, generating low-quality responses that draw on irrelevant material.

### Context Clash
New information and tools added to the context conflict with other information or instructions already present. The model must resolve contradictions, often poorly.

Breunig's six remediation tactics include Tool Loadout (selecting a subset of tools per step, since beyond ~20 tools some models become confused), Context Quarantine, Context Pruning, Context Summarization, and Context Offloading.

---

## Relationship to Adjacent Concepts

### Context Engineering vs. Prompt Engineering

Prompt engineering focuses on crafting a single instruction to a model: word choice, formatting, few-shot examples, chain-of-thought elicitation. Tobi Lutke's original framing captures the distinction: "prompt engineering" suggests typing clever phrases into a chatbot, while context engineering describes "the art of providing all the context for the task to be plausibly solvable by the LLM."

Simon Willison argues the term shift is significant because "prompt engineering suffers from a thing where many people's inferred definition is that it's a laughably pretentious term for typing things into a chatbot." Context engineering has an inferred definition much closer to the intended meaning.

LangChain positions prompt engineering as "a subset of context engineering." Prompts are one component of context; context engineering encompasses everything else: retrieved documents, tool definitions, memory, state, structured output specifications, and the dynamic systems that assemble them.

### Context Engineering vs. Harness Engineering

Harness engineering (a term that crystallized in early 2026 via OpenAI and Mitchell Hashimoto) addresses the full operational infrastructure around an AI agent: execution environments, sandboxing, verification loops, orchestration, safety, and state management.

The distinction, as Louis Bouchard articulates it:

> "Prompt engineering is what to ask. Context engineering is what to send the model so that it can answer confidently. Harness engineering is how the whole thing operates."

HumanLayer positions harness engineering as "a specialized subset of context engineering, focusing on how configuration points manage context windows in coding agents." Martin Fowler frames it the other way: "engineering a user harness is a specific form of context engineering." The boundaries are still settling.

In practice, context engineering and harness engineering are deeply intertwined for coding agents. The harness provides the execution infrastructure; context engineering determines what information flows through that infrastructure to the model. A well-designed harness enables better context delivery. A poorly designed one constrains it.

### Context Engineering vs. RAG

Retrieval-Augmented Generation is one technique within context engineering, not a synonym for it. RAG addresses the "select" dimension -- pulling relevant documents into the context window. Context engineering also encompasses writing (persistence), compression, isolation, tool design, memory management, and the dynamic orchestration of all these components.

As Zep puts it: "RAG is one flavor of context engineering."

---

## Philosophies and Points of Disagreement

### Upfront vs. Demand-Driven Context Loading

**The upfront position** (traditional RAG, early coding agents): retrieve all potentially relevant context before the model reasons. This is fast and predictable but wasteful -- it fills the context window with information that may not be needed and risks context distraction.

**The demand-driven position** (Anthropic, Claude Code, newer agents): let the agent discover and retrieve context as it needs it. Skills load on demand. The agent uses grep and file read to explore the codebase. This is more efficient but slower and relies on the model's judgment about what to retrieve.

**The hybrid resolution** (Anthropic's explicit recommendation): drop critical context upfront (CLAUDE.md, key constraints) while enabling just-in-time and autonomous retrieval for everything else. "Claude Code employs a hybrid model: CLAUDE.md files are naively dropped into context up front, while primitives like glob and grep allow it to navigate its environment and retrieve files just-in-time."

### How Much Context Is Too Much?

**The maximalist position**: fill the context window with everything available. Models are getting better at handling long contexts, and more information is always better than less.

**The minimalist position** (Anthropic, Drew Breunig, Vercel, Dex Horthy): context windows have diminishing returns. Breunig's four failure modes demonstrate that more context actively harms output quality past a threshold. Dex Horthy's analysis shows degradation starting at 40% of window capacity.

**The consensus**: most practitioners have converged on minimalism. Anthropic's principle of "high-signal minimalism" -- the smallest possible set of high-signal tokens -- reflects the dominant view. But the threshold varies by model, task complexity, and context quality.

### Skills vs. MCP: Complementary or Competing?

Skills provide structured domain knowledge and guidance. MCP provides structured access to external data and tools. Pedro Rodrigues (Supabase) argues they are complementary: "Skills don't replace MCP -- they amplify it." But the practical boundary is unclear. A skill can include instructions for how to use an MCP server. An MCP server can return context that makes a skill unnecessary.

The emerging view is that skills handle the "what to do and how" (domain expertise, patterns, constraints), while MCP handles the "access to what" (data sources, tools, live systems). The skill is the playbook; MCP is the toolbox.

### Is Context Engineering Just Good Software Engineering?

A persistent critique, voiced on Hacker News: "Harness Engineering is a marketing term. In reality it's just the practice of leveraging what has always defined a good stable codebase: good docs and high test coverage." The same criticism applies to context engineering.

Addy Osmani addresses this directly: much of current AI work lacks the rigor expected from engineering disciplines, with too much trial-and-error, not enough measurement, and insufficient systematic methodology. The term "engineering" is aspirational -- it signals the intent to bring discipline, measurement, and reproducibility to what has been ad hoc practice.

Martin Fowler warns of the "illusion of control": "There are no unit tests for context engineering." Despite the engineering framing, LLM execution remains probabilistic. Certainty is impossible; probability-based thinking is required.

---

## Timeline: How the Discipline Emerged

### Prehistory: RAG and Prompt Engineering (2023-2024)

Retrieval-Augmented Generation becomes mainstream as a technique for providing LLMs with external knowledge. The term "prompt engineering" dominates discourse. The practices that will later be called context engineering exist but lack a unified name. Anthropic announces Model Context Protocol (November 2024).

### Early 2025: The Practitioners Build Without the Name

Dex Horthy publishes the 12-Factor Agents manifesto (April 2025), using the phrase "context engineering" in the repo: "LLMs are stateless functions. Everything is context engineering." The concept exists in practice across teams building coding agents, but no one has named and popularized it yet.

### June 2025: The Term Crystallizes

**June 19:** Tobi Lutke (Shopify CEO) posts on X: "I really like the term 'context engineering' over prompt engineering. It describes the core skill better: the art of providing all the context for the task to be plausibly solvable by the LLM."

**June 22-26:** Drew Breunig publishes "How Long Contexts Fail" and "How to Fix Your Context," providing the field's first failure taxonomy.

**June 23:** Lance Martin (LangChain) publishes "Context Engineering for Agents" and Harrison Chase publishes "The Rise of Context Engineering."

**June 25:** Andrej Karpathy posts on X: "+1 for 'context engineering' over 'prompt engineering'... context engineering is the delicate art and science of filling the context window with just the right information for the next step."

**June 27:** Simon Willison writes: "I think 'context engineering' is going to stick." Techmeme picks it up.

**June 30:** Phil Schmid (Hugging Face) publishes "The New Skill in AI is Not Prompting, It's Context Engineering," which hits 915 points on Hacker News -- the breakout moment that brings the term to mainstream developer awareness.

### Mid-2025: Frameworks and Production Case Studies

**July 2:** LangChain publishes the detailed "Context Engineering for Agents" post introducing the write/select/compress/isolate framework.

**July 13:** Addy Osmani publishes "Context Engineering: Bringing Engineering Discipline to Prompts" (later republished by O'Reilly in three parts).

**July 18:** Manus publishes "Context Engineering for AI Agents: Lessons from Building Manus," documenting five framework rebuilds and establishing the file system as a context engineering primitive.

### Late 2025: Institutionalization

**September 29:** Anthropic publishes "Effective context engineering for AI agents," the field's most comprehensive technical guide. Introduces finite attention budget, context rot, hybrid loading strategies, and sub-agent isolation.

**October 2025:** First academic papers appear on arXiv: "Agentic Context Engineering" (2510.04618) and "Context Engineering for AI Agents in Open-Source Software" (2510.21413).

**November 2025:** Spotify publishes the Honk series documenting context engineering for background coding agents at production scale. MIT Technology Review publishes "From vibe coding to context engineering: 2025 in software development."

**December 2025:** Anthropic releases Agent Skills as an open standard; adopted by OpenAI, Google, GitHub, and Cursor within weeks. Anthropic donates MCP to the Agentic AI Foundation. Gartner identifies context engineering as a top emerging technology skill for 2026.

### Early 2026: Maturation and Convergence

**February 2026:** Martin Fowler / Birgitta Boeckeler publishes "Context Engineering for Coding Agents," providing the field's structural vocabulary for coding agents (instructions vs. guidance, context interfaces, demand-driven loading). SWE-ContextBench (arXiv:2602.08316) introduces the first benchmark specifically for context reuse in coding agents.

**March-April 2026:** Academic papers proliferate. Multiple conference tracks organize around the concept. AI Engineer Europe 2026 has a dedicated "Context Engineering" track with 8 sessions covering skills, MCP, context graphs, hierarchical memory, and personalization.

---

## Sources

### Origin Sources (Term Crystallization)

1. **Tobi Lutke** -- X post endorsing "context engineering" (June 19, 2025)
   https://x.com/tobi/status/1935533422589399127

2. **Andrej Karpathy** -- X post defining context engineering (June 25, 2025)
   https://x.com/karpathy/status/1937902205765607626

3. **Simon Willison** -- "Context engineering" blog post (June 27, 2025)
   https://simonwillison.net/2025/jun/27/context-engineering/

### Primary Sources (Foundational)

4. **Phil Schmid (Hugging Face)** -- "The New Skill in AI is Not Prompting, It's Context Engineering" (June 30, 2025)
   https://www.philschmid.de/context-engineering

5. **Harrison Chase / LangChain** -- "The Rise of Context Engineering" (June 23, 2025)
   https://blog.langchain.com/the-rise-of-context-engineering/

6. **LangChain** -- "Context Engineering for Agents" (July 2, 2025)
   https://blog.langchain.com/context-engineering-for-agents/

7. **Lance Martin / LangChain** -- "Context Engineering for Agents" (June 23, 2025)
   https://rlancemartin.github.io/2025/06/23/context_engineering/

8. **Manus** -- "Context Engineering for AI Agents: Lessons from Building Manus" (July 18, 2025)
   https://manus.im/blog/Context-Engineering-for-AI-Agents-Lessons-from-Building-Manus

9. **Anthropic** -- "Effective context engineering for AI agents" (September 29, 2025)
   https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents

10. **Drew Breunig** -- "How Long Contexts Fail" (June 22, 2025)
    https://www.dbreunig.com/2025/06/22/how-contexts-fail-and-how-to-fix-them.html

11. **Drew Breunig** -- "How to Fix Your Context" (June 26, 2025)
    https://www.dbreunig.com/2025/06/26/how-to-fix-your-context.html

12. **Martin Fowler / Birgitta Boeckeler** -- "Context Engineering for Coding Agents" (February 5, 2026)
    https://martinfowler.com/articles/exploring-gen-ai/context-engineering-coding-agents.html

### Secondary Sources (Production and Analysis)

13. **Spotify** -- "Background Coding Agents: Context Engineering (Honk, Part 2)" (November 24, 2025)
    https://engineering.atspotify.com/2025/11/context-engineering-background-coding-agents-part-2

14. **Addy Osmani** -- "Context Engineering: Bringing Engineering Discipline to Prompts" (July 13, 2025)
    https://addyo.substack.com/p/context-engineering-bringing-engineering

15. **Dex Horthy / HumanLayer** -- 12-Factor Agents (April 2025)
    https://github.com/humanlayer/12-factor-agents

16. **Vercel** -- "We removed 80% of our agent's tools" (2025)
    https://vercel.com/blog/we-removed-80-percent-of-our-agents-tools

17. **MIT Technology Review** -- "From vibe coding to context engineering: 2025 in software development" (November 5, 2025)
    https://www.technologyreview.com/2025/11/05/1127477/from-vibe-coding-to-context-engineering-2025-in-software-development/
