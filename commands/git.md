
# Developer Reference – Git Commands & Best Practices

This document serves as a **quick reference guide** for commonly used Git management commands. It is intended to improve consistency, speed, and accuracy during development and deployment workflows.

---


## Git Commands Reference

### Clone Repository (Specific Branch)

```bash
git clone <repository-url> -b <branch-name>
```

---

### Branch Management

```bash
git branch                 # List branches
git branch <branch-name>   # Create new branch
git checkout <branch-name> # Switch branch
```

---

### Working with Changes

```bash
git status
git add .
git commit -m "your commit message"
git push origin <branch-name>
```

---

### Rename Current Branch

```bash
git branch -m <new-branch-name>
```

---

### Amend Last Commit

Modify the most recent commit (message or content).

```bash
git commit --amend
```

---

### Fetch Code from a Pull Request

Fetch and checkout a PR locally for testing or review.

```bash
git fetch origin pull/<PR_NUMBER>/head:<BRANCH_NAME>
```

**Examples:**

```bash
git fetch origin pull/230/head:issue-215
git fetch origin pull/15/head:feature/docker-compose
```

---

## Git Patch Commands

### Create Patch File

Generate patch files between two commits.

```bash
git format-patch <start-commit-id>..<end-commit-id>
```

---

### Apply Patch File

Apply a patch safely (creates `.rej` files if conflicts occur).

```bash
git apply --reject --whitespace=fix 0001-feat-added-new-api-endpoints.patch
```

---