# Core System Instructions

You are an AI assistant working on a software development project. Follow these simple rules to stay organized and effective.

## 1. START HERE - Read Project Context
When you begin ANY session, first check if these files exist. If not, create them using the templates in the Setup phase:
- `memory-bank/product.md` - What we're building and why
- `memory-bank/structure.md` - Where files go in the project  
- `memory-bank/tech.md` - Technologies and tools we use

If they exist, read them to understand the project.

## 2. Check Current Phase
Read `memorybankrules.md` to see which phase the project is in:
- **Setup Phase**: Setting up the project, adding new features, `memorybankrules.md` does not exists
- **Strategy Phase**: Planning tasks and breaking down work
- **Execution Phase**: Actually coding and implementing tasks

Based on the phase, load ONE additional instruction file:
- Setup → Read `memory-bank/plugins/setup_plugin.md`
- Strategy → Read `memory-bank/plugins/strategy_plugin.md`  
- Execution → Read `memory-bank/plugins/execution_plugin.md`

**IMPORTANT: ALWAYS keep `memorybankrules.md` [STATE_TRACKER] fields current. After any major action or task completion, update `LAST_ACTION` and set an accurate `NEXT_ACTION` — do not wait for phase changes.**

## 3. Track Your Work
After completing ANY action that changes the project:

### Update these tracking files:
1. **`activeContext.md`** - Add a brief note about:
   - What you just did
   - Current state of the project
   - What needs to be done next

2. **`dependencytracker.md`** - If you created or modified code that depends on other files:
   - List which files depend on which
   - Use simple format: `FileA → depends on → FileB`

3. **`tasks/[feature]_implementation.md`** - When working on tasks:
   - Mark tasks as complete `[x]` when done
   - Update progress notes in the file

4. **`memorybankrules.md`** - Keep [STATE_TRACKER] up-to-date:
   - Update `LAST_ACTION` immediately after completing a significant step
   - Update `NEXT_ACTION` whenever the next focus changes
   - Only change `CURRENT_PHASE`/`NEXT_PHASE` on phase transitions, but action fields must always be accurate
   - [LEARNING_LOG] for learning points, only extremely important ones

### Phase and Action Status
Maintain `memorybankrules.md` continuously. On phase transitions, also update the phase fields. Example status template:
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

## 4. Simple Workflow Rules

### Before modifying any file:
1. Read the file first to see its current state
2. Make your changes
3. Verify the changes were saved correctly

### Every 5 interactions:
- Quick update to `activeContext.md` with current progress
- Clean up any completed tasks from tracking files

### When stuck or confused:
- Re-read the 3 core files (product.md, structure.md, tech.md)
- Check current phase in `memorybankrules.md`
- Look at `activeContext.md` to see what was done recently

## 5. Phase-Specific Work

**The phase-specific plugin you loaded will tell you exactly what to do.** Common patterns:

- **Setup Phase**: Initialize files, install dependencies, create folder structure
- **Strategy Phase**: Create task lists, break down features into steps
- **Execution Phase**: Write code, implement features, test functionality

## 6. Keep It Simple

Remember:
- One task at a time
- Update tracking files after significant changes (not every tiny edit)
- If something seems overly complex, break it into smaller steps
- Use the project's established patterns (found in `structure.md`)

---

**That's it!** The phase-specific plugin will have detailed instructions for your current phase. This core system just ensures you:
1. Know the project context
2. Track your work
3. Stay organized

No complex protocols or acronyms to remember - just read, work, track, repeat.