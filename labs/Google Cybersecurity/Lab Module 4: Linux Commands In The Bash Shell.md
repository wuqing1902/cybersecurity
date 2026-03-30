# Lab Module 4: Linux Commands In The Bash Shell

This module demonstrates practical skills in navigating, managing, and analyzing files, users, and permissions in a Linux Bash shell. It includes six lab activities designed to build foundational Linux skills useful for a security analyst.

---

## Table of Contents
1. [Activity 1: Find files with Linux commands](#activity-1-find-files-with-linux-commands)
2. [Activity 2: Filter with grep](#activity-2-filter-with-grep)
3. [Activity 3: Manage files with Linux commands](#activity-3-manage-files-with-linux-commands)
4. [Activity 4: Manage authorization](#activity-4-manage-authorization)
5. [Activity 5: Add and manage users with Linux commands](#activity-5-add-and-manage-users-with-linux-commands)
6. [Activity 6: Get help in the command line](#activity-6-get-help-in-the-command-line)

---

## Activity 1: Find files with Linux commands

**Objective:** Navigate directories, locate files, and read file contents using Linux commands.

### Commands Used
```bash
# Display current working directory
pwd

# List files and directories in the current working directory
ls -l

# Navigate to reports directory
cd /home/analyst/reports

# List subdirectories
ls -l

# Navigate to users subdirectory
cd users

# Display files in the directory
ls

# Display contents of a file
cat Q1_added_users.txt

# Navigate to logs directory
cd /home/analyst/logs

# Display file names
ls

# Display first 10 lines of a file
head -n 10 server_logs.txt
```

### Reflection:
This activity strengthened my ability to navigate Linux directories, locate files, and read contents, which are foundational skills for analyzing system activity or investigating security events.

---

## Activity 2: Filter with grep

**Objective:** Use grep and piping to search for specific information in files.

### Commands Used
```bash
# Navigate to logs directory
cd /home/analyst/logs

# Search for error messages
grep "error" server_logs.txt

# Navigate to users directory
cd /home/analyst/reports/users

# Find files with 'Q1' in their names
ls | grep "Q1"

# Find files with 'access' in their names
ls | grep "access"

# Search deleted users
grep "jhill" Q2_deleted_users.txt

# List users added to Human Resource department
grep "Human Resource" Q4_added_users.txt
```

### Reflection:
Filtering data with grep allows efficient retrieval of relevant information, essential for analyzing logs or auditing user activities in a system.

---

## Activity 3: Manage files with Linux commands

**Objective:** Create, move, remove files and directories, and edit files using nano.

### Commands Used
```bash
# Create new logs subdirectory
mkdir /home/analyst/logs

# List contents to verify
ls -l /home/analyst

# Remove temp directory
rm -r /home/analyst/temp

# Move Q3patches.txt to reports
mv /home/analyst/notes/Q3patches.txt /home/analyst/reports

# Delete tempnotes.txt
rm /home/analyst/notes/tempnotes.txt

# Create tasks.txt
touch /home/analyst/notes/tasks.txt

# Edit tasks.txt with nano
nano /home/analyst/notes/tasks.txt

# Clear screen
clear

# Display contents to verify
cat /home/analyst/notes/tasks.txt
```

### Reflection:
This activity emphasized effective file and directory management, a key skill for organizing system resources and maintaining data integrity.

---

## Activity 4: Manage authorization

**Objective:** Examine and modify file and directory permissions to control access.

### Commands Used
```bash
# Navigate to projects directory
cd /home/researcher2/projects

# List contents with permissions
ls -la

# Remove write permission for others on a file
chmod o-w project_k.txt

# Restrict group permissions on a file
chmod go-rw project_m.txt

# Adjust hidden file permissions
chmod ug=r .project_x.txt

# Remove execute permission for group on drafts directory
chmod g-x drafts
```

### Reflection:
Managing permissions ensures that sensitive files are only accessible to authorized users, reducing the risk of unauthorized changes or data exposure.

---

## Activity 5: Add and manage users with Linux commands

**Objective:** Add, modify, and delete users and groups in Linux.

### Commands Used
```bash
# Add new user researcher9
sudo useradd researcher9

# Add to primary group
sudo usermod -g research_team researcher9

# Change file ownership
sudo chown researcher9 /home/researcher2/projects/project_r.txt

# Add to secondary group
sudo usermod -a -G sales_team researcher9

# Delete user
sudo userdel researcher9

# Delete unused group
sudo groupdel researcher9
```

### Reflection:
This activity provided experience in user management and demonstrated how proper access control aligns with security best practices.

---

## Activity 6: Get help in the command line

**Objective:** Use man, whatis, and apropos to discover commands and options.

### Commands Used
```bash
# Get short description of cat
whatis cat

# Display manual page for cat
man cat

# Search commands with keywords
apropos "first part file"

# Check options for useradd
man useradd

# Compare rm and rmdir
whatis rm
whatis rmdir

# Identify command to create a new group
apropos "create new group"
```

### Reflection:
Learning how to access command documentation and find options efficiently is invaluable for troubleshooting and mastering Linux commands.

---

## Conclusion:
By completing these six activities, I developed core Linux Bash skills, including directory navigation, file management, filtering data, managing permissions, user administration, and accessing command-line help. These skills are fundamental for security analysts working in Linux environments.

