# Requirements Breakdown Example

This example shows the complete workflow from a "how it works" document to epics, features, and stories.

## Starting Point: how-it-works.md

```markdown
# How It Works: Task Management System

## Overview

**What:** A simple task management system for individuals and small teams

**Why:** Help users organize their work and track progress on tasks

**Who:** Individual knowledge workers and small teams (2-10 people)

## Functional Requirements

### Task Management
**What users can do:** Create, edit, complete, and delete tasks

**How it should work:**
1. User clicks "New Task" button
2. User enters task title and optional description
3. User can set due date, priority, and tags
4. Task appears in task list
5. User can mark task as complete
6. User can edit or delete tasks

**Expected behavior:**
- Tasks are sorted by due date by default
- Completed tasks are visually distinguished
- Overdue tasks are highlighted
- User can filter by tags or status

### Collaboration
**What users can do:** Share tasks and assign them to team members

**How it should work:**
1. User can create a team
2. User can invite team members via email
3. User can assign tasks to team members
4. Assigned members receive notifications
5. Team members can comment on tasks

### Organization
**What users can do:** Organize tasks into projects

**How it should work:**
1. User creates projects
2. User adds tasks to projects
3. User can view all tasks in a project
4. User can set project deadlines
5. Projects show completion progress

## Success Criteria

- [ ] Users can manage personal tasks efficiently
- [ ] Teams can collaborate on shared tasks
- [ ] Tasks are organized into meaningful projects
- [ ] System is fast and responsive
- [ ] Data is never lost
```

## Step 1: Identify Epics

Breaking down the requirements, we identify these epics:

1. **Task Management** - Core task CRUD operations
2. **Team Collaboration** - Team features and task assignment
3. **Project Organization** - Organizing tasks into projects

## Step 2: Epic Breakdown

### Epic: Task Management

```markdown
# Epic: Task Management

## Description
Provide core task management capabilities including creating, editing, completing,
and organizing personal tasks.

## Goals
- Users can efficiently manage personal tasks
- Tasks can be filtered, sorted, and searched
- Task list is fast and responsive

## Value
This is the foundation of the application - without solid task management,
nothing else matters.

## Scope
**In scope:**
- Create, read, update, delete tasks
- Task properties (title, description, due date, priority, tags)
- Filtering and sorting
- Mark tasks as complete

**Out of scope:**
- Team features (separate epic)
- Projects (separate epic)
- Mobile apps (future consideration)

## Dependencies
- None (this is the foundation)

## Success Metrics
- User can create a task in < 3 seconds
- Task list loads in < 500ms
- Users successfully complete tasks regularly
```

## Step 3: Break Epic into Features

### Features for Task Management Epic

#### Feature 1: Basic Task CRUD
```markdown
# Feature: Basic Task CRUD

**Epic:** Task Management

## Description
Allow users to create, view, edit, and delete individual tasks.

## User Story
As a user, I want to create and manage tasks so that I can keep track
of things I need to do.

## Functional Requirements
1. Create task with title and description
2. View task details
3. Edit task information
4. Delete tasks
5. Mark tasks as complete/incomplete

## Acceptance Criteria
- [ ] User can create a new task with title (required) and description (optional)
- [ ] User can view full task details
- [ ] User can edit any task field
- [ ] User can delete a task with confirmation
- [ ] User can toggle task completion status
- [ ] All operations reflect immediately in UI

## Technical Considerations
- Use REST API for task operations
- Optimistic UI updates
- Backend validation
- Database schema for tasks table

## Dependencies
- None

## Estimated Effort
Large (5-8 story points)
```

#### Feature 2: Task Properties
```markdown
# Feature: Task Properties

**Epic:** Task Management

## Description
Add rich properties to tasks including due dates, priority levels, and tags.

## User Story
As a user, I want to add metadata to my tasks so that I can prioritize
and organize my work.

## Functional Requirements
1. Set task due date
2. Set task priority (High, Medium, Low)
3. Add tags to tasks
4. View tasks with their properties

## Acceptance Criteria
- [ ] User can set/edit due date using date picker
- [ ] User can select priority level
- [ ] User can create and assign tags
- [ ] Tags are reusable across tasks
- [ ] Task list displays properties clearly
- [ ] Overdue tasks are visually highlighted

## Technical Considerations
- Date picker component
- Tag autocomplete
- Database schema updates for new fields
- Indexing for query performance

## Dependencies
- Basic Task CRUD feature

## Estimated Effort
Medium (3-5 story points)
```

