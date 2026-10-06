# Skill 04 — Locator Strategy

## Objective

Select stable, maintainable Playwright locators based on the actual application DOM.

## Preferred Strategy

Use the most reliable strategy available for the specific element.

General preference:

1. `getByRole()`
2. `getByLabel()`
3. `getByPlaceholder()`
4. Stable `data-*` / test attributes
5. Stable CSS attributes
6. Other CSS selectors
7. XPath only when there is no reasonable alternative

## Important

Do not choose a locator based only on the preference order.

Evaluate:
- uniqueness
- stability
- semantic meaning
- resistance to UI changes
- readability
- maintainability

A stable application-specific test attribute can be better than a fragile role/name combination.

## Avoid

- generated class names
- positional selectors when avoidable
- `nth()` unless the position is part of the requirement
- XPath as the default
- selectors based on styling
- long CSS chains
- arbitrary text selectors when a semantic locator exists

## Validation

Every locator used for automation should be validated during web exploration whenever practical.

## Output

The selected locator should be recorded in the discovery artifact so the automation stage does not need to rediscover it unnecessarily.
