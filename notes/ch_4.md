# Command-Line Arguments and Environment Variables

## 1. Command-Line Arguments

Command-line arguments are values passed to a Python program when running it from the terminal.

Python uses the `sys` module to read these arguments through `sys.argv`.

### Example: `main.py`

```python
import sys

def add(num1, num2):
    return num1 + num2

num1 = float(sys.argv[1])
operation = sys.argv[2]
num2 = float(sys.argv[3])

if operation == "add":
    result = add(num1, num2)
    print(result)
```

### Run the Program

```bash
python main.py 5.7 add 88.9
```

**Output:**
```text
94.6
```

### How It Works

- `sys.argv` stores the command-line arguments in a list.
- `sys.argv[0]` is the script name (`main.py`).
- `sys.argv[1]` is `5.7`.
- `sys.argv[2]` is `add`.
- `sys.argv[3]` is `88.9`.
- Arguments are received as strings, so `float()` converts numeric values into numbers.

### Why Can't We Use `operation(num1, num2)`?

The value of `operation` is a string, such as `"add"`. A string is not a function, so it cannot be called directly.

Use an `if` condition to check the operation and call the correct function.

```python
if operation == "add":
    result = add(num1, num2)
    print(result)
```

**Note:** This example supports only the `add` operation. Other operations can be added using `elif` conditions.

---

## 2. Environment Variables

Environment variables are named values stored outside the program. They are commonly used to provide configuration settings, such as application modes, file paths, and credentials.

Python uses the `os` module to access environment variables.

### Example: `main.py`

```python
import os

password = os.getenv("password")
print(password)
```

### Set and Read an Environment Variable

**Linux / macOS:**

```bash
export password="hello-maniraj"
python main.py
```

**Output:**
```text
hello-maniraj
```

### How It Works

- `export` sets an environment variable in the current shell.
- `os.getenv("password")` reads its value.
- If the variable does not exist, `os.getenv()` returns `None` by default.

### Important Security Note

Avoid putting real passwords or API keys directly in your code. Environment variables can help keep credentials out of source code, but they must still be protected from unauthorized access.

---

## 3. Quick Summary

| Concept | Purpose |
|---|---|
| `sys.argv` | Reads command-line arguments |
| `float()` | Converts a value into a floating-point number |
| `os.getenv()` | Reads an environment variable |
| `export` | Sets an environment variable in a shell |
| Command-line arguments | Pass input when starting a program |
| Environment variables | Provide configuration outside the code |

---

<p align="center">
  <a href="./ch_3.md"><img src="https://img.shields.io/badge/⬅_Back-blue?style=for-the-badge" alt="Back"></a>
  <a href="./ch_5.md"><img src="https://img.shields.io/badge/Forward_➡-green?style=for-the-badge" alt="Forward"></a>
</p>