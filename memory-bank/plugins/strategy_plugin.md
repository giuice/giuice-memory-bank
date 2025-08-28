# Strategy Phase Instructions

This phase breaks down the project into features and tasks. Each feature gets its own file.

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

List the main features/stories your project needs. Examples:
- User authentication
- Dashboard interface  
- Payment processing
- Admin panel
- API endpoints

For each feature, create a planning file: `memory-bank/tasks/[feature]_implementation.md`

## Step 3: Create Feature Task Files

For each feature, create a file like `memory-bank/tasks/auth_implementation.md`:

```markdown
# [Feature Name] Implementation

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

### Good task breakdown:
```markdown
## Tasks
- [ ] Task 1: Set up database tables
  - [ ] 1.1: Create users table with email, password_hash
  - [ ] 1.2: Add indexes for email lookups
  - [ ] 1.3: Create sessions table
- [ ] Task 2: Build login endpoint
  - [ ] 2.1: Create POST /api/login route
  - [ ] 2.2: Add password verification
  - [ ] 2.3: Generate JWT token
- [ ] Task 3: Create login UI
  - [ ] 3.1: Design login form component
  - [ ] 3.2: Add form validation
  - [ ] 3.3: Handle success/error states
```

### Each task should:
- Take less than a day to complete
- Produce something concrete (file, feature, fix)
- Be testable independently
- Have clear completion criteria

## Step 5: Add Implementation Details

For complex tasks, add a section with specifics:

```markdown
## Implementation Guide

### Task 1: Set up database tables
**Files involved:**
- migrations/001_create_users.sql
- src/db/schema.sql

**Approach:**
1. Create migration file with users table
2. Add email unique constraint  
3. Run migration
4. Test with sample insert

### Task 2: Build login endpoint
**Files involved:**
- src/api/auth/login.js
- src/utils/jwt.js

**Approach:**
1. Set up POST route handler
2. Validate email/password from request
3. Check against database
4. Return JWT if valid
```

## Step 6: Update Index and Context

### Update index.md:
```markdown
## Ready to Start
- auth_implementation.md (5 tasks)
- dashboard_setup.md (8 tasks)

## Backlog
- payment_integration.md
```

### Update activeContext.md:
```markdown
## Current Status
- Strategy phase completed
- Planned 3 features with 21 total tasks
- Priority: Start with auth_implementation
- Next phase: Execution

## Features Planned
1. Authentication (5 tasks) - Critical path
2. Dashboard (8 tasks) - Depends on auth
3. Payment (8 tasks) - Can be done later
```

## Step 7: Set Priorities

In index.md, order features by priority:

```markdown
## Priority Order
1. auth_implementation.md - Required for everything
2. dashboard_setup.md - Core user experience  
3. api_endpoints.md - Needed for frontend
4. payment_integration.md - Can be added later
```

## Ready for Execution?

Check:
- ✓ All critical features have task files
- ✓ Tasks are broken into manageable pieces
- ✓ Dependencies are noted
- ✓ Index.md shows clear priorities

Update `memorybankrules.md`:
```
current_phase: Execution
last_action: "Planned [X] features with [Y] tasks"
next_action: "Start with [first feature]"
```

## Tips for Large Projects

### Organize by milestone
Group features into releases:
```
tasks/
├── index.md
├── v1.0/
│   ├── auth_implementation.md
│   └── basic_dashboard.md
└── v2.0/
    ├── payment_integration.md
    └── admin_panel.md
```

### Keep task files focused
- One feature per file
- 5-15 tasks per feature
- If more than 15, split into two features

### Use clear naming
- auth_implementation.md (not auth.md)
- payment_integration.md (not pay.md)
- Makes purpose obvious

## Response Format

After planning:
```
Strategy Complete:
- Created: [X] feature files in tasks/
- Total tasks: [Y] across all features  
- Priority: Starting with [feature]
- Phase: Ready for Execution
```