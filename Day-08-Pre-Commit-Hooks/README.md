# Day 8 - Configure Pre-Commit Hooks for ML Repository

## 🎯 Objective

Configure pre-commit hooks to automatically enforce code quality checks before every git commit.

---

## 📁 Repository Path

```bash
/root/code/fraud-detection
```

---

## 🛠 Tasks Performed

- Fixed broken `.pre-commit-config.yaml`
- Corrected invalid hook definitions
- Updated deprecated Ruff repository
- Added proper version pinning
- Installed git pre-commit hooks
- Executed all hooks successfully
- Auto-fixed formatting issues

---

## 🔍 Issues Identified

### Incorrect Hook ID

Incorrect:

```yaml
- id: check_yaml
```

Corrected:

```yaml
- id: check-yaml
```

---

### Deprecated Ruff Repository

Incorrect:

```yaml
https://github.com/charliermarsh/ruff-pre-commit
```

Corrected:

```yaml
https://github.com/astral-sh/ruff-pre-commit
```

---

### Incorrect Ruff Hook Name

Incorrect:

```yaml
- id: ruff-lint
```

Corrected:

```yaml
- id: ruff
```

---

### Missing Version Pinning

Every repository entry requires a fixed `rev:` version to ensure reproducible builds.

---

## ✅ Final Configuration

```yaml
repos:
  - repo: https://github.com/pre-commit/pre-commit-hooks
    rev: v5.0.0
    hooks:
      - id: trailing-whitespace
      - id: end-of-file-fixer
      - id: check-yaml

  - repo: https://github.com/astral-sh/ruff-pre-commit
    rev: v0.12.11
    hooks:
      - id: ruff

  - repo: https://github.com/psf/black-pre-commit-mirror
    rev: 25.1.0
    hooks:
      - id: black
```

---

## ⚙️ Hooks Explanation

### trailing-whitespace

Removes unnecessary spaces at line endings.

---

### end-of-file-fixer

Ensures every file ends with a newline.

---

### check-yaml

Validates YAML syntax and formatting.

---

### ruff

Performs Python linting and code quality checks.

Detects:

- unused imports
- syntax issues
- formatting problems
- best practice violations

---

### black

Automatically formats Python code into a consistent style.

---

## 🚀 Commands Used

### Validate Configuration

```bash
pre-commit validate-config
```

---

### Install Hooks

```bash
pre-commit install
```

This creates:

```text
.git/hooks/pre-commit
```

---

### Run Hooks on All Files

```bash
pre-commit run --all-files
```

---

## ⚠️ Initial Failure Reason

First execution failed because hooks automatically corrected formatting issues.

Example:

```text
trim trailing whitespace...Failed
files were modified by this hook
```

This behavior is expected.

---

## ✅ Final Result

After rerunning:

```bash
pre-commit run --all-files
```

All hooks passed successfully.

---

## 🧠 Learning Outcome

- Learned pre-commit workflow
- Configured git hooks
- Practiced Python linting automation
- Understood version pinning
- Explored automatic formatting tools

---

## 🛠 Skills Practiced

- Git hooks
- Pre-commit framework
- Ruff linting
- Black formatting
- YAML validation
- CI/CD quality checks
- Python code quality automation

---

## 🌍 Real-World Relevance

Pre-commit hooks are widely used in:

- DevOps pipelines
- MLOps repositories
- GitHub Actions
- Jenkins CI/CD
- Enterprise Python projects

These checks prevent low-quality code from entering production repositories.
