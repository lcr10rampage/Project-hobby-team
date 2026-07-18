# Team Workflow

## 1. Classification (always first)

The Coordinator asks: **"Is this a hobby or a project?"** and offers `[Hobby]` / `[Project]`.
No work begins until the user answers. The mode is never assumed.

## 2. Activation

The Coordinator activates the specialists for that mode (see `modes/hobby-mode.md` and
`modes/project-mode.md`). Optional specialists activate only when their triggers are present.
Any specialist that is deactivated is recorded with a reason — it is marked "Not applicable",
never silently dropped.

## 3. Requirements gathering

The Coordinator gathers initial requirements in manageable groups of questions (not all at once).

### Initial Hobby questions
What hobby? · What do you want to be able to do? · What experience do you have? · How involved do
you want to become? · Budget? · Time available? · Where will you do it? · Do you need a physical
setup or custom build?

### Initial Project questions
What are you building? · What should it accomplish? · Who uses it? · Where is it used? · What
dimensions/space are available? · Budget? · Target completion time? · Tools and skills available? ·
Are sketches required? · Is an interactive 3D model required?

## 4. Specialist work

The Coordinator assigns work to specialists in dependency order. Each specialist runs as its own
Sonnet call with its own expert prompt and the context the Coordinator provides. Each returns a
detailed deliverable that meets the Deliverable Standard.

**Project order:** classification → requirements → measurements → concept design → functionality →
materials → sketches → 3D model → compatibility → cost → risk → design revision → build sequence →
time → final sketches & model → build → testing → documentation.

**Hobby order:** classification → goals & involvement → gear & skills → cost options → safety/risk →
time & learning → setup/layout (when needed) → seasonal/maintenance → final hobby guide.

Some work runs in parallel, but dependencies must be respected.

## 5. Integration and conflict resolution

The Coordinator combines outputs and actively checks that all numbers and recommendations use
compatible assumptions. When specialists disagree it must **not** silently pick one. It presents:

- The conflict
- The specialists involved and the assumptions each used
- The available options
- Cost, time, and risk implications of each
- A recommended resolution
- The decision required from the user (when one is needed)

Typical conflicts to watch for:
- Design proposes something that does not fit the approved dimensions.
- Cost budgets a different material than the Designer selected.
- Functionality needs access the design blocks.
- Time schedules work before materials arrive.
- 3D model uses measurements that differ from the approved ones.
- Risk identifies a problem requiring redesign.
- Build sequence places tasks in an impossible order.

## 6. Stage control

Only the Coordinator changes the official stage. Stages are listed in the master spec. The
Coordinator keeps the workspace status current: stage, owner, current task, open questions,
conflicts, decisions, and the single recommended next action.

## Coordinator deliverables

Workspace classification · active specialist list · project/hobby summary · requirements summary ·
confirmed facts · assumptions · open questions · current stage · current owner · current task ·
conflicts · decisions · next action · final integrated plan.
