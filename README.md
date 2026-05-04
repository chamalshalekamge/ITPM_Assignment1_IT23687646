# IT3040 Assignment 1 — Transliteration Accuracy Testing

**Repository:** https://github.com/chamalshalekamge/ITPM_Assignment1_IT23687646

---

## Project Description

This project is submitted for **IT3040 — IT Project Management**, Assignment 1, Option 1: Frontend-Only Automated Testing.

The goal is to evaluate the **transliteration accuracy** of the online Singlish-to-Sinhala converter tool at [pixelssuite.com/chat-translator](https://www.pixelssuite.com/chat-translator) using **negative test cases** — inputs that are designed to expose limitations, edge cases, and failure modes of the tool.

### What this project does

- Automates a real Chromium browser using **Playwright** (Python)
- Reads **50 negative test cases** from an Excel spreadsheet (columns: Test Case ID, Input length type, Singlish input, Expected output)
- Types each Singlish input into the web tool and captures the actual Sinhala output
- Compares actual output against expected output and records **PASS / FAIL** status
- Writes results back into the Excel file automatically (columns: Actual output, Status)

### Why negative test cases?

Negative testing verifies how a system behaves when given inputs it is **expected to handle incorrectly**. For a transliteration tool, this means inputs such as ambiguous words, mixed-language sentences, idiomatic expressions, and long or complex sentences — cases where the tool's output is known to deviate from the correct Sinhala.

### Tools & technologies used

| Tool / Library      | Purpose                                                              |
| ------------------- | -------------------------------------------------------------------- |
| Python 3.10–3.12    | Programming language                                                 |
| Playwright (Python) | Browser automation — controls Chromium to interact with the web tool |
| openpyxl            | Reading and writing the `.xlsx` Excel test case file                 |
| Microsoft Excel     | Test case management (50 rows, 8 columns)                            |
| Git / GitHub        | Version control and public submission of the automation project      |

---

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
