# Day 1 - Create Python Virtual Environment for ML

## Objective

Set up a standardized Python virtual environment for machine learning development.

---

## Commands Used

```bash
python3 -m venv ml-env

source ml-env/bin/activate

pip install numpy pandas scikit-learn matplotlib

pip freeze > requirements.txt
```

---

## Installed Packages

- numpy
- pandas
- scikit-learn
- matplotlib

---

## Verification

```bash
pip list
```

---

## Learning Outcome

- Learned Python virtual environment management
- Installed common ML dependencies
- Generated reproducible dependency file
- Understood isolated ML development setup

---

## Real-World Relevance

Virtual environments help isolate dependencies and ensure reproducible ML workflows across development and production systems.
