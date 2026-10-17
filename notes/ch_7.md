# Python Loops for DevOps

## 1. For Loop

A `for` loop is used to repeat a block of code for each item in a sequence, such as a list, tuple, or string.

### Using `range()`

```python
for i in range(10):
    print("Hello DevOps")
```

**Output:**
```text
Hello DevOps
Hello DevOps
Hello DevOps
# Repeats 10 times
```

Here, `range(10)` generates numbers from `0` to `9`.

- Start: `0`
- Stop: `10` (not included)
- Total iterations: `10`

### Iterating Over a Tuple

```python
servers = ("server1", "server2", "server3")

for server in servers:
    print(server)
```

**Output:**
```text
server1
server2
server3
```

**DevOps Example:**

You can use a loop to process multiple servers during a deployment.

```python
servers = ("web-01", "web-02", "web-03")

for server in servers:
    print(f"Deploying application to {server}")
```

**Output:**
```text
Deploying application to web-01
Deploying application to web-02
Deploying application to web-03
```

## 2. While Loop

A `while` loop repeats a block of code as long as its condition is `True`.

```python
count = 0

while count < 5:
    print("Hello DevOps")
    count += 1
```

**Output:**
```text
Hello DevOps
Hello DevOps
Hello DevOps
Hello DevOps
Hello DevOps
```

Here:
- `count = 0` initializes the counter.
- `count < 5` checks the condition.
- `count += 1` increases the counter by one.
- When `count` reaches `5`, the loop stops.

**DevOps Example:**

Repeat a simulated health check three times.

```python
attempt = 1

while attempt <= 3:
    print(f"Checking application health: attempt {attempt}")
    attempt += 1
```

**Output:**
```text
Checking application health: attempt 1
Checking application health: attempt 2
Checking application health: attempt 3
```

This example simulates repeated checks. It does not actually check an application's health.

## 3. Break Statement

The `break` statement immediately stops the loop, even if the loop has more items to process.

```python
numbers = [1, 2, 3, 4, 5]

for number in numbers:
    if number == 3:
        break

    print(number)
```

**Output:**
```text
1
2
```

When `number` becomes `3`, `break` stops the loop. Numbers `3`, `4`, and `5` are not printed.

**DevOps Example:**

Stop processing servers when a server marked as failed is found.

```python
servers = [
    ("web-01", "running"),
    ("web-02", "running"),
    ("web-03", "failed"),
    ("web-04", "running")
]

for server, status in servers:
    if status == "failed":
        print(f"Failure detected on {server}")
        break

    print(f"{server} is {status}")
```

**Output:**
```text
web-01 is running
web-02 is running
Failure detected on web-03
```

This is a simulated example using predefined statuses.

## 4. Continue Statement

The `continue` statement skips the remaining code in the current iteration and moves to the next iteration.

```python
numbers = [1, 2, 3, 4, 5]

for number in numbers:
    if number == 3:
        continue

    print(number)
```

**Output:**
```text
1
2
4
5
```

When `number` is `3`, `continue` skips the `print()` statement for that iteration.

**DevOps Example:**

Skip log entries that are not errors.

```python
log_file = [
    "INFO: Operation successful",
    "ERROR: File not found",
    "DEBUG: Connection established",
    "ERROR: Database connection failed"
]

for line in log_file:
    if "ERROR" not in line:
        continue

    print(line)
```

**Output:**
```text
ERROR: File not found
ERROR: Database connection failed
```

## 5. Practice Exercise — Automating Log File Analysis

Suppose you have a list of log messages and want to display only the errors.

```python
log_file = [
    "INFO: Operation successful",
    "ERROR: File not found",
    "DEBUG: Connection established",
    "ERROR: Database connection failed"
]

for line in log_file:
    if "ERROR" in line:
        print(line)
```

**Output:**
```text
ERROR: File not found
ERROR: Database connection failed
```

### How It Works

1. The `for` loop reads each log message.
2. The `if` statement checks whether `"ERROR"` exists in the message.
3. If it exists, `print()` displays the message.
4. Other messages are ignored.

This is a simple example of filtering log messages. Real log analysis may also require reading files, handling timestamps, and managing large amounts of data.

## 6. Quick Summary

| Concept | Purpose |
|---|---|
| `for` | Iterates over items in a sequence |
| `range()` | Generates a sequence of numbers |
| `while` | Repeats while a condition is `True` |
| `break` | Stops the loop immediately |
| `continue` | Skips the current iteration |
| `if` inside a loop | Checks a condition for each iteration |

## 7. Practice Tasks

1. Create a list of five server names and print each name using a `for` loop.
2. Use `range()` to print numbers from `1` to `10`.
3. Use a `while` loop to simulate three application health checks.
4. Use `break` to stop processing when a server's status is `"failed"`.
5. Use `continue` to skip log messages containing `"DEBUG"`.
6. Modify the log analysis exercise to print only messages containing `"ERROR"` or `"WARNING"`.

---

<p align="center">
  <a href="./ch_6.md">
    <img src="https://img.shields.io/badge/⬅_Back-blue?style=for-the-badge" alt="Back">
  </a>
  <a href="./ch_8.md">
    <img src="https://img.shields.io/badge/Forward_➡-green?style=for-the-badge" alt="Forward">
  </a>
</p>