# Example Build Brief

## User Request

"I need a project management system. It should record every stage, owner, and completion state. All future tasks should go through this system."

## Intake Inventory

- Source materials: short natural-language request
- Current app or prototype: none
- Must-preserve behavior: not applicable
- Known problems: unclear roles, stages, persistence, notifications, and reporting
- Data that must persist: projects, tasks, stages, owners, status, comments, attachments, history
- Roles and permissions: admin, project owner, task assignee, viewer
- External services: none confirmed
- AI/API usage: not confirmed; ask before adding
- Keep: core task/stage tracking
- Remove: none
- Rebuild: not applicable
- Defer: automation and integrations until core workflow works
- Risks and unknowns: database choice, auth model, reporting needs, deployment target

## Buildable Brief

- Purpose: centralize project tasks and stage tracking
- Target users: managers, department leads, task owners
- Core workflows: create project, add stages, assign owners, update status, review progress, export report
- Required modules: dashboard, projects, tasks, stages, users/roles, activity history
- Optional modules: comments, attachments, notifications, recurring tasks, calendar, analytics
- Data model: users, projects, stages, tasks, comments, activity_logs
- Permission boundaries: admin manages users; project owner manages project; assignee updates assigned tasks
- Import/export/audit needs: CSV export and activity log
- Deployment target: confirm before implementation
- Acceptance criteria: browser-tested create/update flow, persisted data, role checks, export works

## First Implementation Slice

1. Scaffold the app and persistence.
2. Add user/project/task/stage schema.
3. Build project list and project detail pages.
4. Add task creation and status update.
5. Add activity log for task changes.
6. Verify in browser with one complete project lifecycle.
