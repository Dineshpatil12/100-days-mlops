# Day 7 - Package an ML Project as Installable Python Package

## Objective

Convert an existing ML project into a proper installable Python package and generate distributable build artifacts.

---

## Project Path

```bash
/root/code/fraud-detection
```

---

## Tasks Performed

- Inspected existing pyproject.toml
- Fixed package metadata
- Added build-system configuration
- Configured src-layout packaging
- Added required dependencies
- Built wheel and source distributions
- Verified generated package artifacts

---

## Issues Identified

### Missing build-system section

The original configuration did not contain the required build system configuration.

---

### Incorrect package name

Incorrect:

```toml
name = "fraud-detection"
```

Corrected to:

```toml
name = "fraud_detection"
```

---

### Incorrect version

Incorrect:

```toml
version = "0.0.1"
```

Corrected to:

```toml
version = "0.1.0"
```

---

### Incorrect Python requirement

Incorrect:

```toml
requires-python = ">=3.8"
```

Corrected to:

```toml
requires-python = ">=3.10"
```

---

### Missing dependencies

Added required ML dependencies:

- scikit-learn
- pandas
- numpy

---

## Final pyproject.toml

```toml
[build-system]
requires = ["setuptools>=61.0", "wheel"]
build-backend = "setuptools.build_meta"

[project]
name = "fraud_detection"
version = "0.1.0"
requires-python = ">=3.10"
dependencies = [
    "scikit-learn",
    "pandas",
    "numpy"
]

[tool.setuptools.packages.find]
where = ["src"]

[tool.setuptools]
package-dir = {"" = "src"}
```

---

## Build Command

```bash
python3 -m build
```

---

## Build Artifacts Generated

```text
dist/
├── fraud_detection-0.1.0-py3-none-any.whl
└── fraud_detection-0.1.0.tar.gz
```

---

## Package Verification

```bash
ls dist/*.whl
```

### Output

```text
dist/fraud_detection-0.1.0-py3-none-any.whl
```

---

## Wheel Installation Example

```bash
pip install fraud_detection-0.1.0-py3-none-any.whl
```

---

## Learning Outcome

- Learned Python packaging workflows
- Configured pyproject.toml
- Understood setuptools build system
- Generated wheel distributions
- Practiced dependency management
- Explored src-layout packaging

---

## Skills Practiced

- Python Packaging
- setuptools
- wheel
- Build Systems
- Dependency Management
- Package Distribution
- MLOps Packaging Workflow

---

## Real-World Relevance

Python packaging is widely used in:

- ML model deployment
- CI/CD pipelines
- Internal Python libraries
- Reusable automation tools
- Docker image builds
- Kubernetes workloads
- Production MLOps systems

Installable packages improve code reuse, deployment consistency, and automation workflows.
