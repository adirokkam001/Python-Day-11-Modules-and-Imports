# 🐍 Give the description of the note

## 📌 Topics Covered

Today I learned about:

- What is a Module?
- Why Modules are used
- Importing Modules
- `import`
- `from ... import`
- Importing multiple functions
- `import *`
- Built-in Modules
- `math` Module
- `random` Module
- `datetime` Module
- `os` Module
- `sys` Module
- Module Aliases using `as`
- Creating Custom Modules
- Using Modules in Cloud/DevOps
- Module vs Function
- Module vs Package vs Library

---

# 1. What is a Module?

A **module** is a Python file containing reusable code.

A Python file with the `.py` extension can be used as a module.

For example:

```text
calculator.py
```

Inside the file:

```python
def add(a, b):
    return a + b

def subtract(a, b):
    return a - b
```

Here, `calculator.py` is a module.

---

# 2. Why Do We Use Modules?

Modules help us organize Python programs.

Instead of putting everything into one large file, we can separate our code into different files.

Example:

```text
project/
│
├── main.py
├── calculator.py
├── server.py
└── config.py
```

Each file can contain code related to a specific purpose.

### Advantages of Modules

- Makes code easier to understand
- Makes code reusable
- Makes large projects easier to manage
- Reduces duplicate code
- Makes debugging easier
- Helps organize projects

---

# 3. Importing a Module

We can use the `import` statement to import a module.

Suppose we have:

### calculator.py

```python
def add(a, b):
    return a + b
```

Now in `main.py`:

```python
import calculator

result = calculator.add(10, 20)

print(result)
```

Output:

```text
30
```

### Explanation

```python
import calculator
```

imports the `calculator` module.

Then:

```python
calculator.add(10, 20)
```

calls the `add()` function from the `calculator` module.

---

# 4. Using `from ... import`

We can import a specific function from a module.

```python
from calculator import add

result = add(10, 20)

print(result)
```

Output:

```text
30
```

Now we don't need to write:

```python
calculator.add()
```

We can directly use:

```python
add()
```

---

# 5. Importing Multiple Functions

We can import multiple functions from the same module.

```python
from calculator import add, subtract

print(add(10, 5))
print(subtract(10, 5))
```

Output:

```text
15
5
```

---

# 6. Import Everything

Python also allows:

```python
from calculator import *
```

Now all available functions from the module can be used directly.

Example:

```python
from calculator import *

print(add(10, 5))
print(subtract(10, 5))
```

However, using `import *` is generally **not recommended** in real projects because it can make code harder to understand.

Prefer:

```python
import calculator
```

or:

```python
from calculator import add
```

---

# 7. Built-in Python Modules

Python comes with many useful modules.

These are called **built-in or standard-library modules**.

Some examples are:

```text
math
random
datetime
os
sys
```

These modules provide functionality that we can use without writing everything ourselves.

---

# 8. `math` Module

The `math` module provides mathematical functions.

Example:

```python
import math

print(math.sqrt(25))
```

Output:

```text
5.0
```

Another example:

```python
import math

print(math.pow(2, 3))
print(math.ceil(4.2))
print(math.floor(4.8))
```

Output:

```text
8.0
5
4
```

---

# 9. `random` Module

The `random` module is used to generate random values.

Example:

```python
import random

number = random.randint(1, 10)

print(number)
```

Possible output:

```text
7
```

Another execution may produce:

```text
3
```

The value is random.

---

# 10. `datetime` Module

The `datetime` module is used to work with dates and times.

Example:

```python
import datetime

today = datetime.datetime.now()

print(today)
```

Example output:

```text
2026-10-07 20:15:30
```

This can be useful in automation, logging, and monitoring.

---

# 11. `os` Module

The `os` module allows Python to interact with the operating system.

Example:

```python
import os

print(os.getcwd())
```

`getcwd()` means:

**Get Current Working Directory**

Example output:

```text
/Users/adi/Python-Day11
```

---

# 12. Listing Files Using `os`

We can use `os.listdir()` to display files and folders.

```python
import os

files = os.listdir()

print(files)
```

Example output:

```text
['main.py', 'server.py', 'README.md']
```

This is useful for automation tasks.

---

# 13. `sys` Module

The `sys` module provides information about the Python environment.

Example:

```python
import sys

print(sys.version)
```

Example output:

```text
3.9.6
```

We can also check the location of the Python executable:

```python
print(sys.executable)
```

---

# 14. Module Aliases

We can give a module a shorter name using `as`.

Example:

```python
import math as m

print(m.sqrt(25))
```

Output:

```text
5.0
```

Here:

```python
math
```

is given the alias:

```python
m
```

---

# 15. Another Alias Example

```python
import datetime as dt

today = dt.datetime.now()

print(today)
```

Here:

```text
datetime → dt
```

The alias can make frequently used modules shorter to type.

---

# 16. Creating Your Own Module

We can create our own Python modules.

Create a file:

```text
cloud.py
```

Add:

```python
def show_cloud():
    print("AWS Cloud")

def show_region():
    print("ap-south-1")
```

Now create another file:

```text
main.py
```

Add:

```python
import cloud

cloud.show_cloud()
cloud.show_region()
```

Output:

```text
AWS Cloud
ap-south-1
```

Here:

```text
cloud.py
```

