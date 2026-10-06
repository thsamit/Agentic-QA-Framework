# Application Under Test

- Target URL: https://www.saucedemo.com/
- Module: User Authentication
- Feature: Login

# Test Credentials

| User | Password | Purpose |
|---|---|---|
| standard_user | secret_sauce | Valid login |
| problem_user | secret_sauce | Valid login |
| performance_glitch_user | secret_sauce | Valid login |
| locked_out_user | secret_sauce | Locked-out login |

# Functional Requirements

## AUTH-REQ-001 — Login Page

Navigating to `/` displays the login form containing:

- Username field
- Password field
- Login button

## AUTH-REQ-002 — Successful Login

When a user enters:

- Username: `standard_user`
- Password: `secret_sauce`

and clicks Login, the application redirects to:

`/inventory.html`

## AUTH-REQ-003 — Locked Out User

When the user enters:

- Username: `locked_out_user`
- Password: `secret_sauce`

the application displays an error banner containing:

`Epic sadface: Sorry, this user has been locked out.`

## AUTH-REQ-004 — Invalid Credentials

When the user enters an invalid username or password, the application displays an error banner containing:

`Epic sadface: Username and password do not match any user in this service`

## AUTH-REQ-005 — Blank Username

When the login form is submitted without a username, the application displays:

`Epic sadface: Username is required`

# Test Design Notes

The following are requirements-derived scenarios.

Potential additional scenarios may be identified by the agent, but they must be clearly marked as recommendations and must not be presented as explicit product requirements unless supported by this document.