#### Feature 3: Task Filtering and Sorting
```markdown
# Feature: Task Filtering and Sorting

**Epic:** Task Management

## Description
Allow users to filter and sort their task list to find relevant tasks quickly.

## User Story
As a user, I want to filter and sort my tasks so that I can focus on
what's most important.

## Functional Requirements
1. Sort by due date, priority, or creation date
2. Filter by completion status
3. Filter by tags
4. Filter by priority
5. Search tasks by title/description

## Acceptance Criteria
- [ ] User can toggle sort order
- [ ] User can filter by status (all, active, completed)
- [ ] User can filter by one or more tags
- [ ] User can filter by priority
- [ ] Filters can be combined
- [ ] Search filters results in real-time
- [ ] Filters persist across sessions

## Technical Considerations
- Query optimization for filters
- URL params for sharable filtered views
- Local storage for filter preferences
- Debounced search input

## Dependencies
- Basic Task CRUD feature
- Task Properties feature

## Estimated Effort
Medium (3-5 story points)
```

## Step 4: Break Features into Stories

### Stories for "Basic Task CRUD" Feature

#### Story 1: Create Task Backend API

```markdown
# Story: Create Task Backend API

**Epic:** Task Management
**Feature:** Basic Task CRUD

## Description
Implement the backend API endpoint for creating new tasks.

## Acceptance Criteria
- [ ] POST /api/tasks endpoint exists
- [ ] Accepts title (required, max 200 chars) and description (optional, max 2000 chars)
- [ ] Returns created task with generated ID and timestamp
- [ ] Returns 400 error for invalid input
- [ ] Returns 401 for unauthenticated requests
- [ ] Task is persisted to database
- [ ] API is documented in OpenAPI spec

## Technical Notes
- Use Express.js router
- Validate with Joi or Zod
- PostgreSQL tasks table schema:
  ```sql
  CREATE TABLE tasks (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    user_id UUID NOT NULL REFERENCES users(id),
    title VARCHAR(200) NOT NULL,
    description TEXT,
    completed BOOLEAN DEFAULT FALSE,
    created_at TIMESTAMP DEFAULT NOW(),
    updated_at TIMESTAMP DEFAULT NOW()
  );
  ```
- Add indexes on user_id and created_at

## Testing Requirements
- Unit tests for validation logic
- Integration test for successful creation
- Integration test for validation errors
- Integration test for authentication

## Dependencies
- Database migration system setup
- Authentication middleware

## Estimated Effort
2 story points (~1 day)
```

#### Story 2: Create Task UI Component

```markdown
# Story: Create Task UI Component

**Epic:** Task Management
**Feature:** Basic Task CRUD

## Description
Build the UI component for creating a new task.

## Acceptance Criteria
- [ ] "New Task" button visible in task list header
- [ ] Clicking button opens modal/form
- [ ] Form has title field (required) and description field (optional)
- [ ] Form validates title is not empty
- [ ] Form shows error messages for invalid input
- [ ] Submit button disabled while saving
- [ ] Success: form closes and new task appears in list
- [ ] Error: error message displayed, form stays open
- [ ] Escape key closes form
- [ ] Clicking outside modal closes form

## Technical Notes
- Use React with hooks
- Form component with local state
- Call POST /api/tasks endpoint
- Optimistic UI update
- Toast notification on success/error
- Accessibility: focus management, ARIA labels

## Testing Requirements
- Component unit tests
- Form validation tests
- API integration tests
- Accessibility tests with jest-axe
- E2E test for complete creation flow

## Dependencies
- Create Task Backend API story

## Estimated Effort
2 story points (~1 day)
```

#### Story 3: View Task Details

```markdown
# Story: View Task Details

**Epic:** Task Management
**Feature:** Basic Task CRUD

## Description
Allow users to view full details of a task.

## Acceptance Criteria
- [ ] Clicking task in list opens detail view
- [ ] Detail view shows title, description, created date
- [ ] Detail view has edit and delete buttons
- [ ] Detail view can be closed
- [ ] URL updates when viewing task (deep linkable)
- [ ] Loading state shown while fetching
- [ ] Error message if task not found

## Technical Notes
- GET /api/tasks/:id endpoint
- React modal or side panel component
- React Router for deep linking
- Error boundary for error states

## Testing Requirements
- Component tests
- API integration tests
- E2E test for viewing task
- Test error states

## Dependencies
- Create Task Backend API
- Create Task UI Component

## Estimated Effort
1 story point (~0.5 day)
```

#### Story 4: Edit Task

```markdown
# Story: Edit Task

**Epic:** Task Management
**Feature:** Basic Task CRUD

## Description
Allow users to edit existing tasks.

## Acceptance Criteria
- [ ] Edit button in task detail view opens edit form
- [ ] Edit form pre-populated with current values
- [ ] User can modify title and description
- [ ] Save button updates task
- [ ] Cancel button discards changes
- [ ] Validation same as create
- [ ] Optimistic UI update
- [ ] Success confirmation shown
- [ ] Changes reflected immediately in task list

## Technical Notes
- PUT /api/tasks/:id endpoint
- Reuse task form component from creation
- Optimistic updates with rollback on error
- Update updated_at timestamp on backend

## Testing Requirements
- Backend tests for update endpoint
- Component tests for edit form
- Integration tests
- E2E test for edit flow

## Dependencies
- Create Task Backend API
- Create Task UI Component
- View Task Details

## Estimated Effort
1.5 story points (~1 day)
```

