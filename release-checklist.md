# Release Checklist

Use this checklist before creating a new release to ensure quality and consistency.

---

## 1. Code Readiness

- All changes are merged into the main branch
- No debug or temporary code remains
- Commands are tested and working as expected

---

## 2. Documentation

- `README.md` is updated
- New commands are documented
- Breaking changes (if any) are clearly mentioned

---

## 3. Versioning

- Version number is updated (if applicable)
- Release follows semantic versioning:
  - MAJOR: Breaking changes
  - MINOR: New features
  - PATCH: Bug fixes

---

## 4. Quality Checks

- Code formatting is consistent
- No unused files or scripts
- No secrets or credentials committed

---

## 5. Git & CI

- All checks / CI pipelines are passing
- Branch is up to date with `main`
- Commit history is clean and meaningful

---

## 6. Release Preparation

- Create a Git tag (e.g., `v1.0.0`)
- Write clear release notes
- Highlight important changes and fixes

---

## 7. Post-Release

- Verify release artifacts (if any)
- Announce the release to the team/users
- Monitor issues or feedback after release

---

This checklist helps ensure stable and predictable releases.
