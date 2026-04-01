# Project Module 7: Update A File Through A Python Algorithm
## Project Description
At my organization, access to restricted content is controlled via an allow list of IP addresses stored in the allow_list.txt file. A separate remove list identifies IP addresses that should no longer have access.

I created a Python algorithm to automate updating the allow list file. This algorithm checks whether any IP addresses on the remove list exist in the allow list, removes them if present, and updates the file accordingly. This project demonstrates file handling, string manipulation, list operations, and iteration in Python.

---

## Project Objective

The objective of this project is to create a Python algorithm that automates the management of an allow list of IP addresses. Specifically, it aims to:

- Identify and remove IP addresses from the allow list that are no longer authorized.
- Demonstrate practical file handling and data manipulation skills in Python.
- Provide a reproducible workflow that can be added to a cybersecurity portfolio to showcase coding proficiency in automation tasks.

---

## Example 1: Single Folder Version
### Python Algorithm
```python
# Step 1: Open the file that contains the allow list
import_file = "allow_list.txt"

with open(import_file, "r") as file:
    # Step 2: Read the file contents into a string
    ip_addresses = file.read()

# Step 3: Convert the string into a list of IP addresses
ip_addresses = ip_addresses.split()

# Example remove list
remove_list = ["192.168.1.10", "10.0.0.5"]

# Step 4: Iterate through the remove list
for element in remove_list:
    # Step 5: Remove IP addresses that are on the remove list
    if element in ip_addresses:
        ip_addresses.remove(element)  # Works because there are no duplicates

# Step 6: Update the file with the revised list of IP addresses
ip_addresses = "\n".join(ip_addresses)  # Convert list back to string with newlines

with open(import_file, "w") as file:
    file.write(ip_addresses)
```

---

## Example 2: Multiple Folder Version 
### Folder Structure
``` bash
Update-File-Python-Algorithm/
│
├── allow_list.txt             # Sample allow list file
├── remove_list.txt            # Sample remove list file
├── update_allow_list.py       # Python algorithm script
└── README.md                  # Project explanation and portfolio entry
```

### allow_list.txt
Sample IP addresses (one per line):
``` bash
192.168.1.1
192.168.1.10
10.0.0.5
172.16.0.1
```

### remove_list.txt
Sample IP addresses to remove:
``` bash
192.168.1.10
10.0.0.5
```

update_allow_list.py
``` python
# update_allow_list.py
"""
Python algorithm to update an allow list of IP addresses
by removing IPs that appear in a remove list.
"""

# File paths
allow_file = "allow_list.txt"
remove_file = "remove_list.txt"

# Read allow list
with open(allow_file, "r") as file:
    ip_addresses = file.read().split()  # Convert to list

# Read remove list
with open(remove_file, "r") as file:
    remove_list = file.read().split()

# Remove IPs from allow list
for element in remove_list:
    if element in ip_addresses:
        ip_addresses.remove(element)

# Update allow list file
with open(allow_file, "w") as file:
    file.write("\n".join(ip_addresses))

print("Allow list updated successfully!")
```

---

## Explanation of Python Syntax and Functions
- **with open(import_file, "r") as file:**  
  Opens a file for reading ("r" mode) and automatically closes it after the block. `file` represents the file object.
- **.read():**  
  Converts the file contents into a string so it can be processed in Python.
- **.split():**  
  Converts a string into a list of elements. In this case, it splits IP addresses into a list.
- **for element in remove_list:**  
  Iterates over each item in the `remove_list` to process them one by one.
- **if element in ip_addresses:**  
  Checks whether the IP address exists in the allow list before attempting to remove it.
- **.remove(element):**  
  Removes the element from the list. Works correctly here because there are no duplicate IP addresses.
- **"\n".join(ip_addresses):**  
  Converts the list back into a string, adding a newline character between each IP address.
- **with open(import_file, "w") as file:**  
  Opens the file for writing ("w" mode) and overwrites the contents with the updated IP addresses.

---

## How to Run
1. Make sure `allow_list.txt` and `remove_list.txt` are in the same folder as `update_allow_list.py`.
2. Open a terminal and navigate to the folder.
3. Run the script:
```bash
python update_allow_list.py
```
4. Check allow_list.txt to see the updated IP addresses.


---

## Reflection

Working on this project helped me better understand practical applications of Python for file handling and automation in cybersecurity. I learned how to safely read and write files, manipulate strings and lists, and automate repetitive tasks that would otherwise be time-consuming.

It also highlighted the importance of considering potential issues such as duplicates or missing entries, and ensuring scripts handle them gracefully. Overall, this project strengthened my confidence in applying Python to real-world cybersecurity problems.

---

## Summary
This algorithm demonstrates how to manage file-based allow lists using Python. It involves:
- Opening and reading a file using a with statement and .read() method.
- Converting a string of IP addresses into a list with .split().
- Iterating through a remove list using a for loop.
- Removing elements from a list with .remove().
- Converting the list back to a string with .join() and writing it back to the file with .write().
By automating this process, the algorithm ensures that only authorized IP addresses have access to restricted content, improving both efficiency and security.

---

## Conclusion

By automating the process of updating the allow list, this project ensures that only authorized IP addresses have access to restricted content. It improves both efficiency and security, demonstrates key Python programming concepts, and can serve as a professional portfolio piece to showcase my practical coding skills in cybersecurity.
