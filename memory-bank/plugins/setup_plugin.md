# Setup Phase Instructions

This phase prepares the project structure and tracking files. Follow these steps in order.

## Step 1: Create Core Files

Create these files if they don't exist:

### 1.1 Create project documentation files in root `memory-bank/` folder -- if not exists:

**product.md**
```markdown
# Product Context

## Overview
[Brief description of what we're building]

## Core Features
- Feature 1: [Description]
- Feature 2: [Description]
- Feature 3: [Description]

## User Types
- Primary users: [Who will use this]
- Their main needs: [What problems we solve]

## Success Metrics
- [How we measure if this works]
```

**structure.md**
```markdown
# Project Structure

## Source Code Organization
src/
├── components/     # UI components
├── api/           # Backend endpoints
├── utils/         # Helper functions
└── tests/         # Test files

## Key Files
- Main entry: src/index.js
- Configuration: config.json
- Database schema: src/db/schema.sql

## Naming Conventions
- Files: camelCase.js
- Components: PascalCase.jsx
- CSS: kebab-case.css
```

**tech.md**
```markdown
# Technical Stack

## Core Technologies
- Language: [e.g., JavaScript/TypeScript]
- Framework: [e.g., React, Next.js]
- Database: [e.g., PostgreSQL, MongoDB]
- Hosting: [e.g., Vercel, AWS]

## Key Libraries
- [Library]: [Purpose]
- [Library]: [Purpose]

## Development Setup
npm install
npm run dev

## Common Commands
- `npm run dev` - Start development
- `npm run test` - Run tests
- `npm run build` - Build for production
```

### 1.2 Create memory-bank folder
```
memory-bank/
```

### 1.3 Create tracking files
In the memory-bank folder, create:
- `activeContext.md` - Current project state and recent changes
- `dependencytracker.md` - File dependencies

### 1.3 Create memorybankrules.md
Create or Format this file in the project root with:

--- start of memorybankrules.md
```
[STATE_TRACKER]
CURRENT_PHASE: Setup/Maintenance
NEXT_PHASE: Strategy  
LAST_ACTION: "Identified core directories and documentation structure"
NEXT_ACTION: "Analyze existing task structure and create modernized format"

[TRANSITION_REQUIREMENTS]
- [ ] Core directories catalogued
- [ ] Documentation structure mapped .. 

[LEARNING_LOG]
- NEVER, EVER, GUESS!. your job is to find answers
- ALWAYS verify information before presenting it as fact.
- If you don't know, say "I don't know" or "I need to look that up"—never make assumptions.
```
--- end memorybankrules.md


## Step 2: Identify Project Structure

### 2.1 Find code directories
Look in the project root for folders containing source code:
- Common names: `src`, `app`, `lib`, `packages`
- Skip: `.git`, `node_modules`, `venv`, `build`, `dist`
- Skip: `docs`, `documentation` (these are for documentation)

## Step 3: Create Dependency Tracker

### 3.1 Basic structure
Update `memory-bank/dependencytracker.md`:
```
# Project Dependencies

## Core Modules
- List main modules/files here
- Example: src/app.js
- Example: src/database/connection.js

## Dependencies
- ModuleA → depends on → ModuleB
- ModuleB → depends on → ModuleC
(Fill in as you discover dependencies)
```

### 3.2 Scan for actual dependencies
- Look at import statements in code files
- Note which files reference which
- Update the tracker with what you find

## Step 4: Update Progress

After completing the above steps, update:

### 4.1 activeContext.md
Add a note about what's been set up:
```
## Current Status
- Setup phase completed on [date]
- Code directories identified: src, tests
- Dependency tracking initialized
- Ready to move to Strategy phase

## Recent Changes
- Initialized project structure
- Created tracking files
- Identified code directories
```

## Step 5: Ready for Next Phase?

Check if everything is ready:
- ✓ All tracking files created
- ✓ Code directories identified
- ✓ Basic dependencies noted

If yes, update memorybankrules.md:
```
current_phase: Strategy
last_action: "Setup completed"
next_action: "Begin task planning"
```

## Common Patterns to Look For

When scanning the project:

### Typical JavaScript/TypeScript project:
- Code in: `src/`, `lib/`, `app/`
- Tests in: `tests/`, `test/`, `__tests__/`
- Config files: `package.json`, `tsconfig.json`

### Typical Python project:
- Code in: `src/`, project name folder, `app/`
- Tests in: `tests/`, `test/`
- Config files: `setup.py`, `pyproject.toml`

### Documentation folders (skip these for code):
- `docs/`, `documentation/`, `wiki/`
- README files are okay to note but not code directories

## Simple Response Format

After completing setup tasks, end your response with:

```
Setup Progress:
- Created: [list any new files]
- Updated: [list any updated files]  
- Next: [what to do next]
- Phase Status: [Setup/Ready for Strategy]
```

That's it! Keep it simple and focus on getting the basic structure in place.