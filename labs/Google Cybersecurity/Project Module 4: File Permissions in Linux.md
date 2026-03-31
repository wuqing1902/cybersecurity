# Project Module 4: File Permissions in Linux

## Project Description
In this activity, I performed file permission analysis and management using Linux commands as part of a security role supporting a research team. The objective was to review existing permissions, identify unauthorized access, and apply appropriate restrictions to ensure system security. This task demonstrates practical skills in access control and Linux system administration.

---

## Check File and Directory Details

To view file and directory permissions, I used the following command:

`ls -la`

This command lists all files (including hidden files) with detailed information such as permissions, ownership, and file type.

### Example Output (Based on Scenario)
```bash
-rw-rw-rw- 1 researcher2 research 1234 project_k.txt
-rw-r----- 1 researcher2 research 1234 project_m.txt
-rw-rw-r-- 1 researcher2 research 1234 project_r.txt
-rw-rw-r-- 1 researcher2 research 1234 project_t.txt
-rw--w---- 1 researcher2 research 1234 .project_x.txt
drwx--x--- 2 researcher2 research 4096 drafts
```

---

## Describe the Permissions String

Example selected:  
`-rw-rw-r--`

This is a 10-character string that represents file type and permissions.

Breakdown:
- `-` → File type (regular file)
- `rw-` → User (owner) permissions: read and write
- `rw-` → Group permissions: read and write
- `r--` → Others permissions: read only

This string helps determine who can access and modify a file.

---

## Change File Permissions

The organization does not allow **others to have write access**.

### File Identified:
`project_k.txt` (others had write permission)

### Command Used:
`chmod o-w project_k.txt`

### Explanation:
- `chmod` → Change file permissions  
- `o-w` → Remove write permission from others  

### Result:
Permissions changed from:
-rw-rw-rw-
To: 
-rw-rw-r--


---

## Change File Permissions on a Hidden File

The file `.project_x.txt` is hidden and should:
- NOT allow write access
- Allow read access for user and group

### Command Used:
`chmod ug+r,u-w,g-w,o-rwx .project_x.txt`

### Explanation:
- `ug+r` → Add read permission for user and group  
- `u-w,g-w` → Remove write permission from user and group  
- `o-rwx` → Remove all permissions from others  

### Result:
Permissions updated to:
-r--r-----

---

## Change Directory Permissions

The `drafts` directory should only be accessible by the owner (`researcher2`).

### Command Used:
`chmod 700 drafts`

### Explanation:
- `7` → read, write, execute (user)
- `0` → no permissions (group)
- `0` → no permissions (others)

### Result:
Permissions changed to:
drwx------

---

## Summary

In this activity, I used Linux commands to review and modify file and directory permissions to meet security requirements. I applied `ls -la` to inspect permissions and `chmod` to enforce proper access control. This ensured that unauthorized users could not modify files or access restricted directories. These skills are essential in cybersecurity roles to maintain system integrity and protect sensitive data.
