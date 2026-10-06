# Skill 01 — Requirement Analysis

## Objective

Convert the provided Markdown requirements into a precise, testable QA understanding without inventing product behavior.

## Responsibilities

1. Identify application, module, feature, URL, credentials, and constraints.
2. Extract explicit functional requirements.
3. Assign/retain stable requirement IDs.
4. Identify explicit expected results.
5. Identify required test data.
6. Identify ambiguities and missing information.
7. Separate explicit requirements from QA recommendations.

## Rules

- Never invent acceptance criteria.
- Never silently add product behavior.
- Preserve exact expected messages when provided.
- Preserve exact URLs/paths when provided.
- Treat recommendations separately from requirements.
- Identify duplicate or conflicting requirements.
- Prefer concise, testable statements.

## Output

Produce:

### analysis.md

Include:
- Application under test
- Module/feature
- Base URL
- Test data
- Requirement list
- Requirement dependencies
- Ambiguities
- Coverage considerations
- Recommended additional scenarios

### analysis.json

Use the structure:

```json
{
  "application": "",
  "baseUrl": "",
  "module": "",
  "feature": "",
  "requirements": [],
  "testData": [],
  "ambiguities": [],
  "recommendations": []
}
```
