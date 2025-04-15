
# 🧪 UI Automation Testing Framework (Selenium + PyTest)

This is a scalable and modular UI Test Automation Framework built with **Selenium WebDriver**, **PyTest**, and the **Page Object Model (POM)**. It supports parallel test execution, HTML reporting, Excel/JSON test data handling, reusable utilities, and environment-based configurations.
---

## 📦 Requirements

All dependencies are listed in `requirements.txt`:

```
selenium
pytest
pytest-html
pytest-xdist
pytest-rerunfailures
openpyxl
```

### Install them with:

```bash
pip install -r requirements.txt
```

### If you need to uninstall them, unnstall them with:

```bash
pip uninstall -r requirements.txt -y
```
---

## 📁 Project Structure

```
project-root/
│
├── tests/              # PyTest test cases
├── pages/              # Page Object Model classes
├── utilities/          # Reusable utilities (browser, waits, Excel, JSON, etc.)
├── reports/            # Auto-generated HTML test reports (created automatically)
├── screenshots/        # Captured screenshots on test failure (auto-created)
│
├── config.ini          # Runtime settings (URL, browser, timeout, etc.)
├── env.ini             # Environment-specific user credentials
├── pytest.ini          # PyTest markers and options
├── conftest.py         # Global fixtures and hooks
├── run_tests.py        # Custom Python test runner
├── requirements.txt    # Python package dependencies
└── README.md           # Project documentation
```

---

## ⚙️ Configuration Files

### 🔧 `config.ini`

Holds framework settings:

```ini
[DEFAULT]
base_url = https://example.com
browser = chrome
timeout = 10
parallel_threads = 1
headless = false
```

### 🔐 `env.ini`
You can create this file to stores your credentials or API keys
<br>Add this file to the .gitignore after creating<br>


```ini
[Section_Name]
username = YourUsername
password = YourPassword
```


### ⚙️ `pytest.ini`

Used to register markers and customize PyTest behavior:

```ini
[pytest]
addopts = -v --tb=short --html=reports/report.html --self-contained-html
testpaths = tests
python_files = test_*.py *_test.py
python_classes = Test*
python_functions = test_*

markers =
    smoke: mark test as part of smoke suite
    regression: mark test as part of regression suite
```


---

## 🛠️ Utility Modules

| Module                     | Description                                          |
|----------------------------|------------------------------------------------------|
| `browser_manager.py`       | Manages WebDriver using singleton pattern            |
| `browser_utilities.py`     | Browser-level actions (scrolling, tabs, alerts, etc.)|
| `excel_utilities.py`       | Read/write Excel test data using `openpyxl`          |
| `json_utilities.py`        | JSON file utilities for test data or configs         |
| `config_reader.py`         | Loads `.ini` configurations and environment variables|

---

## 📸 Reports & Screenshots

- ✅ **HTML reports** are saved to the `reports/` folder.
- 📷 **Screenshots** for failed tests are captured in `screenshots/`.

> These folders are created automatically at runtime if not present.


---

## ✅ Features

- ✅ Page Object Model structure
- ✅ Singleton driver instance
- ✅ Parallel test execution (`pytest-xdist`)
- ✅ HTML reports (`pytest-html`)
- ✅ Test tagging support (`@pytest.mark.smoke`)
- ✅ Screenshot on failure (via `conftest.py`)
- ✅ Excel & JSON test data handling
- ✅ Custom Python test runner (`run_tests.py`)

---

## 👨‍💻 Maintainer

Developed and maintained by - [<b>Faruk Altay<b>](https://github.com/faruk109).

---

> 🔄 Feel free to fork, improve, and contribute to this framework.
