# Python Cheatsheet – Technical Overview

## 1. Array Methods (Python Lists)

In Python, arrays are typically implemented using lists, which are dynamic, ordered, and mutable collections.

### Creating a List
```bash
arr = [1, 2, 3, 4]
```

### Common List Methods

| Method           | Description	             | Example             |
|------------------|---------------------------|---------------------|
| append(x)        | Adds element at end       | arr.append(5)       |
| extend(iterable) | Adds multiple elements	   | arr.extend([6,7])   |
| insert(i, x)	   | Insert at index	         | arr.insert(1, 10)   |
| remove(x)	       | Remove first occurrence   | arr.remove(2)       |
| pop([i])	       | Remove and return element | arr.pop()         |
| clear()	         | Remove all elements	     | arr.clear()         |
| index(x)	       | Return index of element   | arr.index(3)        |
| count(x)	       | Count occurrences	       | arr.count(1)        |
| sort()	         | Sort list	               | arr.sort()          |
| reverse()	       | Reverse list	             | arr.reverse()       |
| copy()	         | Return shallow copy	     | arr.copy()          |


### Important Notes

- Lists are mutable.

- Negative indexing is supported.

- Slicing: `arr[start:end:step]`

List comprehension:
```bash
squares = [x*x for x in range(10)]
```
---

## 2. String Methods

Strings in Python are immutable sequences of Unicode characters.

### String Creation
```bash
text = "Hello World"
```

### Common String Methods

| Method	        | Description	              | Example
|-----------------|---------------------------|----------------------------|
| lower()	        | Convert to lowercase    	| text.lower()
| upper()	        | Convert to uppercase	    | text.upper()
| strip()	        | Remove whitespace	        | text.strip()
| replace(a,b)	  | Replace substring	        | text.replace("Hello","Hi")
| split()	        | Split into list	          | text.split()
| join(iterable)  | Join iterable into string | " ".join(words)
| find(x)	        | Find index	              | text.find("World")
| startswith(x)	  | Check prefix	            | text.startswith("He")
| endswith(x)	    | Check suffix	            | text.endswith("ld")
| isdigit()	      | Check numeric	            | "123".isdigit()

### String Formatting

f-Strings (Recommended)
```bash
name = "Computer"
print(f"Hello {name}")
```
### format()
```bash
"Hello {}".format(name)
```
---
## 3. Objects and Object-Oriented Programming (OOP)

Python supports OOP principles such as:

- Encapsulation

- Abstraction

- Inheritance

- Polymorphism

### Class Definition
```bash
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def greet(self):
        return f"Hi, I am {self.name}"
```
### Creating an Object
```bash
p1 = Person("Naman", 25)
print(p1.greet())
```
### Inheritance
```bash
class Student(Person):
    def __init__(self, name, age, grade):
        super().__init__(name, age)
        self.grade = grade
```
### Special (Magic) Methods

- `__init__` – constructor

- `__str__` – string representation

### Example:

```bash
def __str__(self):
    return self.name
```
--- 

## 4. Decorators

Decorators modify or extend function behavior without changing its code.

### Basic Decorator
```bash
def my_decorator(func):
    def wrapper():
        print("Before function")
        func()
        print("After function")
    return wrapper

@my_decorator
def say_hello():
    print("Hello")

say_hello()
```

### Decorator with Arguments
```bash
def decorator(func):
    def wrapper(*args, **kwargs):
        print("Executing")
        return func(*args, **kwargs)
    return wrapper
```
### Common Use Cases

- Logging

- Authentication

- Timing functions

- Caching (functools.lru_cache)

---

## 5. Virtual Environment

A virtual environment isolates Python dependencies per project.

### Create Virtual Environment
```bash
python -m venv venv
```
### Activate

#### Linux/Mac:
```bash
source venv/bin/activate
```


#### Windows:
```bash
venv\Scripts\activate
```

### Deactivate
```bash
deactivate
```

### Why Use virtualenv?

- Prevent dependency conflicts

- Project-specific packages

- Reproducible environments
---

## 6. pip Package Manager

pip is Python’s package installer.

### Install Package
```bash
pip install requests
```
### Uninstall Package
```bash
pip uninstall requests
```
### List Installed Packages
```bash
pip list
```
### Freeze Requirements
```bash
pip freeze > requirements.txt
```
### Install from requirements.txt
```bash
pip install -r requirements.txt
```
---

## 7. PEP-8 Standards Summary

PEP-8 is the official Python style guide.

### Naming Conventions
| Type      | Convention | Example       |
| --------- | ---------- | ------------- |
| Variables | snake_case | `user_name`   |
| Functions | snake_case | `get_data()`  |
| Classes   | PascalCase | `UserProfile` |
| Constants | UPPER_CASE | `MAX_LIMIT`   |

### Indentation

- 4 spaces per indentation level

- Avoid tabs

### Line Length

- Maximum 79 characters per line

- Docstrings/comments: 72 characters

### Imports

- One import per line

- Order:

    - Standard library

    - Third-party

    - Local imports

#### Example:
```bash
import os
import sys

import requests

from mymodule import myfunc
```
### Whitespace

Correct:
```bah
x = 5
y = x + 2
```

Incorrect:
```bah
x=5
y = x+2
```
### Docstrings

Use triple quotes:
```bash
def add(a, b):
    """Return sum of two numbers."""
    return a + b
