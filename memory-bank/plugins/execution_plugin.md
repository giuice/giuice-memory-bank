# Execution Phase Instructions

This phase implements features from the task files created in Strategy phase.

## Step 1: Check What to Work On

### 1.1 Read the index
Look at `memory-bank/tasks/index.md` to see feature priorities:
- **Active Development**: Continue working on these
- **Ready to Start**: Pick the highest priority
- **Completed**: Skip these

### 1.2 Load the feature file
Open the specific feature file, e.g., `memory-bank/tasks/auth_implementation.md`
Find the first unchecked task `[ ]` or continue where you left off `[~]`

## Step 2: Work Through Tasks

### 2.1 Starting a task
Mark it as in-progress in the feature file:
```markdown
- [~] Task 2: Build login endpoint ← WORKING ON THIS
```

### 2.2 For subtasks
Work through them one by one:
```markdown
- [~] Task 2: Build login endpoint
  - [x] 2.1: Create POST /api/login route ✓
  - [~] 2.2: Add password verification ← CURRENT
  - [ ] 2.3: Generate JWT token
```

### 2.3 Execute the actual work
- Create/modify the files mentioned in the task
- Follow any implementation notes provided
- Test that your changes work
- Handle errors gracefully

### 2.4 Complete the task
Update the feature file:
```markdown
- [x] Task 2: Build login endpoint ✓ DONE
  - [x] 2.1: Create POST /api/login route
  - [x] 2.2: Add password verification  
  - [x] 2.3: Generate JWT token
```

## Step 3: Track Progress

### 3.1 Update the feature file
Add notes about what was accomplished:
```markdown
## Current Focus
~~Working on Task 2.2~~ → Completed Task 2, moving to Task 3

## Completion Notes
- Task 2: Login endpoint working at POST /api/login
  - Returns JWT token on success
  - Proper error messages for invalid credentials
  - Rate limiting added
```

### 3.2 Update activeContext.md
Keep the overall project status current:
```markdown
## Current Status
- Feature: Authentication (auth_implementation.md)
- Progress: 3 of 5 tasks complete
- Just finished: Login endpoint with JWT
- Next: Password reset flow

## Recent Changes  
- Created src/api/auth/login.js
- Added JWT utility in src/utils/jwt.js
- Updated database schema with sessions table
```

### 3.3 Update index.md
Show which features are active:
```markdown
## Active Development
- auth_implementation.md - Task 3 of 5 (60%)

## Ready to Start
- dashboard_setup.md (waiting for auth)
```

## Step 4: Feature Completion

When ALL tasks in a feature file are done:

### 4.1 Mark feature complete
In the feature file:
```markdown
# Authentication Implementation ✓ COMPLETED

## Overview
[...]

## Tasks
- [x] Task 1: Set up database tables
- [x] Task 2: Build login endpoint
- [x] Task 3: Password reset flow
- [x] Task 4: Session management

## Status: COMPLETE - All tasks finished on [date]
```

### 4.2 Update index.md
Move to completed section:
```markdown
## Active Development
(empty or next feature)

## Completed
- auth_implementation.md ✓ (4 tasks done)
```

### 4.3 Start next feature
Pick the highest priority from "Ready to Start" and begin Step 1 again.

## Step 5: Switching Between Features

Sometimes you need to work on multiple features in parallel:

### Managing multiple active features:
```markdown
## Active Development
- auth_implementation.md - Task 3 of 5 (blocked)
- api_endpoints.md - Task 1 of 6 (in progress)
```

### When blocked:
Note why in the feature file:
```markdown
## Current Focus
Task 3 blocked - waiting for email service setup
Switched to api_endpoints.md meanwhile
```

## Step 6: Handling Dependencies

### Check before starting:
```markdown
## Dependencies
- Requires: database_schema.md ✓ Complete
- Requires: config_setup.md ✓ Complete
```

### Update when creating dependencies:
In `dependencytracker.md`:
```markdown
## Feature Dependencies
- dashboard_setup → requires → auth_implementation
- payment_integration → requires → api_endpoints

## File Dependencies  
- src/api/users.js → depends on → src/utils/auth.js
- src/components/Dashboard.js → depends on → src/api/client.js
```

## All Features Complete?

When all features in "Ready to Start" are done:

Update `memorybankrules.md`:
```
current_phase: Strategy  
last_action: "Completed all planned features"
next_action: "Plan next batch of features"
```

## Working with Large Projects

### Focus on one feature:
- Load only the feature file you're working on
- Don't try to load all 30 feature files at once
- Use index.md to navigate between features

### Track carefully:
- Always mark tasks as you work `[~]` 
- Complete them when done `[x]`
- Add notes about important decisions

### Test frequently:
- After each task, verify it works
- Don't wait until the end of a feature
- Document any issues found

## Response Format

After working on tasks:
```
Execution Progress:
- Feature: [feature name]
- Completed: Task X.Y - [description]
- Created/Modified: [files changed]
- Feature Progress: X of Y tasks done
- Next: [next task or feature]
```

## Quick Reference

**Task States:**
- `[ ]` Not started
- `[~]` In progress
- `[x]` Complete

**Where to look:**
- Overall status → `tasks/index.md`
- Feature details → `tasks/[feature]_implementation.md`
- Current state → `activeContext.md`
- Dependencies → `dependencytracker.md`

**When stuck:**
1. Check dependencies are met
2. Break task into smaller subtasks
3. Note the blocker and switch features
4. Update activeContext.md with the issue