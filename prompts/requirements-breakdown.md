# Requirements Breakdown Prompt

Break down a "how it works" or "how it should work" document into actionable epics, features, and stories.

## Process Overview

This is an iterative process:
1. Read the how-it-works document
2. Identify epics (large bodies of work)
3. Break epics into features (specific functionality)
4. Break features into stories (implementable tasks)
5. Review and refine
6. Iterate until you have a complete, detailed plan

## Step 1: Read and Understand

Read the how-it-works document thoroughly:
- Understand all functional requirements
- Note user flows and business rules
- Identify data requirements
- Understand constraints and success criteria
- Note any open questions

Ask clarifying questions if anything is unclear.

## Step 2: Identify Epics

Epics are large bodies of work that group related functionality.

### Guidelines for Epics
- Each epic should represent a major capability or area of functionality
- Epics should be large enough to warrant multiple features
- Epics should align with user-facing value or business goals
- Typically 2-8 epics per project, depending on size

### Epic Template
For each epic, document:
```markdown
# Epic: [Epic Name]

## Description
[High-level description of what this epic delivers]

## Goals
- [Goal 1]
- [Goal 2]

## Value
[What value this provides to users/business]

## Scope
**In scope:**
- [Item 1]
- [Item 2]

**Out of scope:**
- [Item 1]
- [Item 2]

## Dependencies
- [Dependency 1]
- [Dependency 2]

## Success Metrics
- [Metric 1]
- [Metric 2]
```

## Step 3: Break Epics into Features

Features are specific pieces of functionality within an epic.

### Guidelines for Features
- Each feature should deliver a complete, testable piece of functionality
- Features should be sized to take days/weeks, not months
- Features should have clear acceptance criteria
- Typically 3-10 features per epic

### Feature Template
For each feature, document:
```markdown
# Feature: [Feature Name]

**Epic:** [Parent Epic Name]

## Description
[What this feature does and why it's needed]

## User Story
As a [user type], I want to [action] so that [benefit].

## Functional Requirements
1. [Requirement 1]
2. [Requirement 2]
3. [Requirement 3]

## Acceptance Criteria
- [ ] [Criterion 1]
- [ ] [Criterion 2]
- [ ] [Criterion 3]

## Technical Considerations
- [Consideration 1]
- [Consideration 2]

## Dependencies
- [Dependency 1]
- [Dependency 2]

## Estimated Effort
[Small / Medium / Large] or [Story points]
```

## Step 4: Break Features into Stories

Stories are individual, implementable tasks.

### Guidelines for Stories
- Each story should be completable in 1-3 days
- Stories should have clear, testable acceptance criteria
- Stories should be independent when possible
- Stories should deliver incremental value
- Typically 2-8 stories per feature

### Story Template
For each story, create a file: `work/[epic-dir]/[feature-dir]/[story-name].md`

```markdown
# Story: [Story Name]

**Epic:** [Epic Name]
**Feature:** [Feature Name]

## Description
[Detailed description of what needs to be built]

## Acceptance Criteria
- [ ] [Specific, testable criterion 1]
- [ ] [Specific, testable criterion 2]
- [ ] [Specific, testable criterion 3]

## Technical Notes
- [Implementation detail 1]
- [Implementation detail 2]
- [API endpoints or data structures needed]
- [Libraries or tools to use]

## Testing Requirements
- [Test type 1: what to test]
- [Test type 2: what to test]
- Edge cases to cover

## Dependencies
- [Story or component this depends on]
- [External dependency]

## Estimated Effort
[Story points / Hours / Days]

## Notes
[Any additional context, considerations, or open questions]
```

## Step 5: Create Directory Structure

Organize the breakdown in the file system:

```bash
# Create epic directory
mkdir -p work/[epic-name-kebab-case]

# Create feature directory within epic
mkdir -p work/[epic-name]/[feature-name-kebab-case]

# Create story files within feature
# work/[epic-name]/[feature-name]/story-1.md
# work/[epic-name]/[feature-name]/story-2.md
```

