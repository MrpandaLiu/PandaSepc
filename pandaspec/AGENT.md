# PandaSpec Instructions

Instructions for AI coding assistants using PandaSpec for spec-driven development with markdown-based specifications.

## TL;DR Quick Checklist

- Search existing work: `ls pandaspec/features/` (use `rg` for full-text search)
- Decide scope: new feature vs modify existing functionality
- Pick a unique `feature-name`: kebab-case, verb-led (`add-`, `update-`, `remove-`, `refactor-`)
- Scaffold: Create feature folder in `pandaspec/features/` with `design.md` and `task.md`
- Write design: Include requirement background, implementation plan, and test points
- Write tasks: Create ordered checklist of implementation steps
- Request approval: Do not start implementation until design is approved

## Three-Stage Workflow

### Stage 1: Planning Features
Create a plan when you need to:
- Add features or functionality
- Make significant changes (API, architecture)
- Change business logic
- Optimize performance (changes behavior)
- Update security patterns

Triggers (examples):
- "Help me create a feature plan"
- "Help me design a feature"
- "Help me create a spec for this feature"
- "I want to create a feature specification"
- "I want to plan this change"

For planning, create a `spec.plan.md` file in the project root using the plan command.

Skip planning for:
- Bug fixes (restore intended behavior)
- Typos, formatting, comments
- Dependency updates (non-breaking)
- Configuration changes
- Tests for existing behavior

**Workflow**
1. Review existing features in `pandaspec/features/` and explore the codebase to understand current context.
2. Use the `plan` command to create a `spec.plan.md` file with your requirements.
3. Use the `design` command to convert your plan into design documents in `pandaspec/features/<feature-name>/`.

### Stage 2: Designing Features
Create design documents to:
- Document technical approach
- Identify potential issues early
- Communicate implementation plan
- Create traceable requirements

**Workflow**
1. Use the `design` command with your `spec.plan.md` file
2. The command will create a feature folder in `pandaspec/features/` with `design.md` and `task.md`
3. The `design.md` contains requirement background, change diagrams, implementation plan, and test points
4. The `task.md` contains an ordered list of implementation steps
5. Review and refine the design before implementation

### Stage 3: Implementing Features
Track these steps as TODOs and complete them one by one.
1. **Read design.md** - Understand the technical approach
2. **Read task.md** - Get implementation checklist
3. **Implement tasks sequentially** - Complete in order
4. **Confirm completion** - Ensure every item in `task.md` is finished before considering implementation done
5. **Update checklist** - After all work is done, mark each task as completed so the list reflects reality
6. **Approval gate** - Do not start implementation until the design is reviewed and approved

## Before Any Task

**Context Checklist:**
- [ ] Explore existing codebase to understand current implementation
- [ ] Check `pandaspec/features/` for potential conflicts
- [ ] Review project conventions and architecture
- [ ] Read `spec.plan.md` or design docs for the feature

**Before Creating Features:**
- Always check if similar functionality already exists
- Prefer extending existing features over creating duplicates
- If request is ambiguous, ask 1–2 clarifying questions before creating design docs

### Search Guidance
- Enumerate features: `ls pandaspec/features/`
- Show details: Read individual `design.md` and `task.md` files
- Full-text search: `rg -n "requirement|feature|task" pandaspec/`

## Quick Start

### Command Workflow
1. Plan: Create a `spec.plan.md` with your requirements using the plan command
2. Design: Convert the plan to design documents in `pandaspec/features/` using the design command
3. Apply: Implement the feature following the tasks using the apply command

### PandaSpec Commands

```bash
# Use the slash commands:
/pandaspec plan        # Create a new feature plan (creates spec.plan.md)
/pandaspec design      # Create design from plan (creates feature folder in pandaspec/features/)
/pandaspec apply [feature-name]  # Implement a designed feature (follows task.md)
```

## Directory Structure

```
pandaspec/
├── features/               # Feature implementations
│   └── [feature-name]/     # Each feature in its own folder
│       ├── design.md       # Technical design, requirements, test points
│       └── task.md         # Implementation steps checklist
└── AGENT.md               # This file - agent guidelines
```

## Creating Feature Plans

### Using the Plan Command

1. **Create spec.plan.md:** Run `/pandaspec plan` to create a template in the project root
2. **Edit spec.plan.md:** Fill in requirements, expected outcomes, and constraints
3. **Prepare for design:** Ensure the plan is detailed enough for technical design

Basic template created by the plan command:
```markdown
# Feature Plan

## Requirement Title
[Clear title of the feature or change]

## Requirement Description
[Detailed description of what is needed]

## Expected Outcome
[What should be achieved by this feature]

## Constraints and Considerations
[Any limitations, requirements, or special considerations]
```

### Using the Design Command

1. **Validate plan:** Ensure `spec.plan.md` exists with sufficient detail
2. **Create feature folder:** The command creates `pandaspec/features/<feature-name>/`
3. **Generate design.md:**
```markdown
# Feature Design

## Requirement Background
[Context and background for the requirement]

## Problem Cause (for bug fixes)
[Root cause analysis if this is a bug fix]

## Implementation Plan
[Technical approach and code modifications needed]

## Change Diagrams (if needed)
[Architecture diagrams, flow charts, sequence diagrams]

## Suggested Test Points
[Test cases and validation approaches]
```

4. **Generate task.md:**
```markdown
## Implementation Tasks
- [ ] Task 1: Description
- [ ] Task 2: Description
- [ ] Task 3: Description
```

## Creating Feature Implementations

### Apply Command Process

1. **Read design:** Understand the technical approach from design.md
2. **Follow tasks:** Execute tasks from task.md sequentially
3. **Implement feature:** Write code following the design
4. **Validate:** Test against requirements in design.md
5. **Complete tasks:** Update task.md as you progress

## Best Practices

### Simplicity First
- Default to minimal, focused implementations
- Single-file implementations until proven insufficient
- Choose proven, simple patterns
- Make small, incremental changes

### Feature Naming
- Use kebab-case, descriptive names: `user-authentication`, `payment-processing`
- Single purpose per feature
- Descriptive enough that the name explains the core functionality

### Clear References
- Use `file.ts:42` format for code locations
- Reference design docs as `pandaspec/features/<name>/design.md`
- Link related issues and PRs if applicable

## Tool Selection Guide

| Task | Tool | Why |
|------|------|-----|
| Find files by pattern | Glob | Fast pattern matching |
| Search code content | Grep | Optimized regex search |
| Read specific files | Read | Direct file access |
| Explore unknown scope | Task | Multi-step investigation |

## Error Recovery

### Missing Context
1. Explore the codebase with `ls`, `rg`, or direct file reads
2. Check existing features in `pandaspec/features/`
3. Review recent implementations
4. Ask for clarification if requirements are unclear

## Quick Reference

### Stage Indicators
- `spec.plan.md` - Initial requirements
- `pandaspec/features/` - Designed but not yet implemented
- Implemented features - In the main codebase

### File Purposes
- `spec.plan.md` - Initial requirements and plan
- `design.md` - Technical approach and requirements
- `task.md` - Implementation steps checklist

### Command Flow
```
/pandaspec plan  →  spec.plan.md
    ↓
/pandaspec design  →  pandaspec/features/[name]/
    ↓
/pandaspec apply [name]  →  Implementation
```

Remember: Design docs capture intent. Code implements the design. Keep them in sync.