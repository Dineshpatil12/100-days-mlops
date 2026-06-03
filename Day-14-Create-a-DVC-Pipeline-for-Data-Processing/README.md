Day 14 - Create a DVC Pipeline for Data Processing

- Fixed the DVC pipeline configuration in dvc.yaml.
- Configured the process_data stage to process raw transaction data.
- Configured the split_data stage to generate train and test datasets.
- Verified pipeline execution using dvc repro.
- Confirmed all stages are up to date with dvc status.
- Validated pipeline dependencies using dvc dag.

Tools Used:
- DVC
- Python
- Git

Outcome:
Successfully created a reproducible two-stage data processing pipeline with proper dependency tracking and outputs.
