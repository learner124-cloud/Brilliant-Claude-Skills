# ⚡ Ultimate CLAUDE.md for Claude Code

> **The battle-tested, anti-hallucination, and anti-overengineering configuration for Anthropic's Claude Code.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## 🎯 The Problem

By default, AI coding agents love to:
- ❌ **One-shot entire codebases** and produce broken architecture.
- ❌ **Overcomplicate simple tasks** with unnecessary abstractions and libraries.
- ❌ **Touch unrelated code**, breaking working features silently.
- ❌ **Assume and guess** instead of asking clarifying questions.

## 💡 The Solution

This `CLAUDE.md` enforces a **high-accuracy, surgical, and conversational workflow**:

1. **Mandatory Planning & Verification:** Prevents silent failures by creating clear `PLAN.md` phases and low-level specifications.
2. **Conversational Guardrails:** Forces Claude to stop, ask clarifying questions, and clarify ambiguity *before* writing code.
3. **Extreme Simplicity:** Rejects bloat, single-use abstractions, and speculative error handling.
4. **Surgical Diffs:** Modifies only the lines needed to solve the task.

---

## 🚀 Quick Start

### Option 1: Direct Copy
Copy [`CLAUDE.md`](./CLAUDE.md) directly into your project's root directory
