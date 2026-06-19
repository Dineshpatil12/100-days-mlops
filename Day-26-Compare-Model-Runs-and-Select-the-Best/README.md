# Day 26: Compare Model Runs and Select the Best

## Objective
Compare multiple MLflow experiment runs and identify the best-performing model based on the `f1_score` metric. Mark the winning run with a tag so it can be used by downstream processes.

## Prerequisites
- MLflow Tracking Server running on port 5000
- Pre-populated experiment: `model-comparison`
- Three model runs:
  - RandomForest
  - GradientBoosting
  - LogisticRegression

## Steps Performed

### 1. Open MLflow UI
Access the MLflow UI:

http://localhost:5000

### 2. Review Experiment Runs
Navigate to the `model-comparison` experiment and inspect the available runs.

### 3. Compare Metrics
Select all three runs and compare their metrics side by side.

Metrics reviewed:
- accuracy
- f1_score

### 4. Identify the Best Model
Determine the run with the highest `f1_score`.

### 5. Tag the Winning Run
Add the following run-level tag to the best-performing run:

Key:
production-candidate

Value:
true

### 6. Validate Results
Confirm that:
- Only the winning run contains the `production-candidate=true` tag.
- The remaining runs do not contain this tag.

## Outcome
Successfully compared candidate models and marked the best-performing run based on the highest `f1_score`.

## Tools Used
- MLflow Tracking
- MLflow UI
- Experiment Comparison View
- Run Tags

## Result
The model with the highest `f1_score` was selected and tagged as the production candidate for downstream workflows.
