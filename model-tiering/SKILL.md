---
name: model-tiering
description: Use this skill whenever a task is large/risky enough to be split across multiple subagents (e.g. plan → implement → test, or research → build → verify). It tells you which model tier to assign to each role to minimize token cost without sacrificing quality where it matters most. Triggers on phrases like "split this across agents", "use multiple models", "plan then implement", or any task expected to touch many files/require a multi-step agent pipeline.
version: 1.0.0
---

# Multi-agent model tiering

When a task is large enough to warrant splitting work across multiple subagents, assign model tiers by role instead of using one model for everything. Goal: minimize total token cost while keeping quality where mistakes are most expensive.

## Role → model mapping

- **Planning / architecture design** — use the strongest available model (Opus or Fable). Planning mistakes are the most expensive to recover from (they get baked into everything built on top), so spend the most capable model here.
- **Implementation** (mechanical, well-specified work once a plan exists) — use a cheaper model (Sonnet, or Haiku for very simple/repetitive edits like find-and-replace patterns across files).
- **Testing / verification** — use a cheaper model (Haiku or Sonnet). Verifying against a known spec/plan is a bounded, checklist-style task and doesn't need the top-tier model.

## How to apply

1. Before spawning agents for a large task, explicitly propose this plan/implement/test (or research/build/verify) split to the user and get buy-in on the model assignment, rather than defaulting to one model for the whole pipeline or spawning agents ad hoc.
2. Don't spawn a fresh exploratory agent to re-derive context you already gathered directly in the current conversation — that wastes tokens regardless of which model tier you'd assign it. Only spawn agents for genuinely separable work (independent implementation, independent testing) where the context transfer is cheap relative to the work.
3. This applies across any project or codebase — it's a general operating preference, not tied to one repo.
