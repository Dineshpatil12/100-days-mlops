# Day 24: Enable MLflow Autologging

## Objective

The objective of this task was to enable MLflow autologging for a Scikit-Learn model so that model parameters, metrics, and artifacts are automatically tracked without manually calling logging functions.

---

## Environment

- Python 3
- MLflow
- Scikit-Learn
- VS Code Development Environment

---

## Problem Statement

The training script contained two TODO sections that needed to be completed:

1. Enable MLflow autologging for Scikit-Learn.
2. Create and use an experiment named `autolog-demo`.

After execution, MLflow should automatically capture:

- Model parameters
- Training metrics
- Model artifacts
- Run information

---

## Code Changes

Added the following lines:

```python
mlflow.sklearn.autolog()
mlflow.set_experiment("autolog-demo")
```

---

## Execution

Run the script:

```bash
python3 /root/code/autolog_experiment.py
```

---

## Output

```text
Experiment with name 'autolog-demo' does not exist. Creating a new experiment.

Created MLflow autologging run with ID ...

View run at:
http://localhost:5000

Autolog run complete — check the MLflow UI
```

---

## MLflow Verification

### Experiment

```text
autolog-demo
```

### Run

```text
illustrious-rook-144
```

### Logged Parameters

```text
C = 1.0
class_weight = None
dual = False
fit_intercept = True
intercept_scaling = 1
l1_ratio = 0.0
max_iter = 100
n_jobs = None
penalty = deprecated
random_state = 42
solver = lbfgs
tol = 0.0001
verbose = 0
warm_start = False
```

### Logged Model

```text
model/
├── MLmodel
├── model.pkl
├── conda.yaml
├── requirements.txt
└── python_env.yaml
```

---

## Key Learning

### Manual Logging

Without autologging, parameters and metrics must be logged manually:

```python
mlflow.log_param()
mlflow.log_metric()
mlflow.sklearn.log_model()
```

### Automatic Logging

With autologging enabled:

```python
mlflow.sklearn.autolog()
```

MLflow automatically records:

- Model parameters
- Training metrics
- Model artifacts
- Environment information
- Run metadata

This reduces boilerplate code and improves experiment tracking.

---

## Result

✅ Enabled MLflow Autologging

✅ Created experiment `autolog-demo`

✅ Generated MLflow run automatically

✅ Logged LogisticRegression parameters

✅ Logged model artifacts

✅ Successfully completed the challenge

---

## Reference

Challenge Ref ID:

```text
69fc54e42875c0195a38f6de
```
