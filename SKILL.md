---
name: manus-system-builder
description: Build, migrate, refactor, or productionize a new web system with a Manus-like workflow. Use when the user provides rough requirements, old files, screenshots, prototypes, existing code, or a product idea and wants Codex to inspect materials, normalize requirements, plan architecture, implement modules, ask before integrating AI, verify in real browser or production-like environments, debug issues, and iterate with checkpoints.
---

# Manus System Builder

Use this skill to turn unclear product intent or legacy material into a working, verified system. The operating loop is: inspect first, preserve what matters, design the real system, implement vertical slices, verify with tools, then iterate from concrete feedback.

## Intake

Inspect available materials before proposing implementation:
- User requirements, notes, screenshots, URLs, old files, prototypes, or existing code
- Current feature list and workflows
- UI behavior that must be preserved
- Known bugs, missing features, or unwanted legacy pieces
- Data that must persist
- Auth, roles, permissions, deployment, and external service constraints

Produce a short inventory:
- Main modules
- Data entities
- User roles
- External services
- Existing AI/API usage
- Features to keep, remove, rebuild, or defer
- Risks and unknowns

Ask only necessary questions. If the answer can be discovered from files, browser inspection, logs, or existing behavior, inspect first.

## Requirements

Normalize the request into a buildable brief:
- System purpose and target users
- Core workflows
- Required modules and optional modules
- Data model and persistence needs
- Admin/user permission boundaries
- Import, export, backup, or audit needs
- Deployment target and runtime constraints
- Acceptance criteria for "done"

Keep the brief practical. It should guide implementation, not become a long product document unless the user asks for one.

## AI Preflight

Before adding AI capability, explicitly ask the user:
- Whether AI should be built into the system
- Which AI provider, model, or platform should be used
- Which functions need AI and what business goal each function serves
- Whether AI output should be editable before saving
- Whether AI output should be stored, logged, reviewed, or discarded
- Cost, frequency, model, provider, permission, privacy, or compliance limits
- Whether duplicate calls, retries, cancellation, streaming, and timeout behavior are required

Only design the AI layer after this is answered.

When AI is needed:
- Keep secrets and business context server-side
- Inject current site, product, user, or business configuration into prompts
- Add request guards such as loading states, idempotency, AbortController, or in-flight locks
- Handle empty, malformed, slow, or failed model responses
- Make generated content editable before committing it when appropriate
- Test critical AI workflows in the browser, not only by reading code

## Plan

Create and maintain a concrete checklist:
- Foundation and project scaffold
- Database schema and migrations
- Backend routes, services, or routers
- Auth and permissions
- Frontend routing, layout, and global styles
- Core modules
- Supporting modules
- AI features, if confirmed
- Tests and type checks
- Browser verification
- Deployment or production fixes
- Final polish and handoff

Save or note checkpoints after stable milestones: scaffold works, core modules compile, main workflows pass, AI works, production issues are resolved.

## Build

Implement by vertical slices. For each module:
- Define or update the data model
- Add backend CRUD or business actions
- Add frontend pages and components
- Add validation, loading, error, and empty states
- Add focused tests when behavior is important or risk is non-trivial
- Verify the actual user workflow in a browser when the UI is involved

Prefer existing project conventions and framework patterns. Add abstractions only when they reduce real complexity or match the codebase.

## Verify

Do not treat coding as complete until it is checked. Use the relevant mix of:
- Type check
- Lint
- Unit or integration tests
- Migration checks
- Browser smoke tests
- Real form submissions
- Network/request inspection
- Server logs and client console logs
- Preview or production environment checks when relevant

Report what was verified and what was not.

## Debug

When something works in development but fails elsewhere, compare environments:
- Browser differences
- Auth cookies and session state
- CORS preflight and custom headers
- CDN, proxy, buffering, and streaming behavior
- API response shape and parser expectations
- Database schema drift and legacy constraints
- Deployment environment variables
- Server logs and client console errors

Common fixes:
- DOM/runtime errors: validate invalid nested elements, Link usage, browser translation side effects, and add `translate="no"` or an ErrorBoundary only when appropriate.
- AI failures: verify request arrival, auth, CORS, transport mode, response parsing, timeout/cancellation, loading state, and duplicate-call prevention.
- Database errors: compare ORM schema with the live table, remove or migrate legacy NOT NULL columns, indexes, and constraints deliberately.
- Blocked OAuth testing: add a controlled system or test account flow when appropriate.

## Iterate

For each user feedback cycle:
1. Reproduce or inspect the issue.
2. Identify the root cause.
3. Patch the smallest correct area.
4. Run focused verification.
5. Update tests if the behavior is important.
6. Save or note a checkpoint.
7. Report the result clearly.

## Report

When handing work back, include:
- What was built or changed
- Which modules are complete
- Which checks were run
- Browser or production verification status
- Known risks or unverified areas
- Suggested next step
