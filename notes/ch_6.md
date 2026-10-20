# Conditional Statements in Python

Conditional statements allow a program to make decisions. They run different blocks of code depending on whether a condition is `True` or `False`.

Python provides three main conditional statements:

- `if`
- `elif`
- `else`

## 1. `if` Statement

The `if` statement runs a block of code when a condition is `True`.

### Syntax

```python
if condition:
    # Code runs if the condition is True
```

### Example

```python
x = 10

if x > 5:
    print("x is greater than 5")

# Output: x is greater than 5
```

**Explanation:** Since `10 > 5` is `True`, the message is printed.

---

## 2. `elif` Statement

The `elif` statement checks another condition if the previous condition is `False`. You can use multiple `elif` statements.

### Syntax

```python
if condition1:
    # Code for condition1
elif condition2:
    # Code for condition2
else:
    # Code runs if all conditions are False
```

### Example

```python
x = 10

if x > 15:
    print("x is greater than 15")
elif x > 5:
    print("x is greater than 5 but not greater than 15")
else:
    print("x is not greater than 5")

# Output: x is greater than 5 but not greater than 15
```

**Explanation:** The first condition is `False`, so Python checks the `elif` condition. Since `10 > 5` is `True`, its message is printed.

---

## 3. `else` Statement

The `else` statement runs when all the previous `if` and `elif` conditions are `False`.

### Syntax

```python
if condition:
    # Code runs if True
else:
    # Code runs if False
```

### Example

```python
x = 3

if x > 5:
    print("x is greater than 5")
else:
    print("x is not greater than 5")

# Output: x is not greater than 5
```

**Explanation:** Since `3 > 5` is `False`, the `else` block runs.

---

## 4. Quick Summary

| Statement | Purpose |
|---|---|
| `if` | Checks the first condition |
| `elif` | Checks another condition if previous conditions are False |
| `else` | Runs when all previous conditions are False |

### Important Notes

- Use a colon (`:`) after each condition.
- Indentation is required to define the code inside each block.
- Python executes only the first matching block in an `if`–`elif`–`else` chain.
- The `else` statement is optional.
- You can use multiple `elif` statements, but only one `if` is needed at the beginning.
---

<p align="center">
  <a href="./ch_5.md"><img src="https://img.shields.io/badge/⬅_Back-blue?style=for-the-badge" alt="Back"></a>
  </a>
  <a href="../README.md">
    <img src="https://img.shields.io/badge/🏠_Main_README-purple?style=for-the-badge" alt="Main README"/>
  </a>
  <a href="./ch_7.md"><img src="https://img.shields.io/badge/Forward_➡-green?style=for-the-badge" alt="Forward"></a>
</p>