```markdown
# skills-marketing Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches best practices and conventions for contributing to the `skills-marketing` TypeScript codebase. It covers file organization, code style, commit message formatting, and testing patterns to ensure consistency and maintainability across the project.

## Coding Conventions

### File Naming
- Use **kebab-case** for all file names.
  - Example:  
    ```
    email-campaign.ts
    user-profile.test.ts
    ```

### Import Style
- Use **relative imports** for internal modules.
  - Example:
    ```typescript
    import { sendEmail } from './email-utils';
    ```

### Export Style
- Use **named exports** for all modules.
  - Example:
    ```typescript
    // email-utils.ts
    export function sendEmail() { ... }
    export function validateEmail() { ... }
    ```

### Commit Messages
- Follow the **Conventional Commits** format.
- Use the `feat` prefix for new features.
- Keep commit messages concise (average ~33 characters).
  - Example:
    ```
    feat: add email validation utility
    ```

## Workflows

### Feature Development
**Trigger:** When adding a new feature  
**Command:** `/feature-development`

1. Create a new file using kebab-case.
2. Implement the feature using TypeScript.
3. Use relative imports for dependencies.
4. Export functions or constants using named exports.
5. Write corresponding tests in a `.test.ts` file.
6. Commit changes with a `feat:` prefix in the commit message.

### Testing
**Trigger:** When verifying code functionality  
**Command:** `/run-tests`

1. Write tests in files matching the `*.test.*` pattern.
2. Use the project's preferred (unknown) testing framework.
3. Run the test suite to ensure all tests pass.

## Testing Patterns

- Test files should follow the `*.test.*` naming convention.
  - Example:  
    ```
    email-utils.test.ts
    ```
- Place test files alongside the code they test or in a dedicated test directory.
- Testing framework is not specified; follow existing patterns in the repository.

## Commands
| Command              | Purpose                                  |
|----------------------|------------------------------------------|
| /feature-development | Start a new feature using conventions    |
| /run-tests           | Run all tests in the codebase            |
```