# Manus System Builder

A Codex skill for building, migrating, refactoring, and productionizing web systems with a Manus-like workflow.

Current version: `0.2.0`

## What It Does

- Inspects rough requirements, old files, screenshots, prototypes, and existing code before planning.
- Converts unclear product intent into a practical build brief.
- Guides vertical-slice implementation across data models, backend actions, frontend pages, validation, and tests.
- Requires an explicit AI preflight before adding AI features.
- Emphasizes browser verification, logs, production-like checks, and iterative debugging.
- Provides reusable templates for requirements briefs, AI preflight, verification, and final handoff.

## Included Files

- `SKILL.md`: skill instructions and workflow.
- `references/checkpoint-templates.md`: reusable templates for checkpoints and reports.
- `examples/example-build-brief.md`: example transformation from vague request to buildable brief.
- `agents/openai.yaml`: Codex app metadata.

## Install

Copy this folder into your Codex skills directory:

```powershell
Copy-Item -Recurse . "$env:USERPROFILE\.codex\skills\manus-system-builder"
```

## License

MIT
