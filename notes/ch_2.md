
# Python Data Types

Data types define the kind of values a variable can store and the operations that can be performed on them.

## Common Data Types

| Data Type   | Description                      | Example                    |
| ----------- | -------------------------------- | -------------------------- |
| `int`       | Whole numbers                    | `x = 10`                   |
| `float`     | Decimal numbers                  | `x = 3.14`                 |
| `complex`   | Complex numbers                  | `x = 2 + 3j`               |
| `str`       | Text                             | `x = "Hello"`              |
| `list`      | Ordered, changeable collection   | `x = [1, 2, 3]`            |
| `tuple`     | Ordered, unchangeable collection | `x = (1, 2, 3)`            |
| `dict`      | Key-value pairs                  | `x = {"name": "John"}`     |
| `set`       | Unique elements                  | `x = {1, 2, 3}`            |
| `frozenset` | Unchangeable set                 | `x = frozenset([1, 2, 3])` |
| `bool`      | `True` or `False`                | `x = True`                 |
| `bytes`     | Immutable byte sequence          | `x = b"Hello"`             |
| `bytearray` | Mutable byte sequence            | `x = bytearray(b"Hello")`  |
| `NoneType`  | Represents no value              | `x = None`                 |

## Custom Data Types

Custom data types can be created using classes and objects in Python.


# Python Strings, Numbers, and Regular Expressions

## 1. String Operations

### String Concatenation

Combines two or more strings using `+`.

```python
str1 = "Hello"
str2 = "World"

result = str1 + " " + str2
print(result)  # Output: Hello World
```

### String Length

Returns the number of characters using `len()`.

```python
text = "Python is awesome"

print(len(text))  # Output: 17
```

### Uppercase and Lowercase

Converts text to uppercase or lowercase.

```python
text = "Python is awesome"

print(text.upper())  # Output: PYTHON IS AWESOME
print(text.lower())  # Output: python is awesome
```

### Replace Text

Replaces a specified part of a string.

```python
text = "Python is awesome"

new_text = text.replace("awesome", "great")
print(new_text)  # Output: Python is great
```

### Split a String

Converts a string into a list of words.

```python
text = "Python is awesome"

words = text.split()
print(words)  # Output: ['Python', 'is', 'awesome']
```

### Remove Extra Spaces

Removes leading and trailing whitespace.

```python
text = "   Python is awesome   "

print(text.strip())  # Output: Python is awesome
```

### Check for a Substring

Checks whether a specific word exists in a string using `in`.

```python
text = "Python is awesome"
substring = "is"

if substring in text:
    print("Substring found")
else:
    print("Substring not found")

# Output: Substring found
```

---

## 2. Numeric Operations

### Float Arithmetic

Performs basic arithmetic operations on decimal numbers.

```python
num1 = 5.0
num2 = 2.5

print(num1 + num2)  # Output: 7.5
print(num1 - num2)  # Output: 2.5
print(num1 * num2)  # Output: 12.5
print(num1 / num2)  # Output: 2.0
```

### Rounding Numbers

Rounds a number to a specified number of decimal places.

```python
number = 3.14159265359

print(round(number, 2))  # Output: 3.14
```

### Integer Division

`//` returns the quotient without the fractional part.

```python
num1 = 10
num2 = 3

print(num1 // num2)  # Output: 3
```

### Modulus

`%` returns the remainder after division.

```python
print(10 % 3)  # Output: 1
```

### Absolute Value

`abs()` returns the absolute value of a number.

```python
print(abs(-7))  # Output: 7
```

---

## 3. Regular Expressions (`re`)

The `re` module is used to search, match, replace, and split text using patterns.

### Search for a Pattern

`re.search()` finds the first matching pattern anywhere in the string.

```python
import re

text = "The quick brown fox"
pattern = r"brown"

result = re.search(pattern, text)

if result:
    print("Pattern found:", result.group())
else:
    print("Pattern not found")

# Output: Pattern found: brown
```

**Note:** `` .group() `` Returns the actual substring that was matched.

### Match at the Beginning

`re.match()` checks for a pattern only at the beginning of the string.

```python
import re

text = "The quick brown fox"
pattern = r"quick"

result = re.match(pattern, text)

if result:
    print("Match found:", result.group())
else:
    print("No match")

# Output: No match
```

**Note:** The result is `No match` because `quick` does not appear at the beginning of the string.

### Replace a Pattern

`re.sub()` replaces all matching occurrences by default.

```python
import re

text = "The brown fox and brown dog"

new_text = re.sub(r"brown", "red", text)

print(new_text)
# Output: The red fox and red dog
```

### Split Using a Pattern

`re.split()` splits a string wherever the pattern matches.

```python
import re

text = "apple,banana,orange,grape"

result = re.split(r",", text)

print(result)
# Output: ['apple', 'banana', 'orange', 'grape']
```

---

## Quick Summary

| Function / Operator | Purpose                                |
| ------------------- | -------------------------------------- |
| `+`                 | Join strings or add numbers            |
| `len()`             | Count characters or items              |
| `.upper()`          | Convert text to uppercase              |
| `.lower()`          | Convert text to lowercase              |
| `.replace()`        | Replace text                           |
| `.split()`          | Split a string into a list             |
| `.strip()`          | Remove leading and trailing whitespace |
| `in`                | Check whether a value exists           |
| `round()`           | Round a number                         |
| `//`                | Floor division                         |
| `%`                 | Get the remainder                      |
| `abs()`             | Get the absolute value                 |
| `re.search()`       | Find a pattern anywhere                |
| `re.match()`        | Match a pattern at the beginning       |
| `re.sub()`          | Replace matching patterns              |
| `re.split()`        | Split text using a pattern             |

---

<p align="center">
  <a href="./ch_1.md"><img src="https://img.shields.io/badge/⬅_Back-blue?style=for-the-badge" alt="Back"></a>
  <a href="./ch_3.md"><img src="https://img.shields.io/badge/Forward_➡-green?style=for-the-badge" alt="Forward"></a>
</p>