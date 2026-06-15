# Day 23 - Search and Query MLflow Runs

## Objective

Use the MLflow UI to review experiment runs in the `fraud-detection` experiment and classify them based on their F1 Score.

## Tasks Performed

### 1. Shortlist the Best Model

* Opened the MLflow Tracking UI.
* Navigated to the `fraud-detection` experiment.
* Reviewed all experiment runs.
* Identified runs with `f1_score > 0.85`.
* Selected the run with the highest F1 Score.
* Added the tag:

```text
review-status = shortlisted
```

### 2. Reject Under-Performing Models

* Identified all runs with:

```text
f1_score < 0.75
```

* Added the tag:

```text
review-status = rejected
```

to each under-performing run.

### 3. Leave Remaining Runs Unchanged

* Runs with:

```text
0.75 <= f1_score <= 0.85
```

were left without any `review-status` tag.

## Technologies Used

* MLflow
* MLflow Tracking Server
* MLflow UI

## Verification Criteria

* Exactly one run is tagged:

```text
review-status = shortlisted
```

* Every run with `f1_score < 0.75` is tagged:

```text
review-status = rejected
```

* All other runs have no `review-status` tag.

## Outcome

Successfully reviewed and classified MLflow experiment runs based on model performance metrics using the MLflow UI.

