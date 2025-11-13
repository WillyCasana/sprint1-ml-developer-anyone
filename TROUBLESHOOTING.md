# Troubleshooting Guide

## Issue: "ModuleNotFoundError: No module named 'pandas'"

This error occurs when the required Python packages are not installed in the Python environment that Jupyter is using.

### Solution:

**Step 1: Install all required packages**

Run this command in your terminal:

```bash
pip install pandas sqlalchemy requests matplotlib seaborn plotly numpy jupyter
```

**Step 2: Verify installation**

Check if pandas is installed:

```bash
python -c "import pandas; print(pandas.__version__)"
```

**Step 3: Restart Jupyter Kernel**

In VSCode:
1. Click on the "Restart" button in the Jupyter notebook toolbar
2. Or press `Ctrl+Shift+P` and search for "Jupyter: Restart Kernel"

**Step 4: Run the notebook again**

After restarting the kernel, try running the cells again.

---

## Alternative: Use Virtual Environment (Recommended)

If you continue having issues, create a virtual environment:

### For Windows:

```bash
# Create virtual environment
python -m venv venv

# Activate it
venv\Scripts\activate

# Install requirements
pip install -r requirements.txt

# Install Jupyter
pip install jupyter

# Run Jupyter
jupyter notebook
```

### For Linux/Mac:

```bash
# Create virtual environment
python -m venv venv

# Activate it
source venv/bin/activate

# Install requirements
pip install -r requirements.txt

# Install Jupyter
pip install jupyter

# Run Jupyter
jupyter notebook
```

---

## Common Issues:

### 1. Multiple Python Installations

If you have multiple Python versions installed, make sure you're using the correct one:

```bash
# Check Python version
python --version

# Use specific Python version
python3.9 -m pip install -r requirements.txt
```

### 2. Jupyter Using Different Python

In VSCode, select the correct Python interpreter:
1. Press `Ctrl+Shift+P`
2. Type "Python: Select Interpreter"
3. Choose the Python version where you installed the packages

### 3. Permission Issues

If you get permission errors, try:

```bash
pip install --user -r requirements.txt
```

---

## Verify Everything is Working:

Run this test script:

```python
# test_imports.py
try:
    import pandas
    print("✓ pandas installed")
except ImportError:
    print("✗ pandas NOT installed")

try:
    import sqlalchemy
    print("✓ sqlalchemy installed")
except ImportError:
    print("✗ sqlalchemy NOT installed")

try:
    import requests
    print("✓ requests installed")
except ImportError:
    print("✗ requests NOT installed")

try:
    import matplotlib
    print("✓ matplotlib installed")
except ImportError:
    print("✗ matplotlib NOT installed")

try:
    import seaborn
    print("✓ seaborn installed")
except ImportError:
    print("✗ seaborn NOT installed")

print("\nAll required packages are installed!")
```

Run it with:
```bash
python test_imports.py
```

---

## Still Having Issues?

1. Close VSCode completely
2. Reopen VSCode
3. Open the project folder
4. Run the installation command again
5. Restart the Jupyter kernel
6. Try running the notebook

---

## Contact Information

If problems persist, check:
- Python version compatibility (should be 3.9-3.12)
- Available disk space
- Internet connection for package downloads