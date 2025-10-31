# Plan Refinement Prompt

Iteratively refine and improve your project plan (epics, features, stories) based on new learnings, feedback, or changed requirements.

## When to Use This Prompt

Use this prompt when:
- You've started implementing and discovered new requirements
- Requirements have changed or been clarified
- You've found stories that are too large or too small
- Dependencies weren't clear in the original breakdown
- You need to adjust priorities
- You've learned something that impacts the plan
- Feedback from stakeholders requires changes

## Refinement Process

### 1. Identify What Needs Refinement

Review your current plan and identify issues:

**Story Level Issues:**
- [ ] Stories taking longer than 3 days
- [ ] Stories with unclear acceptance criteria
- [ ] Stories blocked by unclear dependencies
- [ ] Stories too small (< 1 day of work)
- [ ] Missing stories discovered during implementation
- [ ] Stories with changed requirements

**Feature Level Issues:**
- [ ] Features scope has changed
- [ ] Feature dependencies weren't clear
- [ ] Features sized incorrectly
- [ ] Features need to be split or merged

**Epic Level Issues:**
- [ ] Epic scope too large or too small
- [ ] Epic priorities have changed
- [ ] New epics discovered
- [ ] Epic goals need clarification

**Priority Issues:**
- [ ] Dependencies require reordering
- [ ] Business priorities have shifted
- [ ] Technical risks require earlier attention
- [ ] Order in work/todo.md doesn't reflect reality

### 2. Document Learnings

Before making changes, document what you've learned:

```markdown
## Refinement Notes - [Date]

### What We Learned
- [Learning 1]
- [Learning 2]

### What Changed
- [Change 1]
- [Change 2]

### Impact
- [Impact on timeline]
- [Impact on scope]
- [Impact on architecture]

### Decisions Made
- [Decision 1]: [Rationale]
- [Decision 2]: [Rationale]
```

### 3. Refine Stories

#### Splitting Large Stories

When a story is too large:

1. Identify natural breakpoints
2. Ensure each split story has value
3. Make dependencies explicit
4. Update acceptance criteria for each

**Example:**
```
Before:
- Story: Implement complete user authentication

After:
- Story: Implement login form UI
- Story: Add backend login endpoint
- Story: Add JWT token generation
- Story: Add token validation middleware
- Story: Add session management
```

#### Combining Small Stories

When stories are too granular:

1. Look for stories in the same area
2. Combine if they're done together
3. Keep acceptance criteria from both
4. Ensure combined story is still < 3 days

**Example:**
```
Before:
- Story: Add button styling
- Story: Add button hover state
- Story: Add button disabled state

After:
- Story: Implement button component with all states
```

#### Adding Missing Stories

When you discover missing work:

1. Create the story file
2. Add to work/todo.md in the right priority order
3. Identify dependencies
4. Add acceptance criteria
5. Note why it wasn't in original plan

#### Updating Existing Stories

When requirements change:

1. Update the description
2. Revise acceptance criteria
3. Adjust technical notes
4. Update estimates
5. Document what changed and why

### 4. Refine Features

#### Splitting Features

When a feature is too large:

1. Identify logical groupings of stories
2. Create new feature directories
3. Move stories to appropriate features
4. Update feature documentation
5. Update work/todo.md paths

#### Merging Features

When features overlap or are too small:

1. Combine related features
2. Merge story files into single feature directory
3. Update feature documentation
4. Update work/todo.md paths

#### Adjusting Feature Scope

When scope changes:

1. Update feature description
2. Revise acceptance criteria
3. Add or remove stories
4. Update dependencies
5. Document scope change

### 5. Refine Epics

#### Splitting Epics

When an epic is too large:

1. Identify natural divisions
2. Create new epic directories
3. Move feature directories
4. Update epic documentation
5. Update all story/feature epic references

#### Adjusting Epic Priorities

When priorities change:

1. Reorder stories in work/todo.md
2. Update epic documentation with new priorities
3. Communicate changes to stakeholders
4. Adjust timelines if needed

### 6. Update Documentation

After making refinements:

**Update work/todo.md:**
```markdown
# Work Todo

<!-- Add note about last update -->
**Last Updated:** [Date] - [Brief description of changes]

## Todo List
<!-- Update order and paths as needed -->
```

**Update how-it-works if needed:**
- If requirements changed, update the source document
- Keep it in sync with the refined plan

