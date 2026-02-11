# Best Practices

This document outlines the best practices to follow while using, maintaining, and contributing to this repository.

---

## 1. Repository Structure

- Keep all executable or utility commands inside the `commands/` directory.
- Use meaningful and descriptive file names.
- Avoid placing temporary or experimental files in the main branch.

---

## 2. Naming Conventions

- Use lowercase and hyphen-separated names for files and folders.
  - ✅ `clear-cache.sh`
  - ❌ `ClearCache.sh`
- Command names should clearly describe their purpose.

---

## 3. Documentation

- Every command should be documented.
- Update `README.md` whenever:
  - A new command is added
  - Existing behavior changes
- Provide usage examples wherever possible.

---

## 4. Code Quality

- Keep commands simple and focused on a single responsibility.
- Avoid hardcoding environment-specific values.
- Use environment variables where applicable.
- Follow consistent formatting and indentation.

---

## 5. Version Control

- Make small, meaningful commits.
- Write clear commit messages:
  - `fix: handle empty input`
  - `feat: add cache cleanup command`
- Do not commit secrets, tokens, or credentials.

---

## 6. Testing & Validation

- Manually verify commands before pushing changes.
- If possible, test commands on a clean environment.
- Ensure commands fail gracefully with helpful error messages.

---

## 7. Security

- Never store sensitive data in the repository.
- Validate user inputs to prevent unintended execution.
- Use safe defaults for destructive commands.

---

## 8. Contribution Guidelines

- Create a feature branch for changes.
- Open a pull request with a clear description.
- Ensure documentation is updated before requesting a review.

---

## 9. Maintenance

- Remove deprecated or unused commands.
- Keep dependencies up to date.
- Regularly review open issues and pull requests.

---

Following these best practices ensures consistency, reliability, and ease of maintenance.
