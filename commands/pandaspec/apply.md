--- 
name: PandaSpec: Apply
description: Implement an approved PandaSpec design and track task completion.
category: PandaSpec
tags: [pandaspec, apply]
---
<!-- PANDASPEC:START -->
**Guardrails**
- Favor straightforward, minimal implementations first and add complexity only when it is requested or clearly required.
- Keep changes tightly scoped to the requested outcome.
- Refer to `pandaspec/AGENT.md` (located inside the `pandaspec/` directory—run `ls pandaspec` if you don't see it) if you need additional PandaSpec conventions or clarifications.

**Steps**
Track these steps as TODOs and complete them one by one.
1. Read the `design.md` and `task.md` files from the specified feature folder in `pandaspec/features/<feature-name>/` to confirm scope and acceptance criteria.
2. Work through tasks sequentially from `task.md`, keeping edits minimal and focused on the requested change.
3. Confirm completion before updating statuses—make sure every item in `task.md` is finished.
4. Update the checklist after all work is done so each task is marked `- [x]` and reflects reality.
5. Reference `ls pandaspec/features` or inspect specific feature folders when additional context is required.

**Reference**
- Use the content from design.md to guide implementation decisions.
- Follow the tasks outlined in task.md to ensure all requirements are met.
<!-- PANDASPEC:END -->