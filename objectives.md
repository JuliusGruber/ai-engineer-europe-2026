# Conference Objectives

What I want to learn and take home from AI Engineer Europe 2026.

## Primary Goal

Improve how I use coding agents to produce code — by understanding and applying better context engineering and harness engineering.

## Context Engineering

- How to write, evaluate, and iterate on Agent Skills effectively
- How to make skills portable across tools (Claude Code, Cursor, Codex)
- Demand-driven context discovery: letting agents surface what context is missing instead of guessing what to curate
- How skills and MCP combine in production — what the benchmarks actually show
- Hierarchical memory and context management patterns (composable primitives for agent knowledge)
- How a context engine makes the difference between mergeable-on-first-pass and hours of wasted tokens

## Harness Engineering

- What a well-structured agent harness looks like (event sourcing, structured handoffs, parallel tool execution)
- How to manage state and debug long-running agents (traces as the primary debugging loop)
- Agent UX patterns: durable sessions, resumable streaming, interruption handling
- Where harness engineering and context engineering meet — how a good harness enables better context delivery

## Coding Agents in Practice

- Skills as extreme leverage (12K LoC to 200 LoC)
- How production teams (HuggingFace, incident.io, IKEA Digital, Linear) actually use coding agents at scale
- Evaluation pipelines for agentic coding workflows — how to know if improvements actually work
- The human side: when comprehension matters more than generation, and where judgment beats automation

## Real-World Validation

- Results on real code or it didn't happen — filter every talk through: does this work on a production codebase with history, tech debt, and scale?

## Meta

- What changes when inference hits 1000+ tok/s — how speed shifts iteration patterns and agent design
- How software engineering fundamentals (TDD, vertical slices) apply to agent workflows
