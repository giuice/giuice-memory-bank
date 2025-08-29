# Execution Phase Instructions

This phase implements features from the task files created in Strategy phase.

> **Global rule:** After any task state change or file edit, immediately update **memorybankrules.md** and **memory-bank/tasks/index.md**.

> Note: Examples below are illustrative placeholders. Adapt names, routes, files, and outputs to the current feature and stack.

## Step 1: Check What to Work On

### 1.1 Read the index

Look at `memory-bank/tasks/index.md` to see feature priorities:

* **Active Development**: Continue working on these
* **Ready to Start**: Pick the highest priority
* **Completed**: Skip these

### 1.2 Load the feature file

Open the specific feature file, e.g., `memory-bank/tasks/{feature}_implementation.md`
Find the first unchecked task `[ ]` or continue where you left off `[~]`

## Step 2: Work Through Tasks

### 2.1 Starting a task

Mark it as in-progress in the feature file:

```markdown
# Example (illustrative)
- [~] Task 2: Build endpoint for <resource> ← WORKING ON THIS
```

### 2.2 For subtasks

Work through them one by one:

```markdown
# Example (illustrative)
- [~] Task 2: Build endpoint for <resource>
  - [x] 2.1: Create <HTTP VERB> /api/<resource> route ✓
  - [~] 2.2: Add input validation ← CURRENT
  - [ ] 2.3: Generate access token / response payload
```

### 2.3 Execute the actual work

* Create/modify the files mentioned in the task
* Follow any implementation notes provided
* Test that your changes work
* Handle errors gracefully

### 2.4 Complete the task

Update the feature file:

```markdown
# Example (illustrative)
- [x] Task 2: Build endpoint for <resource> ✓ DONE
  - [x] 2.1: Create <HTTP VERB> /api/<resource> route
  - [x] 2.2: Add input validation  
  - [x] 2.3: Generate access token / response payload
```

### 2.5 Update ledgers (mandatory)

Immediately reflect the change in both files.

**memorybankrules.md**

```markdown
current_phase: Execution
last_action: "Task {id} - {short_desc} [{state}]"
next_action: "{next_step_hint}"
last_update: "{ISO8601 timestamp}"
active_feature: "{feature_key}"
progress_hint: "{X of Y tasks complete}"
```

**memory-bank/tasks/index.md**

```markdown
## Active Development
- {feature_key}_implementation.md - Task {current} of {total} ({percent}%)

## Ready to Start
- {next_feature}.md {optional_note}

## Completed
{leave as-is unless a feature just finished}
```

## Step 3: Track Progress

### 3.1 Update the feature file

Add notes about what was accomplished:

```markdown
# Example (illustrative)
## Current Focus
~~Working on Task 2.2~~ → Completed Task 2, moving to Task 3

## Completion Notes
- Task 2: Endpoint working at <HTTP VERB> /api/<resource>
  - Returns expected token or data on success
  - Proper error messages for invalid inputs
  - Rate limiting added if applicable
```

### 3.2 Update activeContext.md

Keep the overall project status current:

```markdown
# Example (illustrative)
## Current Status
- Feature: {feature_name} ({feature_key}_implementation.md)
- Progress: 3 of 5 tasks complete
- Just finished: Primary endpoint with token issuance
- Next: Flow for <next capability>

## Recent Changes  
- Created src/api/<feature>/<action>.<ext>
- Added utility in src/utils/<utility>.<ext>
- Updated database schema with <relevant_table> table
```

### 3.3 Update index.md

Show which features are active in `memory-bank/tasks/index.md`:

```markdown
# Example (illustrative)
## Active Development
- {feature_key}_implementation.md - Task 3 of 5 (60%)

## Ready to Start
- ui_setup.md (waiting for {feature_key})
```

## Step 4: Feature Completion

When ALL tasks in a feature file are done:

### 4.1 Mark feature complete

In the feature file:

```markdown
# Example (illustrative)
# {Feature Name} Implementation ✓ COMPLETED

## Overview
[...]

## Tasks
- [x] Task 1: Set up data structures
- [x] Task 2: Build primary endpoint
- [x] Task 3: Secondary flow
- [x] Task 4: State/session management

## Status: COMPLETE - All tasks finished on [date]
```

### 4.2 Update index.md

Move to completed section in `memory-bank/tasks/index.md`:

```markdown
# Example (illustrative)
## Active Development
(empty or next feature)

## Completed
- {feature_key}_implementation.md ✓ (all tasks done)
```

### 4.3 Start next feature

Pick the highest priority from "Ready to Start" and begin Step 1 again.

## Step 5: Switching Between Features

Sometimes you need to work on multiple features in parallel:

### Managing multiple active features:

```markdown
# Example (illustrative)
## Active Development
- {feature_key}_implementation.md - Task 3 of 5 (blocked)
- api_endpoints.md - Task 1 of 6 (in progress)
```

### When blocked:

Note why in the feature file:

```markdown
# Example (illustrative)
## Current Focus
Task 3 blocked - waiting for external service setup
Switched to api_endpoints.md meanwhile
```

## Step 6: Handling Dependencies

### Check before starting:

```markdown
# Example (illustrative)
## Dependencies
- Requires: database_schema.md ✓ Complete
- Requires: config_setup.md ✓ Complete
```

### Update when creating dependencies:

In `dependencytracker.md`:

```markdown
# Example (illustrative)
## Feature Dependencies
- ui_setup → requires → {feature_key}_implementation
- billing_integration → requires → api_endpoints

## File Dependencies  
- src/api/<resource>.js → depends on → src/utils/<helper>.js
- src/components/MainView.js → depends on → src/api/apiClient.js
```

## All Features Complete?

When all features in "Ready to Start" are done:

Update `memorybankrules.md`:

```
# Example (illustrative)
current_phase: Strategy  
last_action: "Completed all planned features"
next_action: "Plan next batch of features"
```

## Working with Large Projects

### Focus on one feature:

* Load only the feature file you're working on
* Don't try to load all 30 feature files at once
* Use `memory-bank/tasks/index.md` to navigate between features

### Track carefully:

* Always mark tasks as you work `[~]`
* Complete them when done `[x]`
* Add notes about important decisions

### Test frequently:

* After each task, verify it works
* Don’t wait until the end of a feature
* Document any issues found

## Response Format

After working on tasks:

```
# Example (illustrative)
Execution Progress:
- Feature: {feature_name}
- Completed: Task X.Y - <short description>
- Created/Modified: <files changed>
- Feature Progress: X of Y tasks done
- Next: <next task or feature>
- Ledgers Updated: yes
```

## Quick Reference

**Task States:**

* `[ ]` Not started
* `[~]` In progress
* `[x]` Complete

**Where to look:**

* Overall status → `memory-bank/tasks/index.md`
* Feature details → `memory-bank/tasks/{feature}_implementation.md`
* Current state → `activeContext.md`
* Dependencies → `dependencytracker.md`

**When stuck:**

1. Check dependencies are met
2. Break task into smaller subtasks
3. Note the blocker and switch features
4. Update `activeContext.md` with the issue