#### Story 5: Delete Task

```markdown
# Story: Delete Task

**Epic:** Task Management
**Feature:** Basic Task CRUD

## Description
Allow users to delete tasks with confirmation.

## Acceptance Criteria
- [ ] Delete button in task detail view
- [ ] Clicking delete shows confirmation dialog
- [ ] Confirmation dialog explains action is irreversible
- [ ] Confirming deletes task and closes detail view
- [ ] Task removed from list immediately
- [ ] Canceling keeps task and closes dialog
- [ ] Success notification shown
- [ ] Error notification if delete fails

## Technical Notes
- DELETE /api/tasks/:id endpoint
- Soft delete (add deleted_at column) or hard delete?
- Decide: Soft delete for now, hard delete later via cleanup job
- Confirmation modal component
- Optimistic UI update

## Testing Requirements
- Backend tests for delete endpoint
- Component tests for confirmation dialog
- Integration tests
- E2E test for delete flow

## Dependencies
- Create Task Backend API
- View Task Details

## Estimated Effort
1 story point (~0.5 day)
```

#### Story 6: Toggle Task Completion

```markdown
# Story: Toggle Task Completion

**Epic:** Task Management
**Feature:** Basic Task CRUD

## Description
Allow users to mark tasks as complete or incomplete.

## Acceptance Criteria
- [ ] Checkbox next to each task in list
- [ ] Clicking checkbox toggles completion state
- [ ] Completed tasks have visual styling (strikethrough, different color)
- [ ] Change reflects immediately
- [ ] Checkbox state matches task completion status
- [ ] Works from both list view and detail view

## Technical Notes
- PATCH /api/tasks/:id endpoint for partial updates
- Update completed boolean field
- CSS styling for completed tasks
- Optimistic UI update

## Testing Requirements
- Backend tests for patch endpoint
- Component tests for checkbox
- Integration tests
- E2E test for completion flow
- Test visual styling

## Dependencies
- Create Task Backend API
- Create Task UI Component

## Estimated Effort
1 story point (~0.5 day)
```

## Step 5: Create Directory Structure

```bash
mkdir -p work/task-management/basic-task-crud
mkdir -p work/task-management/task-properties
mkdir -p work/task-management/task-filtering

# Create story files
touch work/task-management/basic-task-crud/create-task-backend-api.md
touch work/task-management/basic-task-crud/create-task-ui-component.md
touch work/task-management/basic-task-crud/view-task-details.md
touch work/task-management/basic-task-crud/edit-task.md
touch work/task-management/basic-task-crud/delete-task.md
touch work/task-management/basic-task-crud/toggle-task-completion.md
```

## Step 6: Update work/todo.md

```markdown
# Work Todo

## Format
- [ ] Epic Name / Feature Name / Story Name (path/to/story.md)

## Todo List

<!-- Task Management Epic - Basic Task CRUD Feature -->
- [ ] Task Management / Basic Task CRUD / Create Task Backend API (work/task-management/basic-task-crud/create-task-backend-api.md)
- [ ] Task Management / Basic Task CRUD / Create Task UI Component (work/task-management/basic-task-crud/create-task-ui-component.md)
- [ ] Task Management / Basic Task CRUD / View Task Details (work/task-management/basic-task-crud/view-task-details.md)
- [ ] Task Management / Basic Task CRUD / Toggle Task Completion (work/task-management/basic-task-crud/toggle-task-completion.md)
- [ ] Task Management / Basic Task CRUD / Edit Task (work/task-management/basic-task-crud/edit-task.md)
- [ ] Task Management / Basic Task CRUD / Delete Task (work/task-management/basic-task-crud/delete-task.md)

<!-- Continue with Task Properties feature, then Task Filtering -->
<!-- Then move to Team Collaboration and Project Organization epics -->
```

## Summary of Breakdown

**From one how-it-works document, we created:**

- **3 Epics:**
  - Task Management
  - Team Collaboration
  - Project Organization

- **9 Features** (3 shown in detail):
  - Basic Task CRUD
  - Task Properties
  - Task Filtering
  - (+ 6 more for other epics)

- **20+ Stories** (6 shown in detail):
  - Create Task Backend API
  - Create Task UI Component
  - View Task Details
  - Edit Task
  - Delete Task
  - Toggle Task Completion
  - (+ ~14 more for all features)

## Iteration Notes

This is a **first pass** breakdown. As we implement, we would:

- Discover missing stories (e.g., "Set up database migrations")
- Split stories that are too large (e.g., "Create Task UI Component" might split into form component and modal container)
- Add infrastructure stories (e.g., "Set up test framework")
- Refine acceptance criteria based on feedback
- Adjust priorities as we learn

This is expected and healthy! The breakdown process is iterative.
