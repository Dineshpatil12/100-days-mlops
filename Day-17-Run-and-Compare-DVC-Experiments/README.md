What was the goal?

The goal was to test different values of the Random Forest hyperparameter n_estimators, compare model performance, and select the best model without manually modifying project files.

What is n_estimators?

n_estimators defines the number of decision trees in a Random Forest model.

Example:

n_estimators: 100
50 = 50 trees
200 = 200 trees
500 = 500 trees

More trees can improve accuracy but increase training time.

What did we do?
1. Checked Current Parameter
cat params.yaml

Output:

n_estimators: 100

This was the baseline configuration.

2. Ran Baseline Pipeline
dvc repro

This trained the model using:

n_estimators: 100

and generated:

metrics.json

containing accuracy and F1 score.

3. Ran Multiple Experiments
Experiment 1
dvc exp run -S n_estimators=50
Experiment 2
dvc exp run -S n_estimators=200
Experiment 3
dvc exp run -S n_estimators=500

DVC automatically:

Changed parameter temporarily
Executed pipeline
Saved experiment results
Kept main workspace unchanged
4. Compared Experiments
dvc exp show

Example:

Experiment	n_estimators	Accuracy	F1 Score
Workspace	100	0.91	0.89
Exp 1	50	0.90	0.88
Exp 2	200	0.94	0.92
Exp 3	500	0.93	0.91
5. Selected Best Experiment

Comparison:

n_estimators	Accuracy	F1 Score
50	0.90	0.88
200	0.94	0.92
500	0.93	0.91

Best Result:

n_estimators = 200
accuracy = 0.94
f1_score = 0.92

Reason:

Highest Accuracy
Highest F1 Score
6. Applied Best Experiment
dvc exp apply <experiment-id>

Example:

dvc exp apply 919190d

or

dvc exp apply elfin-dita

Now the workspace uses:

n_estimators: 200
7. Saved Changes
dvc commit

This saves DVC-tracked outputs.
