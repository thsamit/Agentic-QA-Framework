# Skill 05 — Automation Planning

## Objective

Convert test cases and discovery information into a concrete Playwright/POM implementation plan.

## First Action

Inspect the existing project under `target-project/`.

Determine:
- current directory structure
- existing Page Objects
- existing tests
- fixtures
- utilities
- configuration
- naming conventions
- locator conventions
- TypeScript configuration

## Rules

- Reuse existing components.
- Do not duplicate Page Objects.
- Do not create unnecessary abstraction.
- Keep Page Objects focused on page behavior.
- Keep assertions in tests unless an assertion is inherently page-state behavior.
- Keep test data separate when appropriate.
- Follow existing project conventions.

## Plan Must Identify

- Page Objects to create/update
- test files to create/update
- helper/fixture changes
- locators required
- methods required
- test cases mapped to specs
- expected navigation/assertions

## Output

Create:

`output/automation/automation-plan.md`

and:

`output/automation/automation-plan.json`
