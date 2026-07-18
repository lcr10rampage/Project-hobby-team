# AI Hobby and Project Planning Team Specification

## Purpose

Build a detailed AI team that helps me plan hobbies and physical projects.

The system supports two operating modes:

1. Hobby Mode
2. Project Mode

Every time I begin something new, the system must first ask:

> Is this a hobby or a project?

The system must not assume which mode applies, even when the answer seems obvious.

After I answer, it activates the specialists that apply to that mode. Some specialists may
not be useful for every hobby or project — that is expected.

The team produces highly detailed, practical deliverables rather than general advice. Its
output is eventually organized inside a localhost browser application containing measurements,
designs, functionality plans, costs, timelines, risks, sketches, interactive 3D models,
materials, tools, build steps, decisions, and documentation. The localhost application becomes
the central workspace for each hobby or project.

---

## First Interaction Requirement

Every new hobby or project begins with:

> Is this a hobby or a project?  →  [Hobby] [Project]

After the user selects a mode, the system creates a new workspace using the appropriate workflow.

### Hobby Mode focuses on
Understanding the hobby · desired involvement · required gear and equipment · skills to learn ·
practice and progression · costs · time commitment · safety · storage · maintenance · seasonal
considerations · trips/events/experiences · optional physical setups or builds.

Examples: hunting, fishing, camping, backpacking, photography, music, model building, gardening,
car restoration, electronics, woodworking, painting, hiking, collecting.

### Project Mode focuses on
Requirements · measurements · constraints · design · functionality · materials · construction ·
cost · risk · time · tools · skills · build sequence · sketches · interactive 3D models · testing ·
maintenance · documentation.

Examples: cargo trailer camper, shed, workbench, furniture, vehicle modification, storage system,
electronics enclosure, workshop layout, home improvement, hunting blind, camping setup, garden
structure, custom equipment, restoration project.

---

## Core Team (Coordinator + 15 Specialists)

1. Project Coordinator
2. Measurement Specialist
3. Designer
4. Functionality Specialist
5. Cost Specialist
6. Risk Specialist
7. Time Specialist
8. Sketch Specialist
9. 3D Model Specialist
10. Materials Specialist
11. Tools and Skills Specialist
12. Build Sequence Specialist
13. Research and Compatibility Specialist
14. Testing and Verification Specialist
15. Documentation Specialist

Not every specialist runs on every request. The Coordinator decides which apply after the user
selects Hobby or Project, and records the reason when a specialist is deactivated.

Full per-specialist mission, responsibilities, deliverables, and rules live in `agents/*.md`.
Activation rules and workflows live in `modes/*.md`. The deliverable detail standard lives in
`DELIVERABLE_STANDARD.md`.

---

## Specialist Activation Rules (summary)

**Hobby Mode default:** Coordinator, Designer, Functionality, Cost, Risk, Time, Materials,
Tools & Skills, Research & Compatibility, Documentation.
**Hobby Mode optional** (activate when the hobby includes a physical setup, workspace, vehicle,
custom storage, equipment mounting, structure, build, detailed layout, custom electronics, or a
restoration): Measurement, Sketch, 3D Model, Build Sequence, Testing & Verification.

**Project Mode default:** all 15 specialists. The Coordinator may deactivate ones that clearly do
not apply, but records why.

---

## Deliverable Detail Standard (summary)

Every specialist deliverable is highly detailed and normally includes: title · specialist ·
revision · date · purpose · scope · inputs used · confirmed information · assumptions · unknowns ·
calculations · detailed analysis · recommendations · alternatives · tradeoffs · dependencies ·
risks · required decisions · verification method · handoff notes · sources/evidence · change history.

Vague output is rejected. "Use strong wood for the frame" is unacceptable; a specific, dimensioned,
assumption-labeled recommendation tied to verified inputs is required. See `DELIVERABLE_STANDARD.md`.

---

## Project Stages

**Project Mode:** CLASSIFICATION → REQUIREMENTS → MEASUREMENT → CONCEPT_DESIGN → FUNCTIONAL_REVIEW →
MATERIAL_SELECTION → VISUALIZATION → COST_REVIEW → RISK_REVIEW → FINAL_DESIGN → BUILD_PLANNING →
READY_TO_BUILD → BUILDING → TESTING → CORRECTIONS → COMPLETE.

**Hobby Mode:** CLASSIFICATION → GOAL_DEFINITION → RESEARCH → GEAR_PLANNING → SKILL_PLANNING →
COST_REVIEW → RISK_REVIEW → SCHEDULE_PLANNING → READY_TO_START → ACTIVE → REVIEW → EXPANSION.

Only the Coordinator changes the official stage.

---

## Localhost Browser Application

A local browser application is the central workspace for all hobbies and projects. It runs on
localhost and does not require cloud hosting for basic operation.

**Navigation:** Home · Projects and Hobbies · Workspace Overview · Requirements · Measurements ·
Design · Functionality · Materials · Cost · Timeline · Risks · Sketches · 3D Model · Build Steps ·
Tools and Skills · Compatibility · Testing · Decisions · Documents · Revisions · Settings.

Sections that do not apply are marked Not applicable / Not yet started / Optional / Waiting for
information — they are never silently hidden.

Per-workspace data structure (JSON + markdown, local):

```
projects/workspace-name/
  workspace.json  requirements.json  measurements.json  design.md  functionality.md
  materials.json  costs.json  timeline.json  risks.json  tools.json  compatibility.json
  build-steps.json  tests.json  decisions.json  status.json
  sketches/  models/  documents/  revisions/
```

---

## Recommended Technical Stack

React · TypeScript · Vite or Next.js · a component system · local SQLite or JSON storage ·
Markdown for long-form reports · SVG for technical sketches · Three.js / React Three Fiber for
3D · GLB/glTF model files · PDF and image export. The exact stack is selected after inspecting the
existing repository; do not introduce technologies that conflict with the existing foundation.

---

## Build Stages

1. Repository audit
2. System architecture
3. Essential team files (modes + core specialist files)
4. Workspace onboarding (always ask Hobby or Project first)
5. Localhost dashboard foundation (home, new-workspace flow, overview, nav, local persistence, status, activation, placeholder pages)
6. Structured data pages (requirements, measurements, costs, timeline, risks, materials, tools, build steps, decisions, testing, revisions)
7. Sketch system (SVG: dimensions, labels, multiple views, revisions, zoom/pan/export)
8. Interactive 3D system (Three.js / R3F: orbit, presets, layers, transparency, exploded, dimensions, annotations, GLB/glTF, screenshot) — begin with block models from measurements
9. Document generation (PDF plan, shopping list, build guide, risk report, timeline, test report, sketch package, model export)
10. Validation (see Definition of Done)

---

## Constraints

Do not build unnecessary complexity before the core workflow works. Do not require every specialist
for every workspace. Do not silently skip a specialist without recording why. Do not present
estimated measurements as confirmed. Do not present conceptual models as fabrication-ready. Do not
present cost estimates as current quotes unless verified. Do not hide risks. Do not let design,
measurement, model, and materials data drift apart. Do not overwrite approved revisions without
retaining history. Do not create vague specialist reports. Do not claim a project is complete
without testing. Do not require cloud hosting for basic use. Reuse existing repository standards
and components where practical. Build in small, working stages. Keep the user in control of
important decisions.

---

## Central Principle

> Every specialist owns one category of truth, while the Project Coordinator ensures that all
> categories agree.
