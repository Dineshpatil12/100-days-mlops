# MLOps & AIOps Hands-On Labs



This repository contains practical MLOps and AIOps exercises completed as part of DevOps and Machine Learning Operations learning.



## Skills Covered



- Git & GitHub

- Python

- Machine Learning Pipelines

- DVC

- Experiment Tracking

- MLflow

- CI/CD for ML

- Docker

- Kubernetes

- Linux Administration

- MLOps Best Practices



---



## Day 20: Install and Start the MLflow Tracking Server



### Objective



Deploy and configure an MLflow Tracking Server for machine learning experiment tracking.



### Tasks Performed



- Created backend storage directory.

- Created artifact storage directory.

- Started MLflow Tracking Server in the background.

- Configured SQLite as the backend store.

- Configured local artifact storage.

- Enabled access from all interfaces.

- Verified service availability on port 5000.

- Confirmed MLflow UI accessibility.



### Commands Used



```bash

mkdir -p /root/code/mlflow-backend

mkdir -p /root/code/mlflow-artifacts



nohup mlflow server \

--host 0.0.0.0 \

--port 5000 \

--backend-store-uri sqlite:////root/code/mlflow-backend/mlflow.db \

--default-artifact-root /root/code/mlflow-artifacts \

--cors-allowed-origins '*' \

--allowed-hosts '*' \

> /root/mlflow.log 2>&1 &

```



### Verification



```bash

ps -ef | grep mlflow

ss -tulpn | grep 5000

ls -l /root/code/mlflow-backend/mlflow.db

curl -I http://localhost:5000

```



### Outcome



Successfully deployed an MLflow Tracking Server with:



- SQLite backend database

- Local artifact storage

- Background execution using nohup

- Web UI access on port 5000



### Production Use Case



MLflow is used to:



- Track machine learning experiments

- Store model parameters and metrics

- Save trained model artifacts

- Compare experiment runs

- Support model lifecycle management



Typical production architecture:



```text

Data Scientist

      |

      v

MLflow Tracking Server

      |

+----------------------+

|                      |

PostgreSQL         S3/Blob Storage

(Metadata)         (Artifacts)

```



---



## Learning Outcome



This lab provided hands-on experience with MLflow deployment, experiment tracking infrastructure, artifact management, and core MLOps concepts used in real-world machine learning platforms.
