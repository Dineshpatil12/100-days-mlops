# Day 6 - Set Up Code Quality Tools for ML Code

## Objective

Configure and fix Python code quality checks using Ruff and Black.

---

## Tools Used

- Ruff
- Black

---

## Tasks Performed

- Fixed deprecated Ruff configuration
- Configured linting rules
- Standardized line length settings
- Removed unused imports
- Auto-fixed lint issues
- Verified code formatting

---

## Ruff Configuration

```toml
[tool.ruff.lint]
select = ["E", "F", "W", "I"]
```

---

## Rules Explained

| Rule | Description |
|------|-------------|
| E | Style errors |
| F | Code issues |
| W | Warnings |
| I | Import sorting |

---

## Commands Used

### Run Ruff Checks

```bash
ruff check src/
```

### Auto Fix Issues

```bash
ruff check src/ --fix
```

### Verify Formatting

```bash
black --check src/
```

---

## Issues Fixed

### Removed Unused Imports

```python
import os
```

Unused imports were removed to satisfy Ruff checks.

---

## Learning Outcome

- Learned Python linting workflows
- Practiced automatic code fixing
- Understood formatting standardization
- Improved Python project quality

---

## Real-World Relevance

Code quality tools like Ruff and Black are commonly integrated into:

- GitHub Actions
- Jenkins pipelines
- Azure DevOps
- CI/CD workflows

These tools help maintain clean, consistent, and production-ready Python codebases.

---

## Final Result

```text
All checks passed!
All done! ✨ 🍰 ✨
```
