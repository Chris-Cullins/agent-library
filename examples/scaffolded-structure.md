# Example Scaffolded Project Structure

This shows what a project looks like after running the setup scaffold.

## Directory Tree

```
your-project/
├── AGENTS.md                    # Copied from agent-library/agents/AGENTS.md
├── docs/
│   ├── README.md               # Documentation overview
│   ├── architecture.md         # System architecture (you create)
│   ├── constitution.md         # Core principles (you create)
│   └── how-it-works.md        # System overview (you create)
├── scripts/
│   ├── README.md               # Script documentation
│   └── [your scripts]          # Execution and utility scripts
└── work/
    ├── todo.md                 # Master story checklist
    ├── user-authentication/    # Example epic
    │   ├── login-feature/      # Example feature
    │   │   ├── implement-login-form.md
    │   │   ├── add-jwt-tokens.md
    │   │   └── password-reset.md
    │   └── registration-feature/
    │       ├── signup-form.md
    │       └── email-verification.md
    └── data-management/
        └── user-profiles/
            ├── create-profile-schema.md
            └── edit-profile-ui.md
```

## Example Files

### work/todo.md

```markdown
# Work Todo

This is the master checklist of all stories to be implemented, organized in priority order.

## Format

- [ ] Epic Name / Feature Name / Story Name (work/epic-dir/feature-dir/story-file.md)

## Todo List

- [ ] User Authentication / Login Feature / Implement Login Form (work/user-authentication/login-feature/implement-login-form.md)
- [ ] User Authentication / Login Feature / Add JWT Tokens (work/user-authentication/login-feature/add-jwt-tokens.md)
- [ ] User Authentication / Registration Feature / Signup Form (work/user-authentication/registration-feature/signup-form.md)
- [ ] User Authentication / Registration Feature / Email Verification (work/user-authentication/registration-feature/email-verification.md)
- [ ] User Authentication / Login Feature / Password Reset (work/user-authentication/login-feature/password-reset.md)
- [ ] Data Management / User Profiles / Create Profile Schema (work/data-management/user-profiles/create-profile-schema.md)
- [ ] Data Management / User Profiles / Edit Profile UI (work/data-management/user-profiles/edit-profile-ui.md)
```

### work/user-authentication/login-feature/implement-login-form.md

```markdown
# Story: Implement Login Form

**Epic:** User Authentication
**Feature:** Login Feature

## Description

Create a login form that allows users to authenticate with email and password. The form should have proper validation, error handling, and a good user experience.

## Acceptance Criteria

- [ ] Login form displays with email and password fields
- [ ] Email field validates proper email format
- [ ] Password field is masked
- [ ] Form shows validation errors for invalid input
- [ ] Form shows authentication errors from backend
- [ ] Loading state is shown while authentication is in progress
- [ ] Successful login redirects to dashboard
- [ ] "Remember me" checkbox persists session
- [ ] "Forgot password" link is visible

## Technical Notes

- Use the existing form component library
- Integrate with the authentication API at `/api/auth/login`
- Store auth token in secure httpOnly cookie
- Follow OWASP best practices for login forms
- Ensure accessibility (ARIA labels, keyboard navigation)

## Testing

- Unit tests for validation logic
- Integration tests for form submission
- E2E test for complete login flow
- Test error scenarios (wrong password, network error)
- Test accessibility with screen reader

## Dependencies

- Authentication API must be implemented first
- Form component library available

## Estimated Effort

3 story points / ~1 day
```

### docs/architecture.md (template)

```markdown
# Architecture

## Overview

[High-level description of your system architecture]

## System Components

### Frontend
[Description of frontend architecture]

### Backend
[Description of backend architecture]

### Database
[Description of data architecture]

### Infrastructure
[Description of hosting and deployment]

## Key Design Decisions

### [Decision 1]
**Decision:** [What was decided]
**Rationale:** [Why this decision was made]
**Alternatives Considered:** [What else was considered]
**Trade-offs:** [Pros and cons]

### [Decision 2]
...

## Data Flow

[Description of how data flows through the system]

## Security Architecture

[Description of security measures and architecture]

## Scalability

[How the system scales]

## Integration Points

[External systems and APIs]
```

### docs/constitution.md (template)

```markdown
# Project Constitution

## Core Principles

1. **[Principle 1]** - [Description]
2. **[Principle 2]** - [Description]
3. **[Principle 3]** - [Description]

## Coding Standards

### General
- [Standard 1]
- [Standard 2]

### Language-Specific
- [Standard 1]
- [Standard 2]

## Code Review Standards

All code must:
- [ ] Follow coding standards
- [ ] Include tests
- [ ] Have clear commit messages
- [ ] Be reviewed by at least one other developer
- [ ] Pass all CI checks

## Quality Standards

### Testing
- Minimum code coverage: [X%]
- All features must have unit tests
- Critical paths must have integration tests

### Performance
- API response time: [threshold]
- Page load time: [threshold]

### Security
- No secrets in code
- All inputs validated
- OWASP top 10 addressed

## Decision-Making Process

[How decisions are made on this project]

## Best Practices

### Git Workflow
[Your git workflow]

### Branch Naming
[Your branch naming conventions]

### Commit Messages
[Your commit message format]

### Documentation
[Documentation requirements]
```

## Workflow Example

1. **Starting a new epic:**
   ```bash
   mkdir -p work/new-epic-name
   ```

2. **Adding a feature:**
   ```bash
   mkdir -p work/new-epic-name/new-feature-name
   ```

3. **Creating a story:**
   - Create story file: `work/epic/feature/story-name.md`
   - Add to `work/todo.md` checklist

4. **Working on a story:**
   - Agent reads story file
   - Implements according to acceptance criteria
   - Writes tests
   - Checks off in `work/todo.md` when complete

5. **Completing work:**
   - All acceptance criteria met
   - Tests passing
   - Documentation updated
   - Story checked off in `work/todo.md`
