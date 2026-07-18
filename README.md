# Project & Hobby Planning Team

A detailed AI planning team for **hobbies** and **physical build projects**. It always begins by
asking *"Is this a hobby or a project?"*, activates the specialists that apply, and produces highly
detailed, practical deliverables — measurements, design, functionality, cost, risk, time, materials,
tools, build sequence, sketches, interactive 3D models, testing, and documentation.

## How it runs

This repo is the team's **knowledge base**. The team itself runs as a Sonnet-powered agent inside
the **Personal_App** dashboard (team id `hobby_project`). The backend reads these files at runtime:
the Coordinator drives the conversation, and each specialist is invoked as its own Sonnet call using
its `agents/<specialist>.md` prompt plus the shared `DELIVERABLE_STANDARD.md`.

The backend finds this repo via `HOBBY_TEAM_DIR` (defaults to `~/Project-hobby-team`).

## Layout

```
HOBBY_PROJECT_TEAM_SPEC.md   Full master specification
START_HERE.md                Orientation
TEAM_WORKFLOW.md             How the Coordinator drives the team + conflict resolution
DELIVERABLE_STANDARD.md      Detail standard prepended to every specialist
DEFINITION_OF_DONE.md        System validation checklist
modes/                       hobby-mode.md, project-mode.md (activation rules + workflows)
agents/                      coordinator.md + 15 specialist prompts
templates/                   deliverable templates
```

## The 15 specialists (+ Coordinator)

Measurement · Designer · Functionality · Cost · Risk · Time · Sketch · 3D Model · Materials ·
Tools & Skills · Build Sequence · Research & Compatibility · Testing & Verification · Documentation.

## Central principle

> Every specialist owns one category of truth; the Coordinator ensures all categories agree.

## Roadmap

The chat-driven team (this repo + dashboard wiring) is Stage 3–4 of the master spec. The full
localhost workspace app — structured data pages, SVG sketches, interactive 3D, and PDF export
(Stages 5–9) — is planned follow-on work. See `HOBBY_PROJECT_TEAM_SPEC.md`.
