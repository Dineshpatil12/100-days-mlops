# Day 28 - Fix a Broken MLflow Project and Re-Run It

## Objective

Diagnose and fix a broken MLflow Project configuration, then execute successful MLflow runs to register experiments in the MLflow Tracking Server.

## Problem Statement

The MLflow Project failed because the parameter name defined in the `MLproject` file did not match the argument expected by `train.py`.

### Incorrect Parameter

```yaml
--n_est {n_estimators}
```

### Correct Parameter

```yaml
--n_estimators {n_estimators}
```

## Files

```
trainer/
├── MLproject
└── train.py
```

## Fix Applied

Updated the MLproject command section:

```yaml
command: >
  python train.py
  --n_estimators {n_estimators}
  --max_depth {max_depth}
  --test_size {test_size}
  --random_seed {random_seed}
```

## Commands Executed

### Custom Run

```bash
mlflow run . -e train -P n_estimators=200 -P max_depth=10 --env-manager=local
```

### Default Run

```bash
mlflow run . -e train --env-manager=local
```

## Result

* Original failed run preserved for debugging history.
* Two successful MLflow runs recorded.
* Parameters correctly logged in the MLflow Tracking Server.
* Experiment execution completed successfully.

## Key Learnings

* MLflow Project structure
* MLproject configuration
* Parameter mapping between MLproject and Python argparse
* YAML troubleshooting
* MLflow experiment tracking
* Reproducible machine learning workflows

