# Global Rules

## Core principles

1. **No hacks** – fix root causes, not symptoms. No "temporary" workarounds.
2. **No dead code** – remove unused code immediately. Every line must serve a purpose.
3. **Revert failed changes** – if a code change doesn't fix the problem, remove it completely before trying the next approach. Never leave dead or ineffective code behind.
4. **No assumptions** – ask if uncertain. Verify with tests. Facts over guesses.
5. **Research before guessing** – web search for solutions before guessing at fixes, especially for platform-specific issues. Facts over trial-and-error.
6. **Security first** – never expose API keys or secrets client-side. No security shortcuts.

## Required reading

Before writing code in a project, check for and read these files first if they exist:

- `CLAUDE.md`, `README.md` in the project root
- `docs/` directory for architecture, conventions, schema docs

## Git

1. **No autonomous commits** – never commit or push without explicit user instruction.
2. **No git reverts without permission** – never revert files using git checkout, git restore, or any git command without explicit user approval. Debug and fix issues instead.
