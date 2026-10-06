# Skill 03 — Web Exploration

## Objective

Explore the actual web application with Playwright before generating automation.

## Core Principle

Do not infer the DOM from requirements.

Inspect the actual application.

## Workflow

1. Read the target URL from the requirements.
2. Open the application with Playwright.
3. Confirm the page loads.
4. Capture page URL and title.
5. Identify interactive elements relevant to the requirements.
6. Inspect accessible roles/names.
7. Inspect labels/placeholders.
8. Inspect stable attributes such as `data-*`.
9. Inspect forms, links, buttons, messages, and navigation.
10. Validate candidate locators by interacting with the application.
11. Explore only pages relevant to the current requirements.

## Locator Discovery

For each required element record:

- semantic purpose
- locator
- locator strategy
- why it is stable
- whether it was validated
- relevant page/state

## Validation

A locator is considered validated only after it successfully identifies the intended element in the application.

If possible, verify:
- count is expected
- element is visible when applicable
- interaction succeeds
- resulting state matches expectations

## Do Not

- Do not blindly scrape the entire website.
- Do not generate selectors without inspection.
- Do not modify the application.
- Do not submit destructive actions.
- Do not use production data unless explicitly authorized.

## Output

Create:

`output/discovery/discovery.md`

and:

`output/discovery/discovery.json`

Recommended JSON shape:

```json
{
  "pages": [
    {
      "name": "Login",
      "url": "/",
      "title": "",
      "elements": [
        {
          "name": "username",
          "locator": "",
          "strategy": "",
          "validated": true,
          "notes": ""
        }
      ]
    }
  ]
}
```