**Update CHANGELOG (optional):**
```markdown
# Plan Changelog

## [Date] - Refinement
### Added
- [New story/feature added]

### Changed
- [What changed and why]

### Removed
- [What was removed and why]

### Priority Changes
- [What moved up/down and why]
```

### 7. Validate Refinements

Check that refinements are sound:

**Story Level:**
- [ ] All stories are 1-3 days of work
- [ ] Acceptance criteria are clear and testable
- [ ] Dependencies are explicit
- [ ] Technical details are sufficient
- [ ] Stories deliver incremental value

**Feature Level:**
- [ ] Features are cohesive and well-scoped
- [ ] Feature boundaries make sense
- [ ] Dependencies are clear
- [ ] Acceptance criteria are complete

**Epic Level:**
- [ ] Epics represent major capabilities
- [ ] Epic scopes are appropriate
- [ ] Priorities align with business goals
- [ ] Dependencies between epics are clear

**Overall Plan:**
- [ ] work/todo.md reflects current priorities
- [ ] All paths in todo.md are correct
- [ ] Dependencies allow for logical progression
- [ ] Plan is achievable and realistic
- [ ] No work is missing or duplicated

### 8. Communicate Changes

If working with a team or stakeholders:

1. Summarize what changed and why
2. Explain impact on timeline/scope
3. Highlight any new risks or dependencies
4. Get buy-in on changes
5. Update stakeholders on new priorities

## Common Refinement Scenarios

### Scenario 1: Story Too Large During Implementation

**Symptom:** Working on a story for 4+ days

**Solution:**
1. Identify what's been completed
2. Create new story for remaining work
3. Update original story's acceptance criteria to match what's done
4. Mark original as complete
5. Add new story to todo.md
6. Continue with new story

### Scenario 2: Hidden Dependencies Discovered

**Symptom:** Can't start a story because something else needs to be done first

**Solution:**
1. Create story for the dependency
2. Add to work/todo.md before the blocked story
3. Document dependency in both stories
4. Implement dependency first

### Scenario 3: Requirements Changed

**Symptom:** Stakeholder says "actually, we need it to work differently"

**Solution:**
1. Update how-it-works document
2. Identify affected stories/features
3. Update or create new stories
4. Adjust priorities if needed
5. Document the change and rationale

### Scenario 4: Technical Discovery Changes Approach

**Symptom:** Discovered a library/pattern that changes how to implement

**Solution:**
1. Update technical notes in affected stories
2. Split or combine stories if approach changes sizing
3. Update acceptance criteria if needed
4. Document the discovery and decision

### Scenario 5: Priority Shift

**Symptom:** Business needs different features sooner

**Solution:**
1. Reorder work/todo.md
2. Check dependencies allow new order
3. Communicate impact on other work
4. Update stakeholders on timeline changes

## Refinement Best Practices

### Do:
- ✅ Refine continuously as you learn
- ✅ Document why changes were made
- ✅ Keep work/todo.md current
- ✅ Communicate changes to stakeholders
- ✅ Validate refinements before implementing
- ✅ Learn from each refinement

### Don't:
- ❌ Make changes without understanding why
- ❌ Let the plan get out of sync with reality
- ❌ Ignore learnings from implementation
- ❌ Be afraid to split stories mid-implementation
- ❌ Skip updating documentation
- ❌ Refine so often you never implement

## Iteration Frequency

**Continuous (as needed):**
- Adding missing stories
- Splitting stories that are too large
- Updating acceptance criteria

**Daily/Weekly:**
- Reordering work/todo.md based on progress
- Adjusting near-term priorities
- Quick story refinements

**Milestone/Sprint:**
- Feature scope adjustments
- Epic priority changes
- Major replanning
- Comprehensive validation

## Checklist for Refinement Session

Before refinement:
- [ ] Gather feedback and learnings
- [ ] Identify what's not working
- [ ] Understand why changes are needed

During refinement:
- [ ] Make changes systematically
- [ ] Document all changes
- [ ] Maintain consistency (paths, naming, structure)
- [ ] Update all affected files

After refinement:
- [ ] Validate the refined plan
- [ ] Update work/todo.md
- [ ] Communicate changes
- [ ] Commit changes with clear message

## Example Refinement

See `examples/plan-refinement-example.md` for a detailed example of refining a plan based on implementation learnings.
