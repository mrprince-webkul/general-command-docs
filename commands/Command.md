# Developer Reference – Useful Commands & Best Practices

This document serves as a **quick reference guide** for commonly used server, Docker, Git, and release management commands. It is intended to improve consistency, speed, and accuracy during development and deployment workflows.

---

## Server ↔ Local ↔ Server File Transfer (rsync)

### Copy files from **Remote Server to Local Machine**

Efficiently sync files from a remote server to your local system using SSH.

```bash
rsync -avz -e "ssh -i <your-key-file>" user@<server-ip>:/path/to/source /local/destination --progress
```

**Options explained:**

* `-a` : Archive mode (preserves permissions & structure)
* `-v` : Verbose output
* `-z` : Compress files during transfer
* `--progress` : Show transfer progress

---

### Copy files from **Local Machine to Remote Server**

Upload local files or directories to a remote server securely.

```bash
rsync -avz -e "ssh -i <your-key-file>" /local/path/to/source user@<server-ip>:/path/to/destination --progress
```

---

## Commit Message Standards

Follow **Conventional Commits** to keep commit history clean and readable.

🔗 Reference:
[https://www.conventionalcommits.org/en/v1.0.0/#specification](https://www.conventionalcommits.org/en/v1.0.0/#specification)

**Example:**

```text
feat: add supplier bulk upload support
fix: resolve validation issue in product form
```

---

## Database Setup Using Docker

### MariaDB (Docker)

Run a MariaDB container with a predefined root password and exposed port.

```bash
docker run \
  --name mariadb-server \
  -e MYSQL_ROOT_PASSWORD=webkul \
  -p 3311:3306 \
  -d mariadb
```

---

### PostgreSQL (Docker)

#### Inspect Docker Volume

Check details of an existing PostgreSQL volume.

```bash
docker volume inspect pgsqlData
```

#### Run PostgreSQL Container

```bash
docker run \
  --name postgres-database \
  -e POSTGRES_USER=devansh \
  -e POSTGRES_PASSWORD=devansh \
  -e POSTGRES_DB=unopim \
  -v pgsqlData:/var/lib/postgresql/data \
  -p 5432:5432 \
  -d postgres:16
```

---

## Recommended Reading & Best Practices

### Laravel Best Practices

A curated list of Laravel conventions and architectural guidelines.

🔗 [https://github.com/alexeymezenin/laravel-best-practices](https://github.com/alexeymezenin/laravel-best-practices)

---

## Pre-Release Checklist

Before creating a release, ensure the following steps are completed:

* ✅ Update `CHANGELOG.md`
* ✅ Document high-impact & low-impact changes in `upgrade.md`
* ✅ Update version number in `Core.php`
* ✅ Review previous release commits & release notes

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

**Tip:** Keep this document updated as workflows evolve to maintain team efficiency and consistency.
