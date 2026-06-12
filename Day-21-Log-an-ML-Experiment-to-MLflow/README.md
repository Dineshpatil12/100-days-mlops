# MLflow Experiment Logging

## Overview

This project demonstrates how to log a machine learning experiment using MLflow.

The script trains a simple Scikit-Learn model and records:

- Hyperparameters
- Evaluation Metrics
- Trained Model Artifact

into the MLflow Tracking Server.

---

## Technologies Used

- Python 3
- MLflow
- Scikit-Learn

---

## Parameters Logged

| Parameter | Value |
|------------|--------|
| n_estimators | 100 |
| max_depth | 5 |
| random_state | 42 |

---

## Metrics Logged

| Metric | Value |
|---------|---------|
| accuracy | 0.92 |
| f1_score | 0.89 |

---

## Model Artifact

The trained Scikit-Learn model is stored as an MLflow artifact.

---

## Run the Project

```bash
python3 log_experiment.py
```

## View MLflow Dashboard

```bash
http://localhost:5000
```

---

## MLflow Features Demonstrated

- Experiment Tracking
- Parameter Logging
- Metric Logging
- Model Artifact Logging
- Run Management
