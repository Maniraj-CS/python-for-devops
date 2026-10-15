# Introduction to Operators in Python

Operators are symbols or keywords used to perform operations on values and variables.

Python has different types of operators for calculations, comparisons, logical decisions, and more.

## Types of Operators

- **Arithmetic Operators:** Perform mathematical calculations.
- **Assignment Operators:** Assign or update variable values.
- **Relational Operators:** Compare two values and return `True` or `False`.
- **Logical Operators:** Combine or reverse conditions.
- **Identity Operators:** Check whether two variables refer to the same object.
- **Membership Operators:** Check whether a value exists in a collection.
- **Bitwise Operators:** Perform operations on the bits of integers.

---

## 1. Arithmetic Operators

Arithmetic operators are used to perform mathematical calculations.

| Operator | Meaning | Example | Result |
|---|---|---|---|
| `+` | Addition | `10 + 5` | `15` |
| `-` | Subtraction | `10 - 5` | `5` |
| `*` | Multiplication | `10 * 5` | `50` |
| `/` | Division | `10 / 3` | `3.333...` |
| `//` | Floor division | `10 // 3` | `3` |
| `%` | Remainder | `10 % 3` | `1` |
| `**` | Power | `2 ** 3` | `8` |

### Example

```python
a = 10
b = 3

print(a + b)   # 13
print(a - b)   # 7
print(a * b)   # 30
print(a / b)   # 3.333...
print(a // b)  # 3
print(a % b)   # 1
print(a ** b)  # 1000
```

**Note:** `//` rounds the result down to the nearest whole number. For negative numbers, it rounds toward negative infinity.

---

## 2. Assignment Operators

Assignment operators assign values to variables or update their existing values.

| Operator | Example | Equivalent To |
|---|---|---|
| `=` | `x = 10` | Assign `10` to `x` |
| `+=` | `x += 5` | `x = x + 5` |
| `-=` | `x -= 5` | `x = x - 5` |
| `*=` | `x *= 5` | `x = x * 5` |
| `/=` | `x /= 5` | `x = x / 5` |
| `//=` | `x //= 5` | `x = x // 5` |
| `%=` | `x %= 5` | `x = x % 5` |
| `**=` | `x **= 2` | `x = x ** 2` i.e `x<sup>2</sup>` |

### Example

```python
x = 10

x += 5
print(x)  # 15

x *= 2
print(x)  # 30

x -= 10
print(x)  # 20

y = 10

y **= 2
print(y) # 100
```

---

## 3. Relational (Comparison) Operators

Comparison operators compare two values and return `True` or `False`.

| Operator | Meaning | Example | Result |
|---|---|---|---|
| `==` | Equal to | `5 == 5` | `True` |
| `!=` | Not equal to | `5 != 3` | `True` |
| `>` | Greater than | `5 > 3` | `True` |
| `<` | Less than | `5 < 3` | `False` |
| `>=` | Greater than or equal to | `5 >= 5` | `True` |
| `<=` | Less than or equal to | `3 <= 5` | `True` |

### Example

```python
a = 10
b = 5

print(a == b)  # False
print(a != b)  # True
print(a > b)   # True
print(a < b)   # False
print(a >= 10) # True
print(b <= 5)  # True
```

**Remember:** `=` assigns a value, while `==` compares two values.

---

## 4. Logical Operators

Logical operators combine conditions or reverse a condition.

| Operator | Meaning |
|---|---|
| `and` | `True` when both conditions are true |
| `or` | `True` when at least one condition is true |
| `not` | Reverses the Boolean result |

### Example

```python
age = 20

print(age > 18 and age < 30)  # True
print(age < 18 or age == 20)  # True
print(not age > 18)           # False
```

---

## 5. Identity Operators

Identity operators check whether two variables refer to the **same object**, not just whether their values are equal.

| Operator | Meaning |
|---|---|
| `is` | Both variables refer to the same object |
| `is not` | Variables refer to different objects |

### Example

```python
a = [1, 2, 3]
b = a
c = [1, 2, 3]

print(a is b)   # True
print(a is c)   # False
print(a == c)   # True
```

**Explanation:**
- `b = a` makes `b` refer to the same list as `a`.
- `c` is a separate list with the same values.
- `==` compares values, while `is` checks object identity.

---

## 6. Membership Operators

Membership operators check whether a value exists in a sequence or collection.

| Operator | Meaning |
|---|---|
| `in` | The value exists |
| `not in` | The value does not exist |

### Example

```python
fruits = ["apple", "banana", "mango"]

print("apple" in fruits)       # True
print("grape" not in fruits)   # True
print("grape" in fruits)      # False
```

Membership operators also work with strings.

```python
text = "Python"

print("Py" in text)      # True
print("Java" not in text) # True
```

---

## 7. Bitwise Operators

Bitwise operators work on the binary bits of integers.

| Operator | Meaning |
|---|---|
| `&` | Bitwise AND |
| `\|` | Bitwise OR |
| `^` | Bitwise XOR |
| `~` | Bitwise NOT |
| `<<` | Left shift |
| `>>` | Right shift |

### Example

```python
a = 5  # Binary: 0101
b = 3  # Binary: 0011

print(a & b)   # 1
print(a | b)   # 7
print(a ^ b)   # 6
print(~a)      # -6
print(a << 1)  # 10
print(a >> 1)  # 2
```

**Simple explanation:**
- `&` returns `1` where both bits are `1`.
- `|` returns `1` where at least one bit is `1`.
- `^` returns `1` where the bits are different.
- `~` flips the bits according to Python's integer representation.
- `<<` shifts bits to the left.
- `>>` shifts bits to the right.

---

## 8. Operator Precedence

Operator precedence decides which operation is performed first in an expression.

### Example

```python
result = 2 + 3 * 4
print(result)  # 14
```

Multiplication happens before addition.

Use parentheses `()` to control the order.

```python
result = (2 + 3) * 4
print(result)  # 20
```

**Tip:** When an expression is complex, use parentheses to make the order clear.

---

## Quick Revision

| Category | Operators |
|---|---|
| Arithmetic | `+`, `-`, `*`, `/`, `//`, `%`, `**` |
| Assignment | `=`, `+=`, `-=`, `*=`, `/=`, `//=`, `%=`, `**=` |
| Comparison | `==`, `!=`, `>`, `<`, `>=`, `<=` |
| Logical | `and`, `or`, `not` |
| Identity | `is`, `is not` |
| Membership | `in`, `not in` |
| Bitwise | `&`, `\|`, `^`, `~`, `<<`, `>>` |

---

<p align="center">
  <a href="./ch_4.md">
    <img src="https://img.shields.io/badge/⬅_Back-blue?style=for-the-badge" alt="Back" />
  </a>
  <a href="./ch_6.md">
    <img src="https://img.shields.io/badge/Forward_➡-green?style=for-the-badge" alt="Forward" />
  </a>
</p>