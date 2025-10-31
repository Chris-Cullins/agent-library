# Agent Templates

Templates for AGENTS.md files that provide context to AI agents working on your projects.

## AGENTS.md Template

The `AGENTS.md` template contains two main sections:

### 1. Generic Agent Guidance
Standard guidance that applies to any project using this structure:
- Directory structure explanation
- Work organization (epics/features/stories)
- Story file format and workflow
- Documentation priority
- Code standards
- Testing requirements
- Git workflow
- Communication expectations

This section typically doesn't need customization.

### 2. Project-Specific Context
Customizable sections for your specific project:
- Project overview and goals
- Architecture overview
- Technology stack
- Development environment setup
- Patterns and conventions
- Common tasks
- Important constraints
- Security and performance considerations
- Known issues and workarounds

**You should customize this section** for each project.

## How to Use

### Setup
1. Copy `AGENTS.md` to your project root:
   ```bash
   cp agents/AGENTS.md /path/to/your/project/
   ```

2. Customize the "Project-Specific Context" section:
   - Fill in your project name and description
   - List your technology stack
   - Document your architecture
   - Add your specific patterns and conventions
   - Include setup and run commands
   - Document important constraints

3. Keep it updated as your project evolves

### For AI Agents
AI agents should read `AGENTS.md` before starting work to understand:
- Project structure and organization
- Where to find documentation
- How to work with stories and features
- Project-specific context and constraints
- Coding standards and patterns

### Maintenance
Review and update `AGENTS.md`:
- When architecture changes
- When new patterns are established
- When technology stack changes
- When new constraints are identified
- At least quarterly for accuracy

## Benefits

A well-maintained AGENTS.md file:
- Reduces AI agent confusion and errors
- Ensures consistent implementation
- Provides single source of truth for context
- Makes onboarding new agents faster
- Helps maintain code quality standards
- Documents important project knowledge
