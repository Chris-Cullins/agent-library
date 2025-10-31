# Bug Fix Prompt

Fix the reported bug following a systematic debugging process.

## Bug Fix Process

### 1. Understand the Bug
- Read the bug report thoroughly
- Identify the expected vs actual behavior
- Note reproduction steps
- Check for error messages or stack traces
- Determine severity and scope of impact

### 2. Reproduce the Bug
- Follow the reproduction steps
- Verify you can consistently reproduce the issue
- Note any additional details discovered
- If unable to reproduce, gather more information

### 3. Investigate Root Cause
- Examine the relevant code paths
- Check recent changes that might have introduced the bug
- Review logs and error messages
- Use debugging tools if needed
- Test hypotheses about what's causing the issue
- Identify the actual root cause (not just symptoms)

### 4. Plan the Fix
- Determine the minimal change needed to fix the root cause
- Consider side effects and edge cases
- Ensure the fix doesn't introduce new issues
- Think about how to prevent similar bugs in the future

### 5. Implement the Fix
- Make focused changes that address the root cause
- Avoid scope creep (fix only the bug, not other issues)
- Add defensive programming where appropriate
- Improve error messages if they were unclear

### 6. Test Thoroughly
- Verify the bug is fixed using reproduction steps
- Test edge cases and related functionality
- Run existing tests to ensure no regressions
- Add new tests to prevent regression of this bug
- Test in different scenarios/environments if applicable

### 7. Document
- Add code comments explaining the fix if non-obvious
- Update documentation if the bug revealed incorrect docs
- Note the root cause in commit message
- Add test descriptions that reference the bug

### 8. Prevent Recurrence
Consider:
- Are there similar bugs elsewhere in the codebase?
- Should we add validation or error handling?
- Are there process improvements needed?
- Should we add monitoring or logging?

## Commit Message Format

```
Fix: [Brief description of the bug]

Root cause: [What was actually causing the bug]
Solution: [How the fix addresses the root cause]
Testing: [How it was verified]

Fixes #[bug-id]
```

## Checklist Before Completion

- [ ] Bug is reproducibly fixed
- [ ] Root cause is understood and addressed
- [ ] No regressions introduced
- [ ] Tests added to prevent regression
- [ ] Code is clean and follows standards
- [ ] Documentation updated if needed
- [ ] Related bugs checked for similar issues
