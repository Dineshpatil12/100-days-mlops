# Day 09 - Cookiecutter ML Template

## 🎯 Task

Fixed a broken Cookiecutter template and generated a reusable ML project structure for xFusionCorp Industries.

---

# 🛠️ Commands Used

```bash id="ui8f1j"
cd /root/code/mlops-template
```

```bash id="w0q6k5"
find .
```

```bash id="z9t2ha"
mkdir -p "{{cookiecutter.project_name}}"/{data,models,src,tests}
```

```bash id="jl9vxr"
vi cookiecutter.json
```

```bash id="s8m1fe"
vi "{{cookiecutter.project_name}}"/README.md
```

```bash id="3u6xpw"
vi "{{cookiecutter.project_name}}"/requirements.txt
```

```bash id="j2w4ce"
cookiecutter /root/code/mlops-template/ -o /root/code/ --no-input project_name=churn-model ml_framework=sklearn
```

```bash id="jyrgnt"
cd /root/code/churn-model
```

```bash id="v8u2xj"
cat requirements.txt
```

```bash id="h4b0ln"
cat README.md
```

```bash id="q5d3ma"
find .
```

---

# 📚 Learning

* Fixed Cookiecutter rendering issues
* Used Jinja2 template variables
* Created dynamic requirements logic
* Generated reusable ML project structure
* Learned variables are case-sensitive in Cookiecutter

