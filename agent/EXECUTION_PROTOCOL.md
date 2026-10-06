# Agent Execution Protocol

## Mission

Given a requirement file and a target web application, autonomously complete the QA workflow using the skills and tools in this repository.

## Before Starting

1. Read `agent/QA_AGENT.md`.
2. Read `config/qa.config.json`.
3. Read all applicable skills.
4. Read `requirements/requirements.md`.
5. Inspect `target-project/`.
6. Determine whether `target-project/` is an existing Playwright project or an empty directory.

## Tool Selection

Use the tool layer for deterministic local operations:

- `read` → inspect a file
- `list` → inspect directory contents
- `search` → find existing code/conventions
- `run` → run a shell command when necessary
- `test` → run Playwright tests
- `git-diff` → inspect target-project changes

The agent remains responsible for reasoning and choosing the appropriate operation.

## Required Execution Order

```text
1. Requirement Analysis
2. Test Design
3. Web Exploration
4. Locator Strategy
5. Automation Planning
6. POM/Test Implementation
7. Code Review
8. Test Execution
9. Failure Analysis
10. Bug Reporting
11. Final QA Report
```

Do not skip a stage unless its artifact already exists and is demonstrably current for the current requirement.

## Artifact Checkpoints

After each stage, verify that the expected artifact exists:

```text
output/analysis/analysis.md
output/analysis/analysis.json
output/test-cases/test-cases.md
output/test-cases/test-cases.json
output/discovery/discovery.md
output/discovery/discovery.json
output/automation/automation-plan.md
output/automation/automation-plan.json
output/automation/code-review.md
output/execution/execution-summary.md
output/execution/execution-summary.json
output/failure-analysis/failure-analysis.md
output/failure-analysis/failure-analysis.json
output/reports/qa-report.md
```

## Existing Project Rule

If `target-project/` contains an existing Playwright project:

- inspect it first;
- preserve its architecture;
- reuse existing Page Objects;
- reuse fixtures and utilities;
- reuse configuration;
- do not rewrite unrelated code.

If it is empty:

- create a minimal Playwright TypeScript POM structure;
- create only what is required by the current requirements.

## Web Exploration Rule

Automation must be based on actual application inspection.

For each locator used:
- discover it from the application;
- validate it;
- record it in the discovery artifact.

Do not guess selectors from a requirement.

## Execution Rule

Run the narrowest relevant test first. If successful, run the complete relevant suite.

If a test fails:
1. collect evidence;
2. classify the failure;
3. fix only when it is an automation/tooling issue;
4. re-run;
5. stop automatic correction after 3 attempts for that test.

## Defect Rule

Do not create a bug merely because a test failed. A bug requires evidence that the application violates an explicit requirement.

## No Silent Requirement Changes

Never change product requirements simply to make a test pass.

If a requirement is ambiguous:
- document the ambiguity;
- make the safest reasonable interpretation;
- record the assumption.

## Completion

The final response must include:
- requirements analyzed
- test cases generated
- files created/modified
- tests executed
- pass/fail/skip counts
- failure classifications
- generated bug IDs
- unresolved issues
- final QA report path
