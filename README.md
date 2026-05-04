# IT3040 Assignment 1 — Transliteration Accuracy Testing

## How to install dependencies

1. Make sure Python 3.11 or 3.12 is installed
2. Create and activate a virtual environment:

```cmd
python -m venv .venv
.venv\Scripts\activate
```

3. Install packages:

```cmd
pip install -r requirements.txt
playwright install chromium
```

## How to run the tests

```cmd
python "IT23687646 test_automation.py" --excel "IT23687646 Assignment 1 - Test cases.xlsx" --url "https://www.pixelssuite.com/chat-translator" --wait-ms 5000 --type-delay-ms 80 --slow-mo-ms 200 --save-every 1 --keep-open
```

Results are written back into the Excel file automatically.

## File descriptions

| File                                        | Description                                                                                                                                            |
| ------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `IT23687646 test_automation.py`             | Playwright automation script that reads inputs from the Excel file, tests the transliteration tool, and writes actual output and Pass/Fail status back |
| `IT23687646 Assignment 1 - Test cases.xlsx` | Excel file containing 50 negative test cases (columns A–H)                                                                                             |
| `requirements.txt`                          | Python package dependencies                                                                                                                            |
