## Day 18 - Fraud Detection - DVC Dataset and Model Versioning

## Project Overview

This project demonstrates how to manage multiple versions of machine learning datasets and models using **Git** and **DVC (Data Version Control)**.

The objective is to maintain separate dataset and model versions across Git branches, enabling data scientists to switch between versions while preserving reproducibility.

---

## Technologies Used

* Git
* DVC (Data Version Control)
* Python
* Machine Learning Pipeline
* CSV Dataset Management

---

## Project Structure

```text
fraud-detection/
├── data/
│   ├── raw/
│   │   ├── transactions.csv
│   │   └── transactions_v2.csv
│   └── processed/
├── models/
├── src/
├── dvc.yaml
├── dvc.lock
├── metrics.json
└── params.yaml
```

---

## Versioning Strategy

### Version 1.0

* Branch: `main`
* Tag: `v1.0`
* Dataset: Original transactions dataset

Dataset Hash:

```text
c4dd797a1451653b3cb76a8bb7b2b4d9
```

---

### Version 2 Improved

* Branch: `v2-improved`
* Dataset: Enhanced transaction dataset
* Pipeline re-executed using updated data

Dataset Hash:

```text
bd6bde1f4b10d12c6249a2d021b57e87
```

---

## Workflow

### Tag Existing Version

```bash
git tag -a v1.0 -m "Baseline version"
```

### Create New Branch

```bash
git checkout -b v2-improved
```

### Replace Dataset

```bash
cp data/raw/transactions_v2.csv data/raw/transactions.csv
```

### Track Dataset with DVC

```bash
dvc add data/raw/transactions.csv
```

### Reproduce Pipeline

```bash
dvc repro
```

### Commit Changes

```bash
git add .
git commit -m "Add improved dataset and retrain model"
```

---

## Restore Original Dataset

Switch back to the main branch:

```bash
git checkout main
```

Restore DVC tracked files:

```bash
dvc checkout
```

Verify the dataset version:

```bash
cat data/raw/transactions.csv.dvc
```

---

## Validation

Check branches:

```bash
git branch
```

Check tags:

```bash
git tag
```

View commit history:

```bash
git log --oneline --decorate --all --graph
```

Verify dataset tracking:

```bash
cat data/raw/transactions.csv.dvc
```

---

## Outcome

Successfully implemented:

* Dataset versioning using DVC
* Branch-based data management using Git
* Model retraining with updated datasets
* Reproducible ML pipeline execution
* Dataset rollback and restoration using DVC checkout

This workflow enables efficient collaboration, experiment tracking, and reproducible machine learning development.

