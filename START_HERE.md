# Start Here — Hobby & Project Planning Team

This repository is the **knowledge base** for the Hobby & Project Planning Team. The team runs as
a Sonnet-powered agent inside the Personal_App dashboard (team id `hobby_project`). The agent reads
these files at runtime to act as the Coordinator and to run each specialist as its own Sonnet call.

## The one rule that always comes first

Every new hobby or project **must** begin by asking:

> Is this a hobby or a project?

Never assume the mode, even when it seems obvious.

## How the team is organized

- `HOBBY_PROJECT_TEAM_SPEC.md` — the full master specification.
- `TEAM_WORKFLOW.md` — how the Coordinator drives the team and resolves conflicts.
- `DELIVERABLE_STANDARD.md` — the detail every specialist deliverable must meet (prepended to every specialist prompt at runtime).
- `DEFINITION_OF_DONE.md` — validation checklist for the whole system.
- `modes/hobby-mode.md`, `modes/project-mode.md` — which specialists activate and in what order.
- `agents/coordinator.md` — the Coordinator's operating instructions.
- `agents/<specialist>.md` — each specialist's mission, responsibilities, deliverable, and hard rules.
- `templates/` — deliverable templates the specialists fill in.

## Central principle

> Every specialist owns one category of truth; the Coordinator ensures all categories agree.

## To work with the team

Open the Personal_App dashboard, select **Project & Hobby Team**, and describe what you want to
plan. The Coordinator will ask Hobby or Project first, activate the right specialists, and produce
detailed deliverables — never vague advice.
