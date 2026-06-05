Day 16: Track ML Metrics with DVC

Objective:
Configure DVC to track machine learning metrics generated during model training.

Tasks Performed:
- Updated the train stage in dvc.yaml.
- Registered metrics.json under metrics instead of outs.
- Configured cache: false to keep metrics in Git history.
- Re-ran the pipeline using dvc repro.
- Verified metrics using dvc metrics show.

Result:
DVC now tracks and displays model metrics such as accuracy and f1_score.

Commands Used:
dvc repro
dvc metrics show

Output:
accuracy: 1.0
f1_score: 1.0
