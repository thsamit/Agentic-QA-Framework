# Skill 09 — Failure Analysis and Bug Reporting

## Objective

Determine the actual cause of Playwright failures and create bug reports only for confirmed application defects.

## Failure Classification

Classify each failure as one of:

- Application Defect
- Test Defect
- Locator Defect
- Environment/Network
- Timing/Flakiness
- Requirement Ambiguity
- Dependency/Configuration
- Other

## Investigation Order

1. Read the failed test.
2. Read the relevant Page Object.
3. Read the assertion error.
4. Inspect screenshot.
5. Inspect trace when available.
6. Inspect current application state.
7. Reproduce the behavior.
8. Compare actual behavior with the requirement.
9. Determine root cause.

## Application Defect Criteria

A failure should be classified as an application defect only when:

- the requirement clearly defines expected behavior,
- the test correctly represents that requirement,
- the application is reachable,
- the test setup is valid,
- the locator/action is valid,
- and the observed application behavior differs from the expected behavior.

## Test/Locator Defect

If the failure is caused by incorrect generated automation:

1. Fix the test/Page Object.
2. Review the change.
3. Re-run the test.
4. Do not create a bug report.

## Environment Failure

Examples:
- DNS/network outage
- application unavailable
- missing credential
- infrastructure failure

Do not create a product bug unless evidence shows the application itself is responsible.

## Flakiness

If the test passes/fails inconsistently:

- reproduce
- inspect timing/state
- determine whether the application or automation is responsible
- avoid masking the problem with arbitrary waits

## Bug Creation

When a confirmed application defect exists:

1. Read `templates/bug-report.md`.
2. Fill every applicable field.
3. Preserve the exact requirement wording.
4. Include test case and requirement IDs.
5. Include actual evidence.
6. Include error/stack trace.
7. Include screenshot/trace paths.
8. Explain why the issue is a product defect.
9. Assign severity based on user/business impact, not merely test failure.

Save to:

`output/bugs/BUG-{TIMESTAMP}.md`

## Security

Never place passwords, tokens, cookies, or secrets into bug reports.

Mask sensitive values in logs and evidence where necessary.

## Output

Create:

`output/failure-analysis/failure-analysis.md`

and:

`output/failure-analysis/failure-analysis.json`
