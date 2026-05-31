## Task
Move transactions dataset from Git tracking to DVC tracking.

## Commands

git rm --cached data/raw/transactions.csv
dvc add data/raw/transactions.csv
git add data/raw/transactions.csv.dvc data/raw/.gitignore
git commit -m "Track transactions dataset with DVC"

## Outcome
- Dataset removed from Git tracking
- Dataset tracked by DVC
- .dvc pointer file created
- Git repository remains lightweight
