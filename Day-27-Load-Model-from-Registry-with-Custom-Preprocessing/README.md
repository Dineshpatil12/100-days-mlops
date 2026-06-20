# Day 27 - Load Model from Registry with Custom Preprocessing

## Objective
Load the champion fraud detection model from MLflow Model Registry, apply custom preprocessing, generate predictions, and save results.

## Steps Performed

1. Loaded champion model from MLflow Registry:
   models:/fraud-detector@champion

2. Wrapped model using ScaledPredictor.

3. Generated batch predictions for inputs.csv.

4. Added predictions as a new column named:
   prediction

5. Saved results to:
   /root/code/predictions.csv

## Run

python3 /root/code/predict_with_preprocessing.py

## Output

predictions.csv

Contains:
- Original input columns
- prediction column
- 10 prediction rows
