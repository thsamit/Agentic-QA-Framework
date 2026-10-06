# [BUG]: {Short, descriptive summary}

**Bug ID:** `BUG-{TIMESTAMP}`
**Date Logged:** {YYYY-MM-DD}
**Severity:** {Critical / High / Medium / Low}
**Priority:** {High / Medium / Low}
**Bug Type:** {Functional / UI / Validation / Navigation / Performance / Other}

**Environment:** `{BASE_URL}`
**Browser:** `{BROWSER}`
**OS:** `{OS}`

**Automation Spec:** `{path/to/failed-spec.ts}`
**Test Case ID:** `{TC_ID}`
**Requirement ID:** `{REQ_ID}`

---

## 1. Executive Summary

{Concise explanation of the confirmed application defect.}

## 2. Test Scenario

- **Test Case:** `{TC_ID}`
- **Title:** {Test Case Name}
- **Module:** {Module Name}
- **Requirement:** `{REQ_ID}`

## 3. Preconditions

{Required preconditions.}

## 4. Test Data

{Relevant test data. Do not expose secrets unnecessarily.}

## 5. Steps to Reproduce

1. Navigate to `{BASE_URL}`.
2. {Step 2}
3. {Step 3}
4. {Step 4}

## 6. Expected Result

{Requirement-based expected behavior.}

## 7. Actual Result

{Observed behavior during execution.}

## 8. Failure Evidence

### Playwright Error

```text
{Playwright CLI output or assertion error}
```

### Screenshot

`{path/to/screenshot}`

### Trace

`{path/to/trace.zip}`

## 9. Failure Analysis

**Classification:** {Application Defect / Test Defect / Environment / Flaky / Other}

{Explain why the failure is considered an application defect.}

## 10. Reproducibility

- **Attempts:** {N}
- **Successful Reproductions:** {N}
- **Confidence:** {High / Medium / Low}

## 11. Impact

{User/business impact.}

## 12. Recommended Action

{Concise recommendation for investigation/fix.}
