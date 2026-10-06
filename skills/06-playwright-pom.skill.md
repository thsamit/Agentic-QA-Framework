# Skill 06 — Playwright + TypeScript + POM

## Objective

Implement reliable Playwright automation using TypeScript and Page Object Model.

## Architecture

Page Object responsibilities:
- locators
- page-specific actions
- page-specific state access

Test responsibilities:
- scenario flow
- test data orchestration
- business-level assertions

## Rules

1. Use `@playwright/test`.
2. Use async/await.
3. Use Page Objects.
4. Keep locators inside Page Objects.
5. Prefer stable locators.
6. Do not use hard-coded sleeps.
7. Use Playwright's auto-waiting.
8. Avoid duplicated locators.
9. Keep tests independent.
10. Use meaningful method names.
11. Keep methods focused.
12. Reuse existing fixtures/utilities.
13. Do not introduce unnecessary abstractions.
14. Do not modify unrelated files.
15. Run formatting/type checking when available.

## Assertions

Assertions must validate meaningful behavior.

Prefer:
- URL assertions
- visible state
- expected text
- enabled/disabled state
- user-visible outcomes

Avoid assertions that only prove implementation details unless required.

## Example

```typescript
export class LoginPage {
  constructor(private readonly page: Page) {}

  readonly usernameInput = this.page.getByTestId('username');
  readonly passwordInput = this.page.getByTestId('password');
  readonly loginButton = this.page.getByTestId('login-button');
  readonly errorMessage = this.page.getByTestId('error');

  async login(username: string, password: string): Promise<void> {
    await this.usernameInput.fill(username);
    await this.passwordInput.fill(password);
    await this.loginButton.click();
  }
}
```

Adapt the actual locators to the application's discovered DOM. Do not copy example locators without validation.
