Here is the Strategy Phase file generalized. Structure unchanged. Examples marked as illustrative placeholders.

---

# Strategy Phase Instructions

This phase breaks down the project into features and tasks. Each feature gets its own file.

> **Global rule:** Examples below are illustrative placeholders. Do not treat example names, routes, or files as mandatory. Replace with the current project’s terms.

## Step 1: Create Task Index

Create `memory-bank/tasks/index.md` to track all features:

```markdown
# Project Features

## Active Development
(features currently being worked on)

## Ready to Start
(features fully planned)

## Backlog
(features identified but not planned yet)

## Completed
(finished features)
```

## Step 2: Identify Features to Build

List the main features/stories your project needs.
**Examples (illustrative):**

* Authentication
* Dashboard UI
* Billing
* Administration
* Core API

For each feature, create a planning file: `memory-bank/tasks/{feature_key}_implementation.md`

## Step 3: Create Feature Task Files

For each feature, create a file like `memory-bank/tasks/{feature_key}_implementation.md`:

```markdown
# {Feature Name} Implementation

## Overview
Brief description of what this feature does and why it's needed

## Tasks
- [ ] Task 1: Clear, specific task description
- [ ] Task 2: Another concrete task
  - [ ] 2.1: Subtask if needed
  - [ ] 2.2: Another subtask
- [ ] Task 3: Final task for this feature

## Dependencies
- Requires: What must be done before this
- Blocks: What can't start until this is done

## Technical Notes
- Key decisions or approaches
- Technologies to use
- Files that will be created/modified
```

## Step 4: Break Down Tasks Properly

### Good task breakdown (illustrative):

```markdown
## Tasks
- [ ] Task 1: Set up data model
  - [ ] 1.1: Create <table|collection> for <entity>
  - [ ] 1.2: Add indexes/constraints for key lookups
  - [ ] 1.3: Create supporting <table|collection> for sessions/state
- [ ] Task 2: Build API endpoint for <resource>
  - [ ] 2.1: Create <HTTP VERB> /api/<resource> route
  - [ ] 2.2: Add credential/input verification
  - [ ] 2.3: Generate access token/session or response payload
- [ ] Task 3: Create UI for <flow>
  - [ ] 3.1: Design form/view component
  - [ ] 3.2: Add client-side validation
  - [ ] 3.3: Handle success/error states
```

### Each task should:

* Take less than a day to complete
* Produce something concrete (file, feature, fix)
* Be testable independently
* Have clear completion criteria

## Step 5: Add Implementation Details

For complex tasks, add a section with specifics.

**Illustrative template:**

```markdown
## Implementation Guide

### Task 1: Set up data model
**Files involved:**
- migrations/<id>_create_<entity>.sql
- src/db/<schema_or_model>.{ext}

**Approach:**
1. Create migration/model for <entity>
2. Add unique/index constraints for <key>
3. Run migration
4. Test with sample insert

### Task 2: Build API endpoint for <resource>
**Files involved:**
- src/api/<domain>/<action>.{ext}
- src/utils/<token_or_helper>.{ext}

**Approach:**
1. Set up <HTTP VERB> route handler
2. Validate input or credentials
3. Check against data store or service
4. Return token/session or data if valid
```

## Step 6: Update Index and Context

### Update `memory-bank/tasks/index.md` (illustrative):

```markdown
## Ready to Start
- {feature_key}_implementation.md ({task_count} tasks)
- {another_feature_key}_implementation.md ({task_count} tasks)

## Backlog
- {future_feature_key}_implementation.md
```

### Update `activeContext.md` (illustrative):

```markdown
## Current Status
- Strategy phase completed
- Planned {feature_count} features with {task_total} total tasks
- Priority: Start with {first_feature_key}_implementation
- Next phase: Execution

## Features Planned
1. {Feature A} ({tasks_A} tasks) - Critical path
2. {Feature B} ({tasks_B} tasks) - Depends on {Feature A}
3. {Feature C} ({tasks_C} tasks) - Can be done later
```

## Step 7: Set Priorities

In `index.md`, order features by priority (illustrative):

```markdown
## Priority Order
1. {first_feature_key}_implementation.md - Required for core flows
2. {second_feature_key}_implementation.md - Core user experience
3. {third_feature_key}_implementation.md - Needed for frontend/backend integration
4. {fourth_feature_key}_implementation.md - Can be added later
```

## Ready for Execution?

Check:

* ✓ All critical features have task files
* ✓ Tasks are broken into manageable pieces
* ✓ Dependencies are noted
* ✓ `index.md` shows clear priorities

Update `memorybankrules.md`:

```
current_phase: Execution
last_action: "Planned {feature_count} features with {task_total} tasks"
next_action: "Start with {first_feature_key}_implementation"
```

## Tips for Large Projects

### Organize by milestone (illustrative)

```
tasks/
├── index.md
├── v1.0/
│   ├── {feature_key}_implementation.md
│   └── {feature_key}_basic.md
└── v2.0/
    ├── {feature_key}_implementation.md
    └── {feature_key}_admin.md
```

### Keep task files focused

* One feature per file
* 5–15 tasks per feature
* If more than 15, split into two features

### Use clear naming

* {feature\_key}\_implementation.md (not ambiguous abbreviations)
* {domain}\_integration.md (not vague names)

## Response Format

After planning:

```
Strategy Complete:
- Created: {feature_count} feature files in tasks/
- Total tasks: {task_total} across all features
- Priority: Starting with {first_feature_key}_implementation
- Phase: Ready for Execution
```
