# Giuice memory-bank an Optimized Project Management System

A simple, scalable system for managing software projects that ANY AI can follow.

## Agent Mode (Copilot Chat)
- Agent Mode is a GitHub Copilot Chat feature that lets you configure modes (specialized behavior) per repository.
- This system works by pointing Copilot Chat to `.github/copilot-instructions.md` and the `memory-bank/` folder. The plugins guide the AI through Setup → Strategy → Execution.
- Keep filenames exactly as referenced in the plugins. The AI will create and update the needed tracking files for you.

## Core Philosophy
- **Fewer files** = Less confusion
- **Simple formats** = Better understanding  
- **Clear progression** = Predictable workflow
- **Scalable structure** = Handles 10 or 1000 tasks

## One‑Minute TL;DR
1) Copy the `memory-bank/` folder into your project root.
2) In VS Code, create `.github/copilot-instructions.md` by copying `memory-bank/plugins/core_system_prompt.md`.
3) Start chatting with Copilot Chat in “Agent Mode” — the AI will create and maintain the rest (rules, tasks, context) following the plugins.

## Quick Start Guide

### Initial Setup
1. **Configure your AI system prompt**
   - Copy the [memory-bank](memory-bank/) folder to your project root
   - In VS Code, create a `.github` folder in your project
   - Save the [Core System Prompt](memory-bank/plugins/core_system_prompt.md) as `copilot-instructions.md`

2. **Use the provided templates**
   - Check the [templates folder](memory-bank/templates/) for examples of:
     - `product.md` - What you're building
     - `structure.md` - Where files go
     - `tech.md` - How you build it

3. **Optional: Create GitHub Copilot Modes**
   - Use each plugin (setup, strategy, execution) to create specialized modes
   - This improves AI performance for each specific phase
  

## File Structure
```
project-root/
├── memorybankrules.md        # Current phase tracker (AI creates/updates)
└── memory-bank/
    ├── product.md            # What we're building
    ├── structure.md          # Where files go
    ├── tech.md               # How we build
   ├── activeContext.md      # Current state (AI creates/updates)
   ├── dependencytracker.md  # File relationships (AI creates/updates)
    └── tasks/
      ├── index.md          # Feature overview (AI creates/updates)
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

### Getting Started by Phase

#### First Time Setup
1. Start with the **Setup phase**
   - Create the basic project structure
   - Identify your code directories
   - Note basic dependencies
2. Move to **Strategy phase** when ready

#### Planning Your Work
1. Use the **Strategy phase**
   - List all features in `tasks/index.md`
   - Create individual `tasks/[feature]_implementation.md` files
   - Break down features into concrete tasks with checkboxes
   - Set priorities for execution
2. Move to **Execution phase** when planning is complete

#### Ready to Code
1. Use the **Execution phase**
   - Pick a feature from `tasks/index.md`
   - Work through unchecked tasks in the feature file
   - Mark completed tasks with `[x]`
   - Update progress tracking
   - Move to the next feature when done

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