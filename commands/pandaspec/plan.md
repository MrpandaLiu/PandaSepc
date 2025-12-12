---
name: PandaSpec: Plan
description: Create a new PandaSpec plan and initialize spec documentation.
category: PandaSpec
tags: [pandaspec, plan]
---
<!-- PANDASPEC:START -->
**Guardrails**
- Favor straightforward, minimal requirements first and add complexity only when it is requested or clearly required.
- Keep plans tightly scoped to the requested outcome.
- Refer to `pandaspec/AGENT.md` (located inside the `pandaspec/` directory—run `ls pandaspec` if you don't see it) if you need additional PandaSpec conventions or clarifications.
- Create a spec.plan.md file in the project root to capture user requirements with a simple writing template.

**Steps**
1. Create a spec.plan.md file in the project root directory if it doesn't exist.
2. Provide a simple template for users to document their requirements in the spec.plan.md file.
3. The template should include sections for: requirement title, requirement description, expected outcome, and any constraints or special considerations.
4. Inform the user that they can edit this file to detail their requirements before proceeding to the design phase.

**Reference**
- Use the spec.plan.md file as input for the design phase when running the `design` command.
- The plan command should not implement any code, only document requirements.
- Always use Chinese when chating with user or writing documents.
<!-- PANDASPEC:END -->