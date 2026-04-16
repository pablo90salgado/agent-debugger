---
name: agent-debugger
description: |
  Debugs errors and traces failures in AI agents and their tools. Use this skill when the user says: "the agent is failing", "tool call not working", "error in the pipeline", "debug this", "why is the agent doing X instead of Y", "trace the execution", "agent is stuck", "infinite loop", "model response won't parse", "context overflow". Identifies context errors, infinite loops, malformed tool calls, response parsing issues and subagent conflicts.
  ---

  # Agent Debugger

  Skill for diagnosing and resolving failures in AI agents, tool calls and pipelines.

  ## When to use this skill

  - The agent enters a loop and never finishes
  - A tool call fails silently or returns an unexpected result
  - The agent does something different from what was requested
  - There is a parsing error in the model response
  - The context fills up and the agent loses information
  - Two subagents conflict or overwrite each other

  ## Patterns and solutions

  **Infinite loop** — add an explicit stop condition, limit iterations
  **Malformed tool call** — validate schema before executing, add examples in the prompt
  **Context overflow** — summarize history every N steps, truncate tool outputs to the minimum needed
  **Parsing error** — use structured outputs if supported, add validation with retry logic
  **Prompt drift** — re-inject the original objective every N steps as a system reminder
  **Silent subagent conflict** — assign exclusive resources to each subagent, implement locks

  ## Verification checklist

  - [ ] Agent completes the task without loops
  - [ ] All tool calls match the expected schema
  - [ ] Context stays below 80% of the limit
  - [ ] Model responses parse correctly
  - [ ] Behavior is consistent across runs
  - [ ] Subagents do not overwrite each other

  ## Compatibility

  Claude Code, Cursor, Windsurf, Cline, Roo and any agent compatible with the Agent Skills standard.
