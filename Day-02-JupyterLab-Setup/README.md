# Day 2 - Set Up and Configure JupyterLab Server

## Objective

Diagnose and fix JupyterLab configuration issues.

---

## Tasks Performed

- Verified JupyterLab configuration
- Fixed incorrect host binding
- Configured server to listen on port 8888
- Set notebook root directory
- Created missing notebook directory
- Started JupyterLab using custom configuration

---

## Commands Used

```bash
source /root/code/ml-env/bin/activate

jupyter lab --config=/root/code/jupyter_lab_config.py --allow-root --no-browser &
```

---

## Learning Outcome

- Learned JupyterLab server configuration
- Understood host binding concepts
- Configured notebook root paths
- Practiced troubleshooting ML development environments

---

## Real-World Relevance

JupyterLab is widely used for collaborative ML experimentation and interactive model development.
