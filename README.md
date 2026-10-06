# Agentic QA Automation Framework

A lightweight, requirement-driven agentic QA framework for web applications using:

- Playwright
- TypeScript
- Page Object Model (POM)
- Markdown requirements
- Markdown/JSON artifacts
- Skill-driven single-agent workflow
- Local test execution

## Goal

The framework should eventually support this workflow:

Requirement
→ Requirement Analysis
→ Test Design
→ Web Exploration
→ Locator Discovery
→ Automation Planning
→ Playwright/POM Code Generation
→ Code Review
→ Test Execution
→ Failure Analysis
→ Bug Report
→ QA Report

The first version deliberately uses one agent with multiple skills instead of multiple specialized agents.

## Repository Structure

```text
agentic-qa/
├── agent/
│   └── QA_AGENT.md
├── requirements/
│   └── requirements.md
├── skills/
│   ├── 01-requirement-analysis.skill.md
│   ├── 02-test-design.skill.md
│   ├── 03-web-exploration.skill.md
│   ├── 04-locator-strategy.skill.md
│   ├── 05-automation-planning.skill.md
│   ├── 06-playwright-pom.skill.md
│   ├── 07-code-review.skill.md
│   ├── 08-test-execution.skill.md
│   └── 09-failure-analysis-and-bug-reporting.skill.md
├── schemas/
│   ├── analysis.schema.json
│   ├── test-cases.schema.json
│   ├── discovery.schema.json
│   ├── automation-plan.schema.json
│   └── failure-analysis.schema.json
├── templates/
│   ├── bug-report.md
│   └── qa-report.md
├── output/
│   ├── analysis/
│   ├── test-cases/
│   ├── discovery/
│   ├── automation/
│   ├── execution/
│   ├── bugs/
│   └── reports/
├── target-project/
│   └── .gitkeep
├── .gitignore
└── package.json
```

## Current Scope

The initial proof of concept targets SauceDemo login.

The agent must:
1. Read the requirements.
2. Analyze and normalize requirements.
3. Generate requirement-derived test cases.
4. Explore the web application with Playwright.
5. Discover and validate locators.
6. Produce an automation plan.
7. Generate Playwright/POM code in `target-project/`.
8. Review generated code.
9. Execute tests locally.
10. Analyze failures.
11. Create bug reports only for confirmed application defects.
12. Produce a final QA report.

## Important Principle

A failed automated test is NOT automatically a product bug.

The agent must classify failures as:
- Application defect
- Test defect
- Locator defect
- Environment/network issue
- Flaky/timing issue
- Requirement ambiguity
- Other

Only confirmed application defects should generate a bug report.

## How to use

Place or replace the application project under:

```text
target-project/
```

Place the feature requirement in:

```text
requirements/requirements.md
```

Then instruct the coding agent to read:

```text
agent/QA_AGENT.md
```

and execute the complete workflow.

## Status

Phase 1 foundation.

The next phase will add the executable orchestration/tooling layer and the autonomous retry/fix loop.

## Phase 2 — Tool Layer and Execution Protocol

Phase 2 adds:

- `config/qa.config.json`
- `.env.example`
- `tools/qa-tools.ts`
- `agent/EXECUTION_PROTOCOL.md`
- `agent/ONE_SHOT_PROMPT.md`

The tool layer provides deterministic local operations for reading files, listing directories, searching the target project, running shell commands, running Playwright, and inspecting Git changes.

### Install

From the framework root:

```bash
npm install
```

### Verify the Tool Layer

```bash
npm run qa:list -- target-project
npm run qa:read -- requirements/requirements.md
npm run qa:search -- target-project Login
npm run qa:diff
```

### Run Playwright

Once `target-project/` contains a Playwright project:

```bash
npm run qa:test
```

Or:

```bash
npm run qa:test -- tests/login.spec.ts
```

### One-Shot Execution

Use the prompt in `agent/ONE_SHOT_PROMPT.md` with Antigravity or Codex.

## Reusing the Framework

The workflow is designed to be reusable across web applications. Normally change:

- `requirements/requirements.md`
- application URL
- test data/credentials
- `target-project/` when an existing automation project is supplied

The skills and workflow should remain reusable.

The framework does not guarantee zero-touch automation for every arbitrary web application. CAPTCHA, MFA/SSO, cross-origin restrictions, inaccessible controls, unusual authentication, native dialogs, third-party integrations, file-system interactions, and environment-specific behavior may require additional application-specific handling.
