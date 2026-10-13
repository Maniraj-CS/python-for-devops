# Python Functions, Modules, and Packages

## 1. Functions

A function is a block of code that performs a specific task. Functions help reuse code without writing it again.

Use the `def` keyword to create a function.

### Example

```python
def greet(name):
    return f"Hello, {name}!"

message = greet("Alice")
print(message)

# Output: Hello, Alice!
```

**Key points:**
- `def` is used to create a function.
- `name` is a parameter that receives a value.
- `return` sends a result back.
- `greet("Alice")` calls the function.

---

## 2. Modules

A module is a Python file that contains code such as functions, variables, and classes. Modules help organize code into separate files.

### Example

Create a file named `my_module.py`:

```python
def square(x):
    return x ** 2

pi = 3.14159
```

Now, use this module in another Python file:

```python
import my_module

print(my_module.square(5))  # Output: 25
print(my_module.pi)         # Output: 3.14159
```

**Key points:**
- A Python file can be used as a module.
- `import` allows you to use code from another module.
- Use `module_name.function_name()` to call its function.

---

## 3. Packages

A package is a directory that groups related Python modules together. Packages help organize large projects.

### Example Structure

```text
my_package/
├── __init__.py
├── module1.py
└── module2.py
```

- `my_package/` is the package directory.
- `module1.py` and `module2.py` are Python modules.
- `__init__.py` is commonly used to mark a directory as a package and can contain initialization code.

### Import a Module from a Package

Suppose `module1.py` contains:

```python
def greet():
    return "Hello from module1!"
```

Use it in another Python file:

```python
from my_package import module1

print(module1.greet())

# Output: Hello from module1!
```

---

## 4. How to Import Modules

Python provides different ways to import code.

### Import the Entire Module

```python
import math

print(math.sqrt(16))  # Output: 4.0
```

### Import a Specific Function or Variable

```python
from math import pi

print(pi)
```

### Use an Alias

An alias gives a module a shorter name.

```python
import math as m

print(m.sqrt(25))  # Output: 5.0
```

---

## 5. Python Environments

A Python environment is the setup used to run Python programs. It includes the Python interpreter and the libraries available to your project.

### Types of Environments

- **System Environment:** Uses the Python installation available on your system.
- **Virtual Environment:** Creates an isolated environment for a project, helping keep its dependencies separate from other projects.

### Create a Virtual Environment

```bash
python3 -m venv myenv
```

### Activate the Environment

**Linux / macOS:**

```bash
source myenv/bin/activate
```

**Windows (Command Prompt):**

```cmd
myenv\Scripts\activate.bat
```

**Windows (PowerShell):**

```powershell
.\myenv\Scripts\Activate.ps1
```

### Install a Package

After activating the environment, install a library using `pip`.

```bash
python -m pip install requests
```

### Deactivate the Environment

```bash
deactivate
```

**Why use virtual environments?**

- Keep project dependencies separate.
- Avoid conflicts between library versions.
- Make projects easier to manage.

---

<p align="center">
  <a href="./ch_2.md"><img src="https://img.shields.io/badge/⬅_Back-blue?style=for-the-badge" alt="Back"></a>
  <a href="./ch_4.md"><img src="https://img.shields.io/badge/Forward_➡-green?style=for-the-badge" alt="Forward"></a>
</p>