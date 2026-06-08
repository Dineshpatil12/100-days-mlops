# Fraud Detection ML Pipeline with DVC

## Overview

This project implements an end-to-end Machine Learning pipeline for fraud detection using DVC (Data Version Control) and Git. The pipeline is fully reproducible, version-controlled, and integrated with SeaweedFS remote storage.

## Project Structure

```text
.
├── data
│   ├── raw
│   │   └── data.csv
│   └── processed
│       ├── clean.csv
│       └── test_split.csv
├── models
│   └── model.pkl
├── reports
│   ├── validation.json
│   └── evaluation.json
├── scripts
│   ├── ingest.py
│   ├── validate.py
│   ├── preprocess.py
│   ├── train.py
│   └── evaluate.py
├── metrics.json
├── params.yaml
├── dvc.yaml
└── dvc.lock
```

## Pipeline Stages

### 1. Ingest

Loads the raw fraud detection dataset.

### 2. Validate

Validates dataset quality and generates validation reports.

Output:

* reports/validation.json

### 3. Preprocess

Cleans and prepares the dataset for training.

Output:

* data/processed/clean.csv

### 4. Train

Trains a Random Forest classifier using parameters from params.yaml.

Parameters:

* n_estimators
* max_depth
* test_size
* random_seed

Outputs:

* models/model.pkl
* data/processed/test_split.csv

Metrics:

* metrics.json

### 5. Evaluate

Evaluates the trained model against the test dataset.

Output:

* reports/evaluation.json

## Run Pipeline

Execute the complete pipeline:

```bash
dvc repro
```

## Push Artifacts to Remote Storage

```bash
dvc push
```

## Git Versioning

Commit changes:

```bash
git add .
git commit -m "Complete DVC fraud detection pipeline"
```

Create release tag:

```bash
git tag -a v1.0 -m "Production release v1.0"
```

## Model Performance

Example evaluation results:

* Accuracy: 1.0
* F1 Score: 1.0
* Precision: 1.0
* Recall: 1.0

## Remote Storage

DVC artifacts are stored in a SeaweedFS bucket configured as the project's remote storage backend.

## Release

Version: v1.0

