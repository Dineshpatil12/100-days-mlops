# Day 10101010101010101010 - Initialize DVC in Existing Git Repository

## Objective

Initialize DVC in an existing ML project repository to manage datasets and model files separately from source code.

## Steps Performed

1. Opened the existing Git repository
2. Initialized DVC using:

   ```bash id="j49duh"
   dvc init
   ```
3. Added generated DVC files to Git:

   ```bash id="fkm7pj"
   git add .dvc .dvcignore
   ```
4. Created a Git commit:

   ```bash id="gb4x9m"
   git commit -m "Initialize DVC"
   ```

## Files Created

* `.dvc/config`
* `.dvc/.gitignore`
* `.dvcignore`

## Outcome

Successfully integrated DVC with Git for better ML project version control and data management.