## Step 6: Update work/todo.md

Add all stories to the master checklist in priority order:

```markdown
# Work Todo

## Format
- [ ] Epic Name / Feature Name / Story Name (path/to/story.md)

## Todo List

- [ ] User Authentication / Login Feature / Implement Login Form (work/user-auth/login/login-form.md)
- [ ] User Authentication / Login Feature / Add JWT Auth (work/user-auth/login/jwt-auth.md)
- [ ] User Authentication / Registration / Signup Form (work/user-auth/registration/signup-form.md)
...
```

## Step 7: Iterate and Refine

Review the breakdown and refine:

### Check Epic Level
- [ ] Do epics represent major capabilities?
- [ ] Are epics roughly similar in size?
- [ ] Does each epic deliver clear value?
- [ ] Are dependencies between epics identified?

### Check Feature Level
- [ ] Are features specific and well-defined?
- [ ] Do features have clear acceptance criteria?
- [ ] Are features sized appropriately (days/weeks)?
- [ ] Are feature dependencies clear?

### Check Story Level
- [ ] Can each story be completed in 1-3 days?
- [ ] Are acceptance criteria specific and testable?
- [ ] Are stories as independent as possible?
- [ ] Do stories include technical implementation details?

### Adjust as Needed
- Split large features/stories into smaller ones
- Combine small stories if they're too granular
- Reorder based on dependencies
- Add missing stories discovered during review
- Clarify vague acceptance criteria

## Step 8: Validate Completeness

Ensure the breakdown covers everything from the how-it-works document:

- [ ] All functional requirements are covered
- [ ] All user flows are represented
- [ ] All business rules are accounted for
- [ ] Data requirements are included
- [ ] Success criteria can be met
- [ ] Nothing from the original document is missing

## Step 9: Prioritize

Order stories in work/todo.md by:
1. **Dependencies** - What must be done first?
2. **Risk** - What has the most uncertainty?
3. **Value** - What delivers the most user/business value?
4. **Foundation** - What do other things build upon?

Common prioritization approach:
1. Foundational/infrastructure stories
2. Core functionality (highest value)
3. Supporting features
4. Nice-to-have features
5. Polish and optimization

## Iteration Tips

### First Pass (Quick)
- High-level epic identification
- Major features outlined
- Rough story breakdown
- Get the big picture

### Second Pass (Detailed)
- Refine epic descriptions
- Detailed feature acceptance criteria
- Complete story breakdown with technical notes
- Identify all dependencies

### Third Pass (Validation)
- Review with stakeholders
- Verify nothing is missing
- Ensure sizing is appropriate
- Confirm priority order

### Ongoing Iteration
As you implement:
- Discover new stories needed
- Split stories that are too large
- Adjust based on learnings
- Update estimates and priorities

## Output Checklist

After completing the breakdown, you should have:

- [ ] Epic documents created
- [ ] Feature documents created
- [ ] Story files created in work/[epic]/[feature]/ structure
- [ ] All stories added to work/todo.md in priority order
- [ ] Dependencies identified and documented
- [ ] Acceptance criteria are specific and testable
- [ ] Estimates are provided
- [ ] Technical notes are included
- [ ] The breakdown covers all requirements from the how-it-works doc
- [ ] The plan is reviewed and refined

## Common Pitfalls to Avoid

1. **Stories too large** - If a story takes more than 3 days, split it
2. **Vague acceptance criteria** - Be specific and testable
3. **Missing dependencies** - Identify what must be done first
4. **No technical detail** - Stories need enough detail to implement
5. **Skipping iteration** - First pass is never perfect, refine it
6. **Forgetting edge cases** - Consider error states and edge cases
7. **No prioritization** - Order matters, especially for dependencies

## Example

See `examples/requirements-breakdown-example.md` for a complete example of breaking down a how-it-works document into epics, features, and stories.
