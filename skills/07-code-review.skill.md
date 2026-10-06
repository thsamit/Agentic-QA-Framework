# Skill 07 — Code Review

## Objective

Review generated/modified Playwright TypeScript code before execution.

## Review Areas

### Correctness
- Does the test implement the intended requirement?
- Are expected results asserted?
- Are negative scenarios handled correctly?

### POM
- Are locators in Page Objects?
- Are page actions encapsulated?
- Is there unnecessary duplication?

### Locator Quality
- Are locators stable?
- Were discovered locators used?
- Are fragile selectors present?

### Synchronization
- Any hard waits?
- Any unnecessary timeout increases?
- Is Playwright auto-waiting used correctly?

### Maintainability
- Naming
- method size
- duplication
- unnecessary abstractions
- existing project conventions

### TypeScript
- type safety
- unused values
- obvious compiler errors

### Test Isolation
- Can tests run independently?
- Is state handled appropriately?

## Rules

Fix legitimate issues found during review.

Do not perform unrelated refactoring.

## Output

Create:

`output/automation/code-review.md`

Include:
- files reviewed
- findings
- severity
- changes made
- remaining concerns
