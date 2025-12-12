---
name: PandaSpec: Design
description: Create a technical design document based on user requirements.
category: PandaSpec
tags: [pandaspec, design]
---
<!-- PANDASPEC:START -->
**Guardrails**
- Favor straightforward, minimal implementations first and add complexity only when it is requested or clearly required.
- Keep changes tightly scoped to the requested outcome.
- Refer to `pandaspec/AGENT.md` (located inside the `pandaspec/` directory—run `ls pandaspec` if you don't see it) if you need additional PandaSpec conventions or clarifications.
- Identify any vague or ambiguous details and ask the necessary follow-up questions before creating design documents.
- Do not write any code during the design stage. Only create design documents (design.md, task.md). Implementation happens in the apply stage after approval.

**Steps**
1. Check if spec.plan.md exists in the project root. If not, prompt the user to create one using the plan command first.
2. Read the spec.plan.md file to understand user requirements.
3. If the requirements are not detailed enough to create a technical design, ask clarifying questions.
4. Once requirements are clear, delete the spec.plan.md file.
5. Create a new folder in `pandaspec/features/` using an appropriate English name based on the feature.
6. Inside the new folder, create `design.md` and `task.md` files.
   - design.md: Contains requirement background, change diagrams (architecture, sequence, flow diagrams if needed), problem cause (for bug fixes), implementation plan (design and related code modifications), suggested test points (including test cases).
   - task.md: Contains an ordered list of small, verifiable work items that deliver user-visible progress, include validation (tests, tooling), and highlight dependencies or parallelizable work.

**Reference**
- Use the content from spec.plan.md to inform the design documents.
- Ensure all design decisions are clearly justified in the design.md file.
- Always use Chinese when chating with user or writing documents.
<!-- PANDASPEC:END -->