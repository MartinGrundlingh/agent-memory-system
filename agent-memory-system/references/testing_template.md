# Testing Strategy & Manual QA Scripts

This file documents the project's testing approach, including automated test commands and manual verification scripts.
Use this to run tests correctly and verify complex user flows.

Note: The example entries in this template are generic. Adapt commands, tools, and scripts to match your repository's actual setup.

## 1. Automated Testing Strategy

### Unit Tests
- **Scope**: Individual functions, components, utilities.
- **Framework**: (fill in)
- **Command**: (e.g., `./run-tests --unit`)
- **When to Run**: Before every commit.

### Integration Tests
- **Scope**: API endpoints, database interactions, component integration.
- **Framework**: (fill in)
- **Command**: (e.g., `./run-tests --integration`)
- **When to Run**: Before pushing to main.

### End-to-End (E2E) Tests
- **Scope**: Full user flows (signup, checkout).
- **Framework**: (fill in)
- **Command**: (e.g., `./run-tests --e2e`)
- **When to Run**: Nightly or before release.

## 2. Mocking Strategy

- **External APIs**: Mock third-party services in unit/integration tests.
- **Database**: Use a separate test database; seed before tests, wipe after.
- **Time**: Mock `Date.now()` for time-sensitive logic.

## 3. Manual QA Scripts

Use these scripts to verify features that are hard to automate or require a human check.

### Script: New User Signup Flow
1.  **Navigate** to `/signup`.
2.  **Enter** valid email and password.
3.  **Click** "Sign Up".
4.  **Verify** redirection to `/dashboard`.
5.  **Verify** welcome email received (check local mail catcher).
6.  **Verify** user created in database with `status: active`.

### Script: Admin Order Processing
1.  **Log in** as Admin.
2.  **Navigate** to `/admin/orders`.
3.  **Select** a "Pending" order.
4.  **Click** "Approve".
5.  **Verify** status changes to "Processing".
6.  **Verify** inventory count decreases for items in order.
