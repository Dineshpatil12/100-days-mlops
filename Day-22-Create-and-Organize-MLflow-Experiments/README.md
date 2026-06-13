# MLflow Experiment Registration – Fraud Detection & Churn Prediction

## Overview
This repository documents the creation of two new MLflow experiments for the xFusionCorp Industries ML platform team.  
The experiments are registered with the required metadata (description and team tags) and do **not** modify the existing `Default` or `legacy-models` experiments.

## Experiments Created

| Experiment Name | Description | Team Tag |
|----------------|-------------|----------|
| `fraud-detection` | Machine learning project for detecting fraudulent transactions. | `team` = `ml-platform` |
| `churn-prediction` | Machine learning project for customer churn prediction. | `team` = `analytics` |

## Prerequisites
- MLflow tracking server running on port `5000`
- Access to the MLflow UI (browser)

## Steps Performed (Summary)
1. Opened MLflow UI (port `5000`).
2. Created `fraud-detection` experiment with:
   - Non‑empty description
   - Tag: `team` = `ml-platform`
3. Created `churn-prediction` experiment with:
   - Tag: `team` = `analytics`
4. Verified both experiments appear in the left‑hand list with correct tags/description.

## Verification
- In MLflow UI → click on each experiment → confirm description and tags are visible.
- Existing experiments (`Default`, `legacy-models`) remain untouched.

## Status
✅ Task completed successfully.  
**Ref ID:** `69fc54916b1bd93e41b99632`

## Notes
- Artifact locations were left as default (not required).
- The `legacy-models` experiment is preserved with its existing tags (`ml-legacy`, `archived`).

## Repository Structure (optional)
