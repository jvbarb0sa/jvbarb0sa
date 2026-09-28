```markdown
# jvbarb0sa Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill documents the development patterns and conventions used in the `jvbarb0sa` Python repository. It covers file and code style conventions, commit patterns, and testing practices to ensure consistency and maintainability across the codebase.

## Coding Conventions

### File Naming
- Use **snake_case** for all Python files.
  - Example: `my_module.py`, `data_processor.py`

### Import Style
- Use **relative imports** within the package.
  - Example:
    ```python
    from .utils import helper_function
    ```

### Export Style
- Use **named exports**; explicitly define what is exported from each module.
  - Example:
    ```python
    __all__ = ['MyClass', 'my_function']
    ```

### Commit Patterns
- Follow the **conventional commits** style.
- Use the `feat` prefix for new features.
- Keep commit messages concise (average 54 characters).
  - Example:
    ```
    feat: add data validation to input parser
    ```

## Workflows

### Feature Development
**Trigger:** When adding a new feature to the codebase  
**Command:** `/feature-development`

1. Create a new branch for your feature.
2. Implement the feature using snake_case file naming and relative imports.
3. Write or update tests with the `*.test.*` pattern.
4. Commit changes using the `feat` prefix and a concise message.
5. Open a pull request for review.

### Testing
**Trigger:** When verifying code correctness  
**Command:** `/run-tests`

1. Identify test files matching the `*.test.*` pattern.
2. Run tests using your preferred Python test runner (e.g., `pytest` or `unittest`).
3. Review test results and fix any failing tests.

## Testing Patterns

- Test files follow the pattern `*.test.*` (e.g., `module.test.py`).
- The specific test framework is not enforced; use your preferred Python testing tool.
- Place test files alongside the modules they test or in a dedicated `tests/` directory.

  Example test file:
  ```python
  # file: utils.test.py
  import unittest
  from .utils import helper_function

  class TestUtils(unittest.TestCase):
      def test_helper_function(self):
          self.assertEqual(helper_function(2), 4)
  ```

## Commands
| Command              | Purpose                                     |
|----------------------|---------------------------------------------|
| /feature-development | Start a new feature development workflow    |
| /run-tests           | Run all test files in the repository        |
```