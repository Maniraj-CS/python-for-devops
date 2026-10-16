# Python Lists and Tuples

## 1. What is a List?

A list is a data structure used to store multiple items in a single variable.

Lists are **ordered and mutable**, which means you can access items by their position and change the list after creating it. A list can contain different data types.

### Creating a List

```python
my_list = [1, 2, 3, "apple", "banana"]

print(my_list)
# Output: [1, 2, 3, 'apple', 'banana']
```

**DevOps Example:**

Store the names of servers where an application needs to be deployed.

```python
servers = ["web-01", "web-02", "db-01"]

print(servers)
# Output: ['web-01', 'web-02', 'db-01']
```

### Accessing List Elements

List indexing starts from `0`.

```python
servers = ["web-01", "web-02", "db-01"]

print(servers[0])   # Output: web-01
print(servers[2])   # Output: db-01
print(servers[-1])  # Output: db-01 (last element)
```

### Finding List Length

Use `len()` to count the number of elements.

```python
servers = ["web-01", "web-02", "db-01"]

print(len(servers))  # Output: 3
```

This can help count the number of servers in a deployment list.

### Adding Elements

Use `append()` to add an element at the end.

```python
servers = ["web-01", "web-02"]

servers.append("web-03")

print(servers)
# Output: ['web-01', 'web-02', 'web-03']
```

### Removing Elements

Use `remove()` to remove the first matching value.

```python
servers = ["web-01", "web-02", "db-01"]

servers.remove("web-02")

print(servers)
# Output: ['web-01', 'db-01']
```

`remove()` raises a `ValueError` if the specified value does not exist in the list.

### List Slicing

Slicing extracts part of a list using `list[start:stop]`. The stop index is not included.

```python
my_list = [10, 20, 30, 40, 50]

print(my_list[1:4])
# Output: [20, 30, 40]
```

**DevOps Example:**

```python
servers = ["web-01", "web-02", "web-03", "db-01"]

print(servers[0:3])
# Output: ['web-01', 'web-02', 'web-03']
```

This extracts the first three servers from the list.

### Combining Lists

Use `+` to combine two lists into a new list.

```python
development_servers = ["dev-01", "dev-02"]
production_servers = ["prod-01", "prod-02"]

all_servers = development_servers + production_servers

print(all_servers)
# Output: ['dev-01', 'dev-02', 'prod-01', 'prod-02']
```

### Sorting a List

Use `sort()` to sort list elements.

```python
numbers = [4, 1, 3, 2]

numbers.sort()
print(numbers)  # Output: [1, 2, 3, 4]

numbers.sort(reverse=True)
print(numbers)  # Output: [4, 3, 2, 1]
```

**DevOps Example:**

```python
servers = ["web-03", "web-01", "web-02"]

servers.sort()
print(servers)
# Output: ['web-01', 'web-02', 'web-03']
```

**Note:** `sort()` changes the original list. By default, strings are sorted alphabetically.

### Checking for an Element

Use `in` to check whether an element exists in a list.

```python
servers = ["web-01", "web-02", "db-01"]

print("web-01" in servers)  # Output: True
print("web-05" in servers)  # Output: False
```

This checks whether a server is present in the list. It does not check whether the server is actually running.

---

## 2. What is a Tuple?

A tuple is a data structure used to store multiple items in a single variable.

Tuples are **ordered and immutable**, which means their elements cannot be added, removed, or replaced after creation.

### Creating a Tuple

```python
my_tuple = (1, 2, "apple", "banana")

print(my_tuple)
# Output: (1, 2, 'apple', 'banana')
```

**DevOps Example:**

Store a server's basic configuration.

```python
server_config = ("web-01", "192.168.1.10", 80)

print(server_config)
# Output: ('web-01', '192.168.1.10', 80)
```

### Accessing Tuple Elements

Tuple indexing starts from `0`, just like lists.

```python
server_config = ("web-01", "192.168.1.10", 80)

print(server_config[0])  # Output: web-01
print(server_config[1])  # Output: 192.168.1.10
print(server_config[2])  # Output: 80
```

### Finding Tuple Length

Use `len()` to count the elements.

```python
server_config = ("web-01", "192.168.1.10", 80)

print(len(server_config))  # Output: 3
```

The tuple contains three elements: a server name, an IP address, and a port.

### Tuple Packing and Unpacking

**Packing** means storing multiple values in a tuple. **Unpacking** means assigning tuple elements to separate variables.

```python
server_config = ("web-01", "192.168.1.10", 80) # Packing

hostname, ip_address, port = server_config    # Unpacking

print(hostname)     # Output: web-01
print(ip_address)   # Output: 192.168.1.10
print(port)         # Output: 80
```

The number of variables must match the number of tuple elements when unpacking.

### Combining Tuples

Use `+` to create a new tuple by combining existing tuples.

```python
server_details = ("web-01", "192.168.1.10")
server_settings = (80, "running")

full_config = server_details + server_settings

print(full_config)
# Output: ('web-01', '192.168.1.10', 80, 'running')
```

### Checking for an Element

Use `in` to check whether a value exists in a tuple.

```python
allowed_ports = (22, 80, 443)

print(22 in allowed_ports)   # Output: True
print(3306 in allowed_ports) # Output: False
```

This checks membership in a Python tuple. It does not configure or enforce firewall rules.

### Returning Multiple Values from a Function

Python functions can return multiple values, which are commonly packed into a tuple.

```python
def get_server_info():
    return "web-01", "running"

hostname, status = get_server_info()

print(hostname)  # Output: web-01
print(status)    # Output: running
```

A function can return multiple pieces of information, such as a server name and its reported status.

---

## 3. Lists vs Tuples

Both lists and tuples store multiple items in an ordered collection, but they have important differences.

| Feature | List | Tuple |
|---|---|---|
| Syntax | `[1, 2, 3]` | `(1, 2, 3)` |
| Ordered | Yes | Yes |
| Mutable | Yes | No |
| Add or remove items | Yes | No |
| Access by index | Yes | Yes |
| Supports slicing | Yes | Yes |
| Common use | Data that changes | Data that should remain fixed |
| DevOps example | Deployment target list | Fixed server configuration |

### Mutability Example

**List — elements can be changed:**

```python
numbers = [1, 2, 3]
numbers[0] = 100

print(numbers)  # Output: [100, 2, 3]
```

**Tuple — elements cannot be changed:**

```python
numbers = (1, 2, 3)

# numbers[0] = 100  # Raises TypeError
```

### When Should You Use Them?

- **List:** Use it when you need to add, remove, or update items, such as deployment targets, server names, or tasks.
- **Tuple:** Use it when you want an ordered collection that should not be changed, such as a fixed set of configuration values or coordinates `(x, y)`.

**Important:** Tuples are not always automatically faster or smaller in every situation. Choose a list or tuple mainly based on whether the collection needs to change.

---

## 4. Quick Summary

- Lists use square brackets `[]` and are mutable.
- Tuples use parentheses `()` and are immutable.
- Indexing starts from `0` in both.
- `len()` returns the number of elements.
- `in` checks whether an element exists.
- Slicing extracts a part of a list or tuple.
- `append()`, `remove()`, and `sort()` are common list methods.
- Tuple unpacking assigns elements to separate variables.
- Lists are useful for collections that change, such as deployment targets.
- Tuples are useful for grouped values that should remain fixed, such as server configuration.

---

<p align="center">
  <a href="./ch_7.md">
    <img src="https://img.shields.io/badge/⬅_Back-blue?style=for-the-badge" alt="Back" />
  </a>
  <a href="./ch_9.md">
    <img src="https://img.shields.io/badge/Forward_➡-green?style=for-the-badge" alt="Forward" />
  </a>
</p>