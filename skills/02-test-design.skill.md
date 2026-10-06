# Skill 02 — Test Design

## Objective

Transform explicit requirements into concise, meaningful functional test cases.

## Rules

1. Every requirement-derived test case must reference one or more requirement IDs.
2. Do not create unnecessary UI/technical tests unless required.
3. Prefer user/business outcomes.
4. Include positive and negative coverage when supported by requirements.
5. Avoid duplicate scenarios.
6. Clearly distinguish requirement-derived tests from recommendations.
7. Test cases must be independently executable where practical.

## Test Case Structure

Each test case must contain:

- Test Case ID
- Requirement ID
- Title
- Test Type
- Preconditions
- Test Data
- Steps
- Expected Result
- Automation Candidate

## ID Format

Use:

`TC-{MODULE}-{NUMBER}`

Example:

`TC-AUTH-001`

## Output

Create:

- `test-cases.md`
- `test-cases.json`

Recommended JSON shape:

```json
{
  "testCases": [
    {
      "id": "TC-AUTH-001",
      "requirementIds": ["AUTH-REQ-001"],
      "title": "",
      "type": "Functional",
      "preconditions": [],
      "testData": [],
      "steps": [],
      "expectedResult": "",
      "automationCandidate": true
    }
  ],
  "recommendations": []
}
```
