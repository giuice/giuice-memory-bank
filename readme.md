# Giuice memory-bank an Optimized Project Management System

A simple, scalable system for managing software projects that ANY AI can follow.

## Core Philosophy
- **Fewer files** = Less confusion
- **Simple formats** = Better understanding  
- **Clear progression** = Predictable workflow
- **Scalable structure** = Handles 10 or 1000 tasks

## File Structure
```
project-root/
├── memorybankrules.md        # Current phase tracker
└── memory-bank/
    ├── product.md            # What we're building
    ├── structure.md          # Where files go
    ├── tech.md               # How we build
    ├── activeContext.md      # Current state
    ├── dependencytracker.md  # File relationships
    └── tasks/
        ├── index.md          # Feature overview
        ├── auth_implementation.md
        ├── dashboard_setup.md
        └── [feature]_implementation.md
```

## Three Simple Phases

### Phase 1: Setup (When starting a project)
1. Create tracking files
2. Identify code directories
3. Note basic dependencies
4. Ready for planning

### Phase 2: Strategy (When planning work)  
1. Create tasks/index.md with feature list
2. Create tasks/[feature]_implementation.md per feature
3. Break down into concrete tasks with checkboxes
4. Set priorities
5. Ready for execution

### Phase 3: Execution (When doing the work)
1. Pick a feature from index.md
2. Work through unchecked tasks
3. Mark complete with [x]
4. Update progress tracking
5. Move to next feature

## Key Improvements from Original

| Original System | Optimized System |
|-----------------|------------------|
| 10+ tracking files | 5 essential files |
| Complex naming (IP1_T1_1_1) | Simple names (auth_implementation) |
| MUP, APM, PAVP protocols | Just "update when done" |
| Progress percentages | Simple checkboxes [x] |
| Multiple instruction files | Tasks in feature files |
| 300 tasks in one file | ~10 tasks per feature file |
| Complex XML-like tags | Clean markdown |

## How It Handles Scale

### Small Project (< 50 tasks)
```
tasks/
├── index.md
├── core_features.md
└── nice_to_have.md
```

### Medium Project (50-200 tasks)
```
tasks/
├── index.md
├── auth_implementation.md
├── dashboard_setup.md
├── api_endpoints.md
├── admin_panel.md
└── reporting_features.md
```

### Large Project (200+ tasks)
```
tasks/
├── index.md
├── v1.0/
│   ├── auth_implementation.md
│   ├── core_dashboard.md
│   └── basic_api.md
├── v2.0/
│   ├── payment_integration.md
│   ├── advanced_dashboard.md
│   └── analytics.md
└── v3.0/
    └── enterprise_features.md
```

## Working Example

### Starting a new feature:
1. **Check index.md:**
   ```markdown
   ## Ready to Start
   - auth_implementation.md (5 tasks)
   ```

2. **Open auth_implementation.md:**
   ```markdown
   ## Tasks
   - [ ] Task 1: Set up database tables
   - [ ] Task 2: Build login endpoint
   ```

3. **Do the work:**
   - Create the files
   - Test they work
   - Mark complete

4. **Update progress:**
   ```markdown
   - [x] Task 1: Set up database tables ✓
   - [~] Task 2: Build login endpoint ← CURRENT
   ```

## Why This Works Better

### For AI:
- **Less context needed** - Load only current feature file
- **Clear instructions** - Checkboxes show what to do
- **No complex rules** - Just read, work, check off
- **Tool agnostic** - Works with any AI's capabilities

### For Humans:
- **GitHub-friendly** - Markdown renders beautifully
- **Natural organization** - Features map to PRs/branches
- **Easy to review** - See progress at a glance
- **Standard format** - Looks like normal task lists

### For Teams:
- **Parallel work** - Multiple features can progress
- **No conflicts** - Each feature has own file
- **Clear ownership** - Assign features to people
- **Simple merging** - Less chance of git conflicts

## Quick Start Guid

A. **Set your system prompt with Core System Prompt [Core System Prompt](memory-bank/plugins/core_system_prompt.md)**
- On Vscode github copilot create `.github` folder and save core [Core System Prompt](memory-bank/plugins/core_system_prompt.md) with the name copilot-instructions.md
- I included in [Template Folder] (`memory-bank/templates`) product, structure and tech examples
- You can create Github Copilot Modes with each plugin(setup, strategy and execution) this is improve the work on exactly phase.

1. **First time?** Start in Setup phase:
   - Create the basic structure
   - Move to Strategy

2. **Planning work?** Strategy phase:
   - List features in index.md
   - Create feature files with tasks
   - Move to Execution

3. **Ready to code?** Execution phase:
   - Pick a feature
   - Work through tasks
   - Check them off

## Common Patterns

### Adding a new feature mid-project:
1. Create `tasks/new_feature_implementation.md`
2. Add to index.md under "Backlog"
3. Move to "Ready to Start" when planned
4. Execute when priority allows

### Handling blockers:
```markdown
## Current Focus
Task 3 blocked - waiting for API keys
Switched to dashboard_setup.md meanwhile
```

### Tracking decisions:
```markdown
## Implementation Notes
- Chose PostgreSQL over MongoDB for relationships
- Using JWT instead of sessions for stateless auth
- Rate limiting set to 10 requests/minute
```

## The Bottom Line

This system turns complex project management into three simple questions:
1. **What features do we need?** (Strategy)
2. **What tasks build each feature?** (Planning) 
3. **Which task is next?** (Execution)

No complex protocols. No redundant files. No overwhelming rules.

Just clear, actionable steps that any AI or human can follow.