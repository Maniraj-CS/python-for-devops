# Python Lists and Tuples for DevOps

## 1. What is a List?

A list stores multiple items in a single variable. Lists are **ordered and mutable**, which means you can add, remove, or update items.

In DevOps, lists are useful for storing server names, IP addresses, Docker containers, and deployment tasks.

### Creating a List

```python
servers = ["web-01", "web-02", "db-01"]

print(servers)

# Output:
# ['web-01', 'web-02', 'db-01']
```

### Accessing List Elements

List indexing starts from `0`.

```python
servers = ["web-01", "web-02", "db-01"]

print(servers[0])   # web-01
print(servers[-1])  # db-01
```

**DevOps use case:** Access a specific server from a list.

### Finding the Number of Servers

Use `len()` to count the items.

```python
servers = ["web-01", "web-02", "db-01"]

print(len(servers))  # Output: 3
```

**DevOps use case:** Count the servers in an inventory list.

### Adding a Server

Use `append()` to add a new item.

```python
servers = ["web-01", "web-02"]

servers.append("web-03")

print(servers)
# Output: ['web-01', 'web-02', 'web-03']
```

**DevOps use case:** Add a server to a list before running an automation task.

### Removing a Server

Use `remove()` to remove an item by value.

```python
servers = ["web-01", "web-02", "web-03"]

servers.remove("web-02")

print(servers)
# Output: ['web-01', 'web-03']
```

**DevOps use case:** Update an inventory list when a server is no longer part of the target group.

### Checking a Server

Use `in` to check whether a server exists in the list.

```python
servers = ["web-01", "web-02", "db-01"]

if "web-01" in servers:
    print("Server found")
else:
    print("Server not found")

# Output: Server found
```

**DevOps use case:** Check whether a server is included in a deployment target list.

### Looping Through Servers

A `for` loop lets you process each item.

```python
servers = ["web-01", "web-02", "db-01"]

for server in servers:
    print(f"Checking server: {server}")
```

Output:

```text
Checking server: web-01
Checking server: web-02
Checking server: db-01
```

**DevOps use case:** Loop through servers to run health checks or automate routine tasks.

---

## 2. What is a Tuple?

A tuple stores multiple items in a single variable. Tuples are **ordered and immutable**, meaning their elements cannot be replaced, added, or removed after creation.

In DevOps, tuples are useful for grouping fixed configuration values, such as a server's hostname and port number.

### Creating a Tuple

```python
server_config = ("web-01", "192.168.1.10", 80)

print(server_config)
```

Output:

```text
('web-01', '192.168.1.10', 80)
```

### Accessing Tuple Elements

```python
server_config = ("web-01", "192.168.1.10", 80)

print(server_config[0])  # web-01
print(server_config[1])  # 192.168.1.10
print(server_config[2])  # 80
```

**DevOps use case:** Access a server's hostname, IP address, or port.

### Tuple Unpacking

Unpacking assigns tuple elements to separate variables.

```python
server_config = ("web-01", "192.168.1.10", 80)

hostname, ip_address, port = server_config

print(hostname)    # web-01
print(ip_address)  # 192.168.1.10
print(port)        # 80
```

**DevOps use case:** Read fixed configuration values into separate variables.

### Returning Multiple Values

A function can return multiple values, which Python packs into a tuple.

```python
def get_server_info():
    return "web-01", 80

hostname, port = get_server_info()

print(hostname)  # web-01
print(port)      # 80
```

**DevOps use case:** Return a server name and port from a helper function.

### Checking a Tuple

```python
allowed_ports = (22, 80, 443)

if 443 in allowed_ports:
    print("HTTPS port is allowed")

# Output: HTTPS port is allowed
```

**DevOps use case:** Check whether a port belongs to a predefined set of allowed ports. This example only checks the tuple; it does not configure a firewall.

---

## 3. Lists vs Tuples in DevOps

| Feature | List | Tuple |
|---|---|---|
| Syntax | `["web-01", "web-02"]` | `("web-01", 80)` |
| Mutable | Yes | No |
| Add or remove items | Yes | No |
| Access by index | Yes | Yes |
| Typical use | Server inventory | Fixed configuration values |
| Example | Deployment targets | Hostname and port |

### Example: List for Deployment Targets

```python
deployment_targets = ["web-01", "web-02"]

deployment_targets.append("web-03")

for server in deployment_targets:
    print(f"Deploying application to {server}")
```

### Example: Tuple for Server Configuration

```python
server_config = ("web-01", 80)

hostname, port = server_config

print(f"Server: {hostname}, Port: {port}")
```

**Remember:** Use lists when your collection needs to change. Use tuples when you want to keep an ordered group of values unchanged.

Note that a tuple containing mutable objects can still have those objects modified. Tuples are not a security mechanism for protecting configuration data.

---

## 4. Quick Summary

| Method / Function | Purpose |
|---|---|
| `len(servers)` | Count servers |
| `servers[0]` | Access the first server |
| `servers.append()` | Add a server |
| `servers.remove()` | Remove a server |
| `"web-01" in servers` | Check whether a server exists |
| `for server in servers` | Process each server |
| `hostname, port = config` | Unpack tuple values |

**DevOps practice idea:** Create a Python script that stores server names in a list, checks whether a target server exists, and prints a deployment message for each server.

---

<p align="center">
  <a href="./ch_7.md"><img src="https://img.shields.io/badge/⬅_Back-blue?style=for-the-badge" alt="Back"></a>
  <a href="./ch_9.md"><img src="https://img.shields.io/badge/Forward_➡-green?style=for-the-badge" alt="Forward"></a>
</p>