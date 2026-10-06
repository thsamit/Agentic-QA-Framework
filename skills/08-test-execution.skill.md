# Skill 08 — Test Execution

## Objective

Execute relevant Playwright tests locally and collect reliable evidence.

## Workflow

1. Confirm dependencies are available.
2. Confirm the application/base URL.
3. Run the smallest relevant test scope first.
4. If successful, execute the complete relevant suite.
5. Capture Playwright results.
6. Preserve screenshots/traces for useful failures.
7. Record exact command and result.

## Rules

- Do not claim a test passed without executing it.
- Do not hide failures.
- Do not repeatedly rerun a test without a reason.
- Do not change assertions simply to make tests pass.
- Do not increase timeouts as a blind response to failures.

## Retry Guidance

A retry can help determine whether a failure is transient, but retries do not prove that a product defect exists.

Use a maximum of 3 automatic correction attempts per test.

## Output

Create:

- `output/execution/execution-summary.md`
- `output/execution/execution-summary.json`

Record:
- command
- timestamp
- total
- passed
- failed
- skipped
- duration
- failure artifact paths
