# Day 29 - Configure MLflow with Remote Tracking Server and Artifact Store

## Project Overview

This project demonstrates how to configure MLflow with a production-style setup using:

* PostgreSQL as the backend store for experiment metadata
* SeaweedFS (S3-compatible) as the artifact store
* MLflow Tracking Server for experiment tracking and model management

The objective was to diagnose and fix an artifact storage connectivity issue that prevented MLflow from uploading model artifacts to the SeaweedFS bucket.

---

## Architecture

```text
MLflow Client
      |
      v
MLflow Tracking Server (Port 5000)
      |
      +---- PostgreSQL (Metadata Store)
      |
      +---- SeaweedFS S3 Bucket (Artifact Store)
```

---

## Problem Statement

The MLflow server was successfully storing experiment metadata in PostgreSQL, but model artifacts were not being uploaded to the SeaweedFS bucket.

The issue was caused by an incorrect artifact store configuration in the MLflow startup script.

---

## Solution

### Verified MLflow Configuration

```bash
export AWS_ACCESS_KEY_ID=weedadmin
export AWS_SECRET_ACCESS_KEY=weedadmin123
export MLFLOW_S3_ENDPOINT_URL=http://localhost:8333
```

### MLflow Server Startup

```bash
mlflow server \
  --backend-store-uri postgresql://mlflow:mlflow123@localhost:5432/mlflow \
  --artifacts-destination s3://mlflow-artifacts \
  --host 0.0.0.0 \
  --port 5000
```

### Restarted MLflow Server

```bash
bash /root/code/restart-mlflow.sh
```

### Executed Smoke Test

```bash
python3 /root/code/log_test_run.py
```

---

## Validation

### PostgreSQL Validation

Verified experiment metadata, parameters, metrics, and run information were stored successfully.

Example:

```sql
SELECT * FROM runs;
SELECT * FROM params;
SELECT * FROM metrics;
```

### SeaweedFS Validation

Verified model artifacts were uploaded to the bucket:

```text
mlflow-artifacts/
└── 1/
    └── models/
        └── model-files
```

### Smoke Test Result

```text
test-remote run logged successfully
```

---

## Skills Demonstrated

* MLflow Configuration
* MLflow Tracking Server Administration
* PostgreSQL Integration
* S3-Compatible Storage Configuration
* SeaweedFS Administration
* Linux Troubleshooting
* Environment Variable Management
* Log Analysis
* DevOps Debugging
* MLOps Fundamentals

---

## Key Learning Outcomes

* Understanding MLflow architecture
* Difference between metadata store and artifact store
* Configuring remote tracking servers
* Using PostgreSQL as a backend store
* Using SeaweedFS as an S3-compatible artifact store
* Troubleshooting MLflow connectivity issues
* Validating end-to-end MLOps workflows

---

## Result

Successfully configured MLflow with:

* PostgreSQL Backend Store ✅
* SeaweedFS Artifact Store ✅
* Remote Tracking Server ✅
* Successful Experiment Tracking ✅
* Successful Artifact Upload ✅
* End-to-End Validation ✅

---

**Author:** Dinesh Patil
**Role:** DevOps / MLOps Learning Project

