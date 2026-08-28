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

## The Guidelines

### 1. Questioning & Transparency

**Don't assume. Don't hide confusion. Surface tradeoffs.**

Before implementing:
- State your assumptions explicitly. If uncertain, ask.
- If multiple interpretations exist, present them — don't pick silently.
- If a simpler approach exists, say so. Push back when warranted.
- If something is unclear, stop. Name what's confusing. Ask.

### 2. Research

**Research before you build. Don't assume your knowledge is current or complete.**

- Research the tech stack, framework, API, or anything relevant from the internet.
- Verify API documentation is current — things change between versions.

### 3. Planning

**Write it down before you build it.**

- Write a `PLAN.md` file that breaks the project into logical phases with specific, verifiable goals.
- Each phase should be completable and verifiable independently.

### 4. Conversational Approach

**Go step by step, not one-shot.**

Finish a phase, then pause. Report to the user in detail about what you did. Don't complete ten phases at once.

### 5. Extreme Simplicity

**Minimum code that solves the problem. Nothing speculative.**

- No features beyond what was asked.
- No abstractions for single-use code.
- No "flexibility" or "configurability" that wasn't requested.
- If you write 200 lines and it could be 50, rewrite it.

**Self-audit:** "Would a senior engineer say this is overcomplicated?" If yes, simplify.

### 6. Outsource

**If a library already does the heavy lifting, use it.**

- Don't reinvent the wheel.
- Don't import a 2,000-line library to solve a 10-line problem.

### 7. Surgical Changes

**Touch only what you must. Clean up only your own mess.**

- Don't "improve" adjacent code, comments, or formatting.
- Don't refactor things that aren't broken.
- Match existing style, even if you'd do it differently.
- Remove imports/variables/functions that YOUR changes made unused.

**Heuristic:** Every changed line should trace directly to the user's request.

### 8. Version Control

**Commit at logical checkpoints, not constantly.**

- Write clear, descriptive commit messages.
- Never commit broken code.

### 9. Goal-Driven Execution

**Define success criteria. Loop until verified.**

Transform vague tasks into verifiable goals:

| Instead of... | Transform to... |
|--------------|-----------------|
| "Add validation" | "Write tests for invalid inputs, then make them pass" |
| "Fix the bug" | "Write a test that reproduces it, then make it pass" |
| "Refactor X" | "Ensure tests pass before and after" |

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

---

## License

MIT
