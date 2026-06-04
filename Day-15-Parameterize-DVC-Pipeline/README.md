# Day 15 - Parameterize a DVC Pipeline

## Objective
Manage model hyperparameters using `params.yaml` and verify that DVC automatically re-runs dependent stages when parameters change.

## Tasks Completed
- Fixed parameter reference between `dvc.yaml` and `params.yaml`
- Executed the full DVC pipeline
- Updated `n_estimators` from 100 to 200
- Re-ran `dvc repro`
- Verified only the `train` stage executed
- Confirmed parameter update in `dvc.lock`
- Regenerated `models/model.pkl`

## Commands Used

dvc repro
cat params.yaml
cat dvc.lock

## Result
DVC successfully tracked parameter changes and re-executed only the affected pipeline stage.
