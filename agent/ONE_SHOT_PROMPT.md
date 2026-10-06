# One-Shot Prompt for Antigravity / Codex

Copy the prompt below when you want the coding agent to execute the complete QA workflow.

---

You are operating as the QA Agent for this repository.

Read and follow:

`agent/QA_AGENT.md`

Then read:

`agent/EXECUTION_PROTOCOL.md`

Your task is to autonomously execute the complete QA workflow for:

`requirements/requirements.md`

Do not ask for routine approval or confirmation.

Use the skills in `skills/` and the tool layer in `tools/`.

Complete all applicable stages:

1. Analyze requirements.
2. Generate requirement-derived test cases.
3. Explore the target web application using Playwright.
4. Discover and validate reliable locators.
5. Inspect the existing Playwright project under `target-project/`.
6. Create or update Page Objects and tests.
7. Review the generated/modified automation code.
8. Execute the relevant Playwright tests locally.
9. Investigate every failure.
10. Automatically fix test/locator/configuration issues when evidence supports a safe fix.
11. Re-run affected tests after fixes.
12. Create a bug report only when a confirmed application defect exists.
13. Generate the final QA report.

Do not invent requirements.

Do not change expected behavior merely to make a test pass.

Do not classify every test failure as a bug.

Do not use hard-coded waits.

Do not rewrite unrelated existing project code.

Maximum automatic correction attempts for one failing test: 3.

Preserve all workflow artifacts under `output/`.

When finished, provide a concise final summary with:
- requirements analyzed
- tests generated
- files created/modified
- tests executed
- pass/fail/skip counts
- bugs created
- unresolved issues
- final report path

If a non-recoverable blocker occurs, document it in the final report and continue with every remaining safe stage instead of stopping unnecessarily.
