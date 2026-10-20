# Python Project — List Files in Multiple Folders

## 1. Project Overview

This project lists the files and directories inside multiple folders provided by the user.

It also handles common errors, such as a folder that does not exist or a folder that cannot be accessed due to permission restrictions.


## 2. Complete Code

```python
import os


def list_files_in_folder(folder_path):
    try:
        files = os.listdir(folder_path)
        return files, None

    except FileNotFoundError:
        return None, "Folder not found"

    except PermissionError:
        return None, "Permission denied"


def main():
    folder_paths = input(
        "Enter a list of folder paths separated by spaces: "
    ).split()

    for folder_path in folder_paths:
        files, error_message = list_files_in_folder(folder_path)

        if error_message is None:
            print(f"Contents of {folder_path}:")

            for file in files:
                print(file)
        else:
            print(f"Error in {folder_path}: {error_message}")


if __name__ == "__main__":
    main()
```

## 3. Understanding the Code

### Step 1: Import the OS Module

```python
import os
```

The `os` module provides functions for interacting with the operating system.

Here, we use `os.listdir()` to get the names of entries inside a folder.

**DevOps use:** This type of operation can be useful when building scripts to inspect directories containing application files, configuration files, or logs.

### Step 2: Create a Function

```python
def list_files_in_folder(folder_path):
```

- `def` defines a function.
- `list_files_in_folder` is the function name.
- `folder_path` is a parameter that receives a folder path.

For example:

```python
list_files_in_folder("/var/log")
```

This passes `/var/log` to the function. The function attempts to list that directory's contents.

### Step 3: List Directory Contents

```python
files = os.listdir(folder_path)
return files, None
```

`os.listdir(folder_path)` returns a list containing the names of entries inside the specified directory.

For example, a directory might contain:

```python
["syslog", "auth.log", "application.log"]
```

The function returns two values:

- `files` — the list of entries.
- `None` — indicates that no error was reported.

**Important:** `os.listdir()` returns both files and subdirectories. It does not return only files.

### Step 4: Handle Errors

```python
except FileNotFoundError:
    return None, "Folder not found"

except PermissionError:
    return None, "Permission denied"
```

The `try` block contains code that may raise an exception. The `except` blocks handle specific errors.

| Exception | Meaning |
|---|---|
| `FileNotFoundError` | The specified path does not exist. |
| `PermissionError` | The program does not have sufficient permission to access the directory. |

When an error occurs, the function returns:

```python
None, "Folder not found"
```

The first value is `None` because there is no file list to return. The second value describes the error.

Other exceptions may still occur; this example handles only the two listed errors.

### Step 5: Get User Input

```python
folder_paths = input(
    "Enter a list of folder paths separated by spaces: "
).split()
```

The `input()` function reads text entered by the user.

The `.split()` method separates that text at whitespace and returns a list.

For example, the user enters:

```text
/var/log /etc /tmp
```

Python creates:

```python
folder_paths = ["/var/log", "/etc", "/tmp"]
```

Now the program can process each path separately.

**Note:** This input format does not support paths containing spaces as a single path.

### Step 6: Iterate Over the Folder Paths

```python
for folder_path in folder_paths:
    files, error_message = list_files_in_folder(folder_path)
```

The `for` loop processes one path at a time.

For each path, the function returns two values, which are assigned to:

- `files`
- `error_message`

This is an example of **tuple unpacking** because the function returns two values.

### Step 7: Display Results or Errors

```python
if error_message is None:
    print(f"Contents of {folder_path}:")

    for file in files:
        print(file)
else:
    print(f"Error in {folder_path}: {error_message}")
```

If `error_message` is `None`, the program displays the directory entries.

The inner `for` loop prints each entry on a separate line.

Otherwise, it displays the error message.

Checking `error_message is None` is more reliable than checking `if files`, because an existing empty directory returns an empty list (`[]`), which is a valid result rather than an error.

### Step 8: Main Entry Point

```python
if __name__ == "__main__":
    main()
```

This condition runs `main()` when the Python file is executed directly.

It prevents `main()` from running automatically when the file is imported as a module by another Python program.


## 5. Run the Project

Save the code in a file named `list_folders.py`.

Run it from your terminal:

```bash
python3 list_folders.py
```

Example input:

```text
Enter a list of folder paths separated by spaces: /tmp /var/log /folder-does-not-exist
```

Example output (the actual entries depend on your system):

```text
Contents of /tmp:
some-file
some-directory

Contents of /var/log:
syslog
auth.log

Error in /folder-does-not-exist: Folder not found
```

The file names above are illustrative; your output may differ.

## 6. Important Concepts Summary

| Concept | Purpose |
|---|---|
| `import os` | Access operating system functions |
| `os.listdir()` | List entries in a directory |
| `def` | Define a reusable function |
| `return` | Send results back to the caller |
| `try` | Run code that may raise an exception |
| `except` | Handle a specific exception |
| `input()` | Read terminal input |
| `.split()` | Convert space-separated input into a list |
| `for` | Process each folder or entry |
| Tuple unpacking | Assign multiple returned values to variables |
| `if` / `else` | Choose which output to display |
| `is None` | Check whether a value is `None` |
| `__name__` | Identify how a Python module is being executed |

## 7. Practice Tasks

1. Test the program with three existing directories.
2. Include one nonexistent path and observe the error handling.
3. Try an empty directory and verify that it is not reported as an error.
4. Modify the program to display the total number of entries in each directory using `len(files)`.
5. Extend the program to distinguish files from subdirectories using `os.path.isfile()` and `os.path.isdir()`.

**DevOps connection:** Directory inspection is a useful building block for automation scripts that examine application directories, log locations, and configuration paths. This project is a starting point, not a complete production log-management tool.

---

<p align="center">
  <a href="./ch_8.md">
    <img src="https://img.shields.io/badge/⬅_Back-blue?style=for-the-badge" alt="Back" />
  </a>
  </a>
  <a href="../README.md">
    <img src="https://img.shields.io/badge/🏠_Main_README-purple?style=for-the-badge" alt="Main README"/>
  </a>
  <a href="./ch_10.md">
    <img src="https://img.shields.io/badge/Forward_➡-green?style=for-the-badge" alt="Forward" />
  </a>
</p>