# AI Agent Context and Guidelines

This document provides context and guidelines for AI agents working on this project.

---

## Generic Agent Guidance

### Working with This Project

#### Directory Structure
This project follows a standard structure:
- **`docs/`** - Architecture, constitution, and system documentation
- **`scripts/`** - Execution and utility scripts
- **`work/`** - Development workflow tracking (epics, features, stories)
  - `work/todo.md` - Master checklist of all stories to implement

#### Work Organization
Features are organized hierarchically:
- **Epics** - Large bodies of work (directory: `work/epic-name/`)
- **Features** - Specific features within epics (directory: `work/epic-name/feature-name/`)
- **Stories** - Individual implementation tasks (files: `work/epic-name/feature-name/story-name.md`)

Always check `work/todo.md` for the prioritized list of stories to work on.

#### Story Files
Each story file contains:
- Description of what needs to be built
- Acceptance criteria (must all be met)
- Technical notes and constraints
- Testing requirements

When implementing a story:
1. Read the story file completely
2. Understand all acceptance criteria
3. Ask clarifying questions if needed
4. Implement following the acceptance criteria
5. Test thoroughly
6. Check off the story in `work/todo.md` when complete

#### Documentation Priority
Before implementing features:
1. Read `docs/constitution.md` - Core principles and standards
2. Read `docs/architecture.md` - System design and structure
3. Read `docs/how-it-works.md` - High-level system overview

These documents are the source of truth for how this project should be built.

#### Code Standards
- Follow the coding conventions defined in `docs/constitution.md`
- Write clean, maintainable code
- Include appropriate error handling
- Add tests for new functionality
- Document complex logic
- No debug code in commits (console.log, print statements, etc.)

#### Testing Requirements
- Write tests for all new functionality
- Ensure existing tests still pass
- Test edge cases and error scenarios
- Include integration tests for complex features
- Verify acceptance criteria are met

#### Git Workflow
- Write clear, descriptive commit messages
- Keep commits focused and logical
- Reference story files in commits
- Don't commit sensitive data or credentials
- Run tests before committing

#### Communication
- Ask questions when requirements are unclear
- Provide updates on progress and blockers
- Explain significant decisions and trade-offs
- Be explicit about what's complete vs in-progress

---

## Project-Specific Context

> **Note:** Customize this section for your specific project.

### Project Overview

**Name:** [Your Project Name]

**Description:** [Brief description of what this project does]

**Primary Technologies:** [e.g., Node.js, TypeScript, React, PostgreSQL]

**Target Users:** [Who uses this application]

### Project Goals and Principles

[What are the main goals of this project?]

Key principles:
- [Principle 1]
- [Principle 2]
- [Principle 3]

### Architecture Overview

[High-level architecture description - reference docs/architecture.md for details]

Key components:
- **[Component 1]:** [Brief description]
- **[Component 2]:** [Brief description]
- **[Component 3]:** [Brief description]

### Technology Stack

**Backend:**
- [Technology and version]
- [Technology and version]

**Frontend:**
- [Technology and version]
- [Technology and version]

**Database:**
- [Database and version]

**Infrastructure:**
- [Hosting/deployment platform]
- [Other infrastructure]

### Development Environment

**Prerequisites:**
- [Prerequisite 1]
- [Prerequisite 2]

**Setup:**
```bash
# [Setup commands]
```

**Running the Application:**
```bash
# [Run commands]
```

**Running Tests:**
```bash
# [Test commands]
```

### Important Patterns and Conventions

**File Organization:**
- [Pattern 1]
- [Pattern 2]

**Naming Conventions:**
- [Convention 1]
- [Convention 2]

**Code Patterns:**
- [Pattern 1]
- [Pattern 2]

### Common Tasks

**Adding a New Feature:**
1. [Step 1]
2. [Step 2]
3. [Step 3]

**Debugging Issues:**
1. [Step 1]
2. [Step 2]
3. [Step 3]

**Deploying:**
1. [Step 1]
2. [Step 2]
3. [Step 3]

### Important Constraints and Considerations

- [Constraint 1]
- [Constraint 2]
- [Constraint 3]

### Known Issues and Workarounds

- **[Issue 1]:** [Description and workaround]
- **[Issue 2]:** [Description and workaround]

### External Dependencies and Integrations

- **[Service/API 1]:** [Purpose and documentation link]
- **[Service/API 2]:** [Purpose and documentation link]

### Security Considerations

- [Security consideration 1]
- [Security consideration 2]
- [Security consideration 3]

### Performance Considerations

- [Performance consideration 1]
- [Performance consideration 2]

### Questions and Support

**For questions about:**
- Architecture and design decisions → See `docs/architecture.md`
- Coding standards → See `docs/constitution.md`
- How the system works → See `docs/how-it-works.md`
- Current work and priorities → See `work/todo.md`

**Project maintainer:** [Name/contact]

**Documentation:** [Links to additional docs]

---

## Agent-Specific Instructions

### For Implementation Agents
- Always read the story file before starting
- Check acceptance criteria throughout implementation
- Write tests as you implement features
- Update `work/todo.md` as stories are completed
- Reference relevant documentation before making design decisions

### For Review Agents
- Check against coding standards in `docs/constitution.md`
- Verify acceptance criteria are met
- Ensure tests are comprehensive
- Look for security vulnerabilities
- Check for performance issues

### For Documentation Agents
- Keep documentation in sync with implementation
- Update architecture docs when structure changes
- Ensure examples are tested and working
- Use clear, concise language
- Include diagrams where helpful

### For Debugging Agents
- Reproduce the issue first
- Check logs and error messages
- Review recent changes
- Find root cause, not just symptoms
- Add tests to prevent regression

---

## Updates and Maintenance

**Last Updated:** [Date]

**Update Instructions:** Keep this document current as the project evolves. Review and update:
- When architecture changes
- When new patterns are established
- When technology stack changes
- When new constraints are added
- At least quarterly for accuracy
