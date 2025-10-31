# Project Directory Setup Scaffold

This prompt guides an AI agent to create the standard project directory structure.

## Instructions for AI Agent

Please create the following directory structure in the current project:

### 1. Create Main Directories

Create these top-level directories:

```bash
mkdir -p docs
mkdir -p scripts
mkdir -p work
```

### 2. Create Initial Files

Create the following initial files:

**`docs/README.md`** - Overview of documentation structure:
```markdown
# Documentation

This directory contains the architectural and constitutional documentation for this project.

## Contents

- `architecture.md` - System architecture and design decisions
- `constitution.md` - Core principles and guidelines for this project
- `how-it-works.md` - High-level explanation of how the application works

## Maintaining Documentation

Keep these documents up to date as the project evolves. They serve as the source of truth for understanding the system.
```

**`work/todo.md`** - Master checklist of all stories:
```markdown
# Work Todo

This is the master checklist of all stories to be implemented, organized in priority order.

## Format

- [ ] Epic Name / Feature Name / Story Name (work/epic-dir/feature-dir/story-file.md)

## Todo List

<!-- Add stories here as they are created -->
```

**`scripts/README.md`** - Script directory overview:
```markdown
# Scripts

This directory contains scripts for running the application and development tools.

## Contents

- Execution scripts for the application
- AI agent runner scripts
- Build and deployment scripts
- Development utilities

## Usage

Document each script's purpose and usage here.
```

### 3. Set Up Work Directory Structure

The `work/` directory uses the following organization pattern:

```
work/
├── todo.md                      # Master story checklist
├── [epic-name]/                # Epic directory
│   └── [feature-name]/         # Feature directory
│       ├── story-1.md          # Individual story files
│       ├── story-2.md
│       └── ...
└── [another-epic]/
    └── [another-feature]/
        └── story-1.md
```

### 4. Create Example Epic Structure (Optional)

To demonstrate the structure, you can optionally create an example:

```bash
mkdir -p work/example-epic/example-feature
```

Then create `work/example-epic/example-feature/example-story.md`:
```markdown
# Story: [Story Name]

**Epic:** Example Epic
**Feature:** Example Feature

## Description

[What needs to be built]

## Acceptance Criteria

- [ ] Criterion 1
- [ ] Criterion 2
- [ ] Criterion 3

## Technical Notes

[Implementation details, considerations, dependencies]

## Testing

[How to test this story]
```

### 5. Confirm Completion

After creating the structure, verify all directories and initial files exist:
- `docs/` with README.md
- `scripts/` with README.md
- `work/` with todo.md
- Proper nested structure for epics/features/stories (if examples created)

Report back to the user that the project scaffold has been created successfully.
