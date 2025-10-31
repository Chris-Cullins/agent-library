# Agent Library

A collection of reusable prompts, agent configurations, and project templates for software development across multiple applications.

## Contents

- **`prompts/`** - Library of development prompts (code review, features, bugs, docs, architecture)
- **`agents/`** - AGENTS.md templates for AI agent context
- **`templates/`** - Directory structure scaffolding and setup instructions

## Quick Start

### Setting Up a New Project

1. Copy the AGENTS.md template to your project root:
   ```bash
   cp agents/AGENTS.md /path/to/your/project/
   ```

2. Have an AI agent run the setup prompt to scaffold your directory structure:
   ```bash
   # Show the setup prompt to your agent
   cat templates/SETUP_SCAFFOLD.md
   ```

3. Copy any relevant prompts from `prompts/` into your project for quick access.

## Directory Structure Created by Scaffold

The setup scaffold creates the following structure:

```
your-project/
├── docs/           # Architecture, constitution, how things work
├── scripts/        # Execution scripts, agent runners
└── work/           # Development workflow
    ├── todo.md     # Ordered checklist of all stories
    └── [epics]/    # Epic directories
        └── [features]/  # Feature directories
            └── *.md     # Story files
```

## Using the Prompts

The `prompts/` directory contains templates for common development tasks. Copy and customize them as needed for your specific project context.

## Customizing AGENTS.md

The AGENTS.md template contains both generic guidance and customizable sections. Update the project-specific sections to provide context about your particular application.

## License

MIT