is our custom module.

---

# 17. Practical Cloud/DevOps Example

We can create a module for server-related functions.

### server.py

```python
def check_server(status):
    if status == "Running":
        return "Server is running"
    else:
        return "Server is stopped"
```

### main.py

```python
import server

result = server.check_server("Running")

print(result)
```

Output:

```text
Server is running
```

This allows us to keep server-related functions in `server.py`.

---

# 18. Organizing a Cloud/DevOps Project

A Python automation project could look like this:

```text
cloud-automation/
│
├── main.py
├── aws.py
├── server.py
├── network.py
└── config.py
```

Possible responsibilities:

```text
main.py
    ↓
Main program

aws.py
    ↓
AWS-related functions

server.py
    ↓
Server-related functions

network.py
    ↓
Network-related functions

config.py
    ↓
Configuration
```

This makes a large project easier to manage.

---

# 19. Module vs Function

A **module** is usually a Python file.

Example:

```text
server.py
```

A **function** is a reusable block of code inside a module.

Example:

```python
def check_server():
    print("Server is running")
```

So:

```text
server.py
    ↓
Module

check_server()
    ↓
Function
```

---

# 20. Module vs Package vs Library

### Module

Usually a single Python file.

```text
server.py
```

### Package

A collection of related Python modules.

```text
cloud/
├── aws.py
├── server.py
└── network.py
```

### Library

A broader collection of reusable code that can contain modules and packages.

For now, remember:

```text
Module  → Python file
Package → Collection of modules
Library → Reusable collection of code
```

---

# 21. Important Import Syntax

### Import a complete module

```python
import math
```

Use:

```python
math.sqrt(25)
```

---

### Import a specific function

```python
from math import sqrt
```

Use:

```python
sqrt(25)
```

---

### Import multiple functions

```python
from math import sqrt, ceil
```

Use:

```python
sqrt(25)
ceil(4.2)
```

---

### Import using an alias

```python
import math as m
```

Use:

```python
m.sqrt(25)
```

---

# 22. Same Folder Example

If your project looks like:

```text
day11/
│
├── main.py
└── server.py
```

You can normally import `server.py` from `main.py`.

### server.py

```python
def check_server():
    return "Server is running"
```

### main.py

```python
import server

print(server.check_server())
```

Output:

```text
Server is running
```

---

# 23. Complete Example

### server.py

```python
def start_server():
    return "Server started"

def stop_server():
    return "Server stopped"
```

### main.py

```python
from server import start_server, stop_server

print(start_server())
print(stop_server())
```

Output:

```text
Server started
Server stopped
```

This demonstrates how we can separate functionality into different modules.

---

# 24. Why Modules Are Important in Cloud & DevOps

Modules are very useful when creating automation scripts.

For example, instead of creating one huge Python file, we can separate:

```text
AWS functions
Server functions
Network functions
File functions
Configuration
Logging
```

into separate modules.

This makes Cloud/DevOps automation:

- More organized
- Reusable
- Easier to maintain
- Easier to debug
- Easier to scale

---

# 25. Practice Questions

### Practice 1

Create a module called:

```text
calculator.py
```

Create functions:

```text
add()
subtract()
multiply()
divide()
```

Import them into:

```text
main.py
```

---

### Practice 2

Create:

```text
server.py
```

Create a function:

```python
def check_server(status):
```

Return whether the server is running or stopped.

---

### Practice 3

Use the `math` module to find:

- Square root
- Power
- Ceiling value
- Floor value

---

### Practice 4

Use the `os` module to:

- Print the current directory
- List files in the current directory

---

### Practice 5

Use the `datetime` module to print the current date and time.

---

# 🧠 Day 11 Summary

Today I learned that a **module is a Python file containing reusable code**.

### Main concepts:

```python
import module
```

Imports a module.

```python
from module import function
```

Imports a specific function.

```python
import module as alias
```

Imports a module with a shorter name.

### Important modules learned:

```text
math
random
datetime
os
sys
```

### Custom module example:

```python
import server

server.check_server()
```

Modules allow us to organize Python programs into smaller, reusable pieces.

---

# ✅ Day 11 Checklist

- [ ] Understand what a module is
- [ ] Understand why modules are used
- [ ] Use `import`
- [ ] Use `from ... import`
- [ ] Import multiple functions
- [ ] Understand `import *`
- [ ] Use the `math` module
- [ ] Use the `random` module
- [ ] Use the `datetime` module
- [ ] Use the `os` module
- [ ] Use the `sys` module
- [ ] Use module aliases
- [ ] Create your own module
- [ ] Import a custom module
- [ ] Understand module vs function
- [ ] Understand module vs package vs library
- [ ] Practice Cloud/DevOps examples

---

## 🚀 Key Takeaway

**Modules allow you to divide a large Python program into smaller, reusable files.**

For example:

```text
main.py
   ↓
server.py
   ↓
aws.py
   ↓
network.py
```

Each module can handle a specific responsibility, which is especially useful when building Python-based Cloud and DevOps automation.

---

## 📅 Day 12 Preview

**File Handling — Reading and Writing Files**

You will learn:

- What file handling is
- Opening files
- Reading files
- Writing files
- Appending data
- `with open()`
- File modes
- Reading logs
- Writing automation output
- Practical Cloud/DevOps file examples

