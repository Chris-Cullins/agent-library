# Code Review Prompt

Please perform a thorough code review of the changes.

## Review Focus Areas

### 1. Code Quality
- Is the code readable and maintainable?
- Are there any code smells or anti-patterns?
- Does it follow the project's coding standards and conventions?
- Are variable and function names clear and descriptive?

### 2. Functionality
- Does the implementation match the requirements?
- Are edge cases handled properly?
- Is error handling comprehensive and appropriate?
- Are there any logical errors or bugs?

### 3. Performance
- Are there any obvious performance issues?
- Could any operations be optimized?
- Are resources (memory, connections, etc.) managed properly?

### 4. Security
- Are there any security vulnerabilities (SQL injection, XSS, authentication issues)?
- Is user input properly validated and sanitized?
- Are secrets and sensitive data handled securely?
- Are dependencies up to date and secure?

### 5. Testing
- Are there adequate tests for the new/modified code?
- Do the tests cover edge cases and error scenarios?
- Are the tests clear and maintainable?

### 6. Documentation
- Is the code properly commented where necessary?
- Are complex algorithms or business logic explained?
- Is API documentation up to date?
- Are README or other docs updated if needed?

### 7. Architecture
- Does this fit well with the overall architecture?
- Are there any concerning coupling or cohesion issues?
- Could this be structured better?

## Output Format

Provide feedback in the following format:

**Summary:** Brief overview of the changes

**Strengths:** What's done well

**Issues:** Problems that must be fixed (blocking)

**Suggestions:** Improvements to consider (non-blocking)

**Security Concerns:** Any security-related findings

**Verdict:** APPROVE / REQUEST CHANGES / COMMENT
