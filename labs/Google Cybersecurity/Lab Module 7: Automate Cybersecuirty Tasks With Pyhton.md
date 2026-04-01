# Lab Module 7: Automate Cybersecuirty Tasks With Pyhton
## Objective
The goal of this portfolio is to demonstrate my understanding and practical application of Python concepts as applied to cybersecurity. This includes automation, data parsing, conditional logic, iterative statements, and file operations—all essential skills for real-world security tasks such as log analysis, threat detection, and system monitoring.

---

## Projects / Labs Included
### 1. Python Section 1 Concepts
**Sections Covered:** Comments, Functions, Conditional Statements, Iterative Statements  
**Description:**
- Explored basic Python syntax and program structure.
- Practiced creating comments, using built-in functions (print(), type(), range()).
- Applied conditional statements (if, elif, else, logical operators) to make decisions in code.
- Used iterative statements (for, while, break, continue) to process sequences.


#### Comments
##### Single-line comment
```python
# Print approved usernames
```
##### Multi-line comment / Docstring
```python
"""
The estimate_attempts() function takes in a monthly
login attempt total and a number of months and
returns their product.
"""
```
#### Conditional Statements
**Keywords and Operators:** if, elif, else, and, or, not  
```python
if username == "bmoreno" and login_attempts < 5:
    print("Access granted")
elif status == 500:
    print("Server error")
else:
    print("Access denied")
```

#### Iterative Statements
**Keywords and Operators:** for, while, break, continue  
```python
for user in ["bmoreno", "tshah", "elarson"]:
    print(user)

while login_attempts < 5:
    login_attempts += 1
    print(login_attempts)
```

#### User-defined Functions
- def to define a function
- return to output values
```python
def calculate_fails(total_attempts, failed_attempts):
    fail_percentage = failed_attempts / total_attempts
    return fail_percentage

print(calculate_fails(50, 5))
```

#### Built-in Functions
**Keywords and Operators:** print(), type(), range(), max(), min(), sorted()  
```python
print(max(10, 15, 5))  # 15
print(type(True))      # <class 'bool'>
print(sorted([10, 15, 5]))  # [5, 10, 15]
```

#### Importing Modules and Libraries
- import keyword
- from module import function
```python
import statistics
from statistics import mean, median

print(mean([1, 2, 3]))
```


---


### 2. Python Section 2 Concepts
**Sections Covered:** User-defined Functions, Built-in Functions, Importing Modules and Libraries  
**Description:**
- Learned to create reusable functions with def and return.
- Explored built-in functions (max(), min(), sorted()).
- Imported Python standard libraries (statistics) and used functions like mean() and median().


#### User-defined Functions
```python
def greet_employee():
    print("Welcome!")

def calculate_fails(total_attempts, failed_attempts):
    fail_percentage = failed_attempts / total_attempts
    return fail_percentage
```

#### Built-in Functions
**Keywords and Operators:** max(), min(), sorted()  
```python
print(max(10, 15, 5))  # 15
print(min(10, 15, 5))  # 5
print(sorted([10, 15, 5]))  # [5, 10, 15]
print(sorted(["bmoreno", "tshah", "elarson"]))  # ['bmoreno','elarson','tshah']
```

#### Importing Modules and Libraries
```python
import statistics
from statistics import mean
from statistics import mean, median
```


---


### 3. Python Section 3 Concepts
**Sections Covered:** String Methods, List Methods, Regular Expressions, Advanced Syntax  
**Description:**
- Manipulated strings (upper(), lower(), index()) and lists (append(), insert(), remove()).
- Applied concatenation (+) and slicing ([]) for strings and lists.


#### Built-in Functions
**Keywords and Operators:** str(), len()
```python
str(10)  # '10'
print(len("security"))  # 8
```

#### String Methods
**Keywords and Operators:** .upper(), .lower(), .index()  
```python
print("Security".upper())  # 'SECURITY'
print("Security".lower())  # 'security'
print("Security".index("c"))  # 2
```

#### List Methods
**Keywords and Operators:** .insert(), .remove(), .append(), .index()  
```python
username_list = ["elarson", "fgarcia", "tshah"]
username_list.insert(2, "wjaffrey")
username_list.remove("elarson")
username_list.append("btang")
print(username_list.index("tshah"))
```

#### Additional Syntax  
Concatenation: +  
Bracket notation: []  
```python
device_id = "IT" + "nwp12"  # 'ITnwp12'
users = ["elarson", "bmoreno"] + ["tshah", "btang"]
print(users[2])  # 'tshah'
```

#### Regular Expressions
re.findall(), \w, \d, ., \s, +, *, {}
```python
import re
re.findall("\w+", "a53-32c .E")  # ['a53','32c','E']
re.findall("\d", "a53-32c .E")    # ['5','3','3','2']
```

---


### 4. Python Section 4 Concepts
**Sections Covered:** File Operations, Parsing  
**Description:**
- Practiced opening, reading, writing, and appending files using open() and with.
- Used .split() and .join() methods to parse and format text data.


#### File Operations
**Keywords and Operators:** `with`, `open()`, `.read()`, `.write()`, `as`
```python
with open("login_attempts.txt", "r") as file:
    file_text = file.read()

with open("access_log.txt", "a") as file:
    file.write("jrafael")
```

#### Parsing
**Keywords and Operators:** .split(), .join()
``` python
approved_users = "elarson,bmoreno,tshah".split(",")
removed_users = "wjaffrey jsoto abernard".split()
approved_users_string = ",".join(["elarson","bmoreno","tshah"])
```

---

## How to Run a Python Script

1. Ensure your Python file(s) are in the same folder as any required input files (e.g., `allow_list.txt`, `remove_list.txt`).
2. Open a terminal and navigate to the project folder.
3. Run any Python file using the following command:

```bash
python <filename>.py
```

**Example:**
```bash
python update_allow_list.py
python calculate_fails.py
python process_logs.py
```

**Hint:** Replace <filename>.py with the name of the Python script you want to execute.

---

## Reflection
This module helped me consolidate fundamental Python concepts while applying them in cybersecurity-related scenarios.
Practicing conditional logic, loops, and file operations gave me insight into automating routine security tasks.
Working with string parsing and regex strengthened my ability to extract and analyze critical data efficiently.
I now feel more confident using Python for incident response, log analysis, and building scripts to support cybersecurity operations.

---

## Conclusion

This module demonstrates a progression from basic Python syntax to practical cybersecurity applications. By combining sections learned in this module, I can showcase my ability to automate tasks, analyze data, and develop Python scripts that enhance operational efficiency and security awareness.
