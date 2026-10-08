# Python for DevOps

## Shell Script vs Python

In DevOps, many tasks need automation.

For example:

* Create files and folders
* Manage servers
* Run Linux commands
* Check system health
* Work with AWS
* Call APIs
* Read JSON/YAML files
* Process logs
* Automate deployments
* Monitor applications

For simple tasks, **Shell Script** is often enough.

For more complex tasks, **Python** is usually a better choice.

---

# 1. Shell Script

A Shell Script is a file that contains Linux commands.

### Example

```bash
#!/bin/bash

echo "Starting application..."

# -p: creates nested folders, and doesn't give an error if the folder already exists
mkdir -p logs/paymentServicelogs
touch logs/pyamentServicelogs/app.log

echo "Application started"
```

Here, Shell Script is directly working with Linux commands.

## Good Use Cases

Use Shell Script when:

* The task is simple
* The task mainly uses Linux commands
* You need to manage files and directories
* You need to start or stop services
* You need to work with environment variables
* You need a quick automation script

---

# 2. Python

Python is a general-purpose programming language.

It can be used for simple automation as well as complex automation.

### Example

```python
import os

# Name of the directory where the log file will be stored
log_directory = "logs"

# Check if the "logs" directory already exists
if not os.path.exists(log_directory):

    # Create the "logs" directory if it does not exist
    os.makedirs(log_directory)

# Open the app.log file in append mode ("a")
# If the file does not exist, Python will create it
with open("logs/pyamentServicelogs/app.log", "a") as file:

    # Write a message to the log file
    # \n moves the next message to a new line
    file.write("Application started\n")

# Print a message on the terminal
print("Application started")
```

But Python gives more control when the logic becomes complex.

---

# 4. When to Use Shell Script

## 4.1 System Administration

Shell is very good for basic Linux administration.

### Example

```bash
#!/bin/bash

sudo systemctl restart nginx
sudo systemctl status nginx
```

This is a simple task.

There is no need to use Python for such a small task.

---

## 4.2 Running Linux Commands

If the main job is running commands, Shell is usually the easiest option.

```bash
docker ps
docker images
docker system df
```

A Shell Script can combine these commands:

```bash
#!/bin/bash

docker ps
docker images
docker system df
```

---

## 4.3 Quick Automation

Suppose you want to remove old log files.

```bash
#!/bin/bash

find /var/log -name "*.log" -mtime +7 -delete
```

For a small task like this, Shell is a good choice.

---

# 5. When to Use Python

Python becomes more useful when the task has more logic.

For example:

> Check 50 servers and find which servers are down.

Python can store the servers in a list.

```python
servers = [
    "server-01",
    "server-02",
    "server-03",
]
```

Then process each server:

```python
for server in servers:
    print(f"Checking {server}")
```

Later, more features can be added:

* SSH
* API calls
* Error handling
* Logging
* JSON
* AWS
* Database operations

This is where Python becomes more useful.

---

# 6. API Integration

One important reason DevOps engineers use Python is **API integration**.

Python can communicate with APIs.

### Example

```python
import requests

response = requests.get("https://api.example.com/servers")

print(response.status_code)
print(response.json())
```

Shell can also call APIs using tools like `curl`.

```bash
curl https://api.example.com/servers
```

But when the API workflow becomes complicated, Python is usually easier to maintain.

---

# 7. JSON Processing

DevOps tools produce a lot of JSON data.

### Example JSON

```json
{
    "server": "web-01",
    "status": "running",
    "port": 80
}
```

Python can easily work with this data.

```python
server = {
    "server": "web-01",
    "status": "running",
    "port": 80
}

print(server["server"])
print(server["status"])
```

### Output

```text
web-01
running
```

JSON processing is useful when working with:

* AWS
* REST APIs
* Docker
* Kubernetes
* CI/CD systems
* Monitoring tools

---

# 8. Error Handling

Python provides good error handling.

### Example

```python
try:
    with open("server.txt") as file:
        data = file.read()

except FileNotFoundError:
    print("server.txt was not found")
```

If the file does not exist, Python can handle the error instead of simply stopping the program.

Error handling is important in production automation.

---

# 9. Complex Logic

Suppose we need to perform these tasks:

```text
10 servers
    ↓
Check server status
    ↓
If server is down
    ↓
Send alert
    ↓
Write log
    ↓
Try restart
    ↓
Check again
    ↓
Generate report
```

This is possible with Shell.

However, as the logic becomes larger, Shell Scripts can become difficult to maintain.

Python is usually a better choice for this type of automation.

### Python can handle:

```text
Python
 ├── Server checking
 ├── Error handling
 ├── API calls
 ├── Logging
 ├── Retry logic
 └── Report generation
```

---


# 11. Shell and Python Together

In real DevOps work, we do not always have to choose only one.

Shell and Python can work together.

### Example

```text
Shell Script
      ↓
Start Python Script
      ↓
Python
      ↓
Call AWS API
      ↓
Process JSON
      ↓
Generate Result
```

So remember:

> **Python does not replace Shell.**

Both are useful DevOps automation tools.

Use the tool that fits the task.


---

### Final Point

A DevOps engineer should know **both Shell and Python**.

Use Shell when the task is simple and Linux-focused.

Use Python when the task needs more logic, data processing, APIs, error handling, or reusable automation.

---

<p align="center">
  <a href="../README.md"><img src="https://img.shields.io/badge/⬅_Back-blue?style=for-the-badge" alt="Back"></a>
  <a href="./ch_2.md"><img src="https://img.shields.io/badge/Forward_➡-green?style=for-the-badge" alt="Forward"></a>
</p>