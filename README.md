### Mamram rules

# 🚀 CI Pipeline with GitHub Actions

This project includes a minimal **CI workflow** using **GitHub Actions** that runs a custom shell script (`test.sh`) on every code push.

---
## 🔧 Workflow Overview

* **Location:** `.github/workflows/ci.yml`
* **Trigger:** Every `push` to any branch

---

## ✅ What the Workflow Does

1. **Check out the repository**
   Uses `actions/checkout@v3` to clone the repository code.

2. **Make `test.sh` executable**
   Runs `chmod +x ./test.sh` to ensure the script has execution permissions.

3. **Run the test script**
   Executes `./test.sh`, allowing custom logic like tests, builds, or other validations.

---

## 📁 Example Workflow File

```yaml
name: CI Pipeline

on: [push]

jobs:
  ci-job:
    runs-on: ubuntu-latest
    steps:
      - name: Check out repository
        uses: actions/checkout@v3

      - name: Make test.sh executable
        run: chmod +x ./test.sh

      - name: Run test script
        run: ./test.sh
```

---

## 💡 Requirements

* A `test.sh` file must exist in the root of your repository.
* The script should contain valid executable commands (e.g., build steps, test suites).
