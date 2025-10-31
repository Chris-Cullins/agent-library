# Prompt Library

A collection of reusable prompts for common software development tasks.

## Available Prompts

### Planning and Requirements

#### Requirements Breakdown (`requirements-breakdown.md`)
Systematic process for breaking down "how it works" documents into epics, features, and stories. Includes iterative refinement guidance.

**When to use:** When starting a new project or epic, or when you have functional requirements that need to be translated into actionable work items.

#### Plan Refinement (`plan-refinement.md`)
Iterative refinement process for improving and adjusting your project plan based on learnings, feedback, or changed requirements.

**When to use:** During implementation when you discover missing stories, stories are too large/small, priorities change, or requirements evolve.

### Implementation

#### Code Review (`code-review.md`)
Comprehensive code review checklist covering quality, functionality, performance, security, testing, documentation, and architecture.

**When to use:** Before merging code, during PR reviews, or for general code quality checks.

#### Feature Implementation (`feature-implementation.md`)
Structured approach to implementing new features from story files, including planning, implementation, testing, and documentation.

**When to use:** When starting work on a new feature or user story.

#### Bug Fix (`bug-fix.md`)
Systematic debugging process from understanding and reproducing bugs through fixing, testing, and preventing recurrence.

**When to use:** When investigating and fixing reported bugs or issues.

### Documentation

#### Documentation (`documentation.md`)
Guidelines for creating and maintaining various types of documentation including architecture, APIs, READMEs, and code comments.

**When to use:** When creating or updating project documentation.

#### Architecture Design (`architecture-design.md`)
Comprehensive architecture design process covering requirements, component design, data architecture, quality attributes, and trade-offs.

**When to use:** When designing new systems, features, or major refactors.

## How to Use These Prompts

### Option 1: Direct Reference
Copy the prompt content and provide it to an AI agent along with your specific context.

### Option 2: Copy to Project
Copy relevant prompts into your project's documentation for easy access:
```bash
cp prompts/feature-implementation.md /path/to/your/project/.prompts/
```

### Option 3: Reference by Path
Point AI agents directly to these prompts in your agent library:
```
Please follow the feature implementation process in agent-library/prompts/feature-implementation.md
```

## Customizing Prompts

Feel free to customize these prompts for your specific:
- Coding standards
- Technology stack
- Team processes
- Project requirements
- Quality standards

## Creating New Prompts

When creating new prompts, follow this structure:
1. Clear title and purpose
2. Step-by-step process
3. Checklists and criteria
4. Examples or templates
5. Common pitfalls to avoid

## Contributing

Add new prompts for other common development tasks you encounter across multiple projects.
