# Blueprint

> **Behavioral guidelines for coding agents. Follow the blueprint.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## The Problem

By default, AI coding agents love to:

- ❌ **One-shot entire codebases** and produce broken architecture.
- ❌ **Overcomplicate simple tasks** with unnecessary abstractions and libraries.
- ❌ **Touch unrelated code**, breaking working features silently.
- ❌ **Assume and guess** instead of asking clarifying questions.

## The Solution

Blueprint enforces a **high-accuracy, surgical, and conversational workflow**:

1. **Questioning & Transparency** — Forces agents to stop, ask clarifying questions, and clarify ambiguity *before* writing code.
2. **Research First** — Prevents hallucinated APIs and outdated documentation by requiring internet research.
3. **Mandatory Planning** — Creates clear `PLAN.md` phases and low-level specifications before implementation.
4. **Extreme Simplicity** — Rejects bloat, single-use abstractions, and speculative error handling.
5. **Surgical Changes** — Modifies only the lines needed to solve the task.
6. **Goal-Driven Execution** — Transforms vague tasks into verifiable success criteria.

---

## Quick Start

### Option 1: Claude Code (Recommended)

Install via the Claude Code plugin marketplace:

```
/plugin marketplace add learner124-cloud/Brilliant-Claude-Skills
/plugin install blueprint
```

Or manually copy `CLAUDE.md` into your project's root directory:

```bash
curl -o CLAUDE.md https://raw.githubusercontent.com/learner124-cloud/Brilliant-Claude-Skills/main/CLAUDE.md
```

### Option 2: Cursor

Copy `.cursor/rules/blueprint.mdc` into your project's `.cursor/rules/` directory:

```bash
mkdir -p .cursor/rules
curl -o .cursor/rules/blueprint.mdc https://raw.githubusercontent.com/learner124-cloud/Brilliant-Claude-Skills/main/.cursor/rules/blueprint.mdc
```

The rule is configured with `alwaysApply: true` — it activates automatically when you open the project in Cursor.

### Option 3: Other Tools

If your tool only supports a root instruction file, copy `CLAUDE.md` into your project root.

---

## How to Know It's Working

These guidelines are working if you see:

- ✅ **Fewer unnecessary changes in diffs** — Only requested changes appear.
- ✅ **Fewer rewrites due to overcomplication** — Code is simple the first time.
- ✅ **Clarifying questions come before implementation** — Not after mistakes.
- ✅ **Clean, minimal PRs** — No drive-by refactoring or "improvements."

---

## Customization

Blueprint is designed to be merged with project-specific instructions. Add your own sections:

```markdown
## Project-Specific Guidelines

- Use TypeScript strict mode
- All API endpoints must have tests
- Follow the existing error handling patterns in `src/utils/errors.ts`
```

---

## Tradeoff Note

These guidelines bias toward **caution over speed**. For trivial tasks (simple typo fixes, obvious one-liners), use judgment — not every change needs the full rigor.

The goal is reducing costly mistakes on non-trivial work, not slowing down simple tasks.
