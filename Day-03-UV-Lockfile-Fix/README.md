# Day 3 - Fix a Broken UV Lockfile Specification

## Objective

Fix dependency specification issues and generate a valid lockfile.

---

## Tasks Performed

- Reviewed requirements.in
- Fixed package version specifications
- Generated requirements.txt using uv
- Verified dependency resolution
- Checked transitive dependencies

---

## Commands Used

```bash
uv pip compile requirements.in -o requirements.txt
```

---

## Learning Outcome

- Learned dependency management
- Understood package version pinning
- Practiced reproducible environment setup
- Explored transitive dependencies

---

## Real-World Relevance

Lockfiles ensure consistent package installation across development, testing, and production environments.
