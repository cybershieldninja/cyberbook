# **Files and Directory Permissions (chmod)**

Understanding file permissions is crucial for protecting your environment, files, and directories from unauthorized access or accidental deletion. In UNIX-based systems like Linux, which are multi-user environments, every file and directory in your account can be protected or made accessible by changing its access permissions.

### **🔍 Types of Permissions**

In UNIX, file and directory permissions are categorized into three main types:

1. **Read (r)**: Allows the user to view the contents of a file.
2. **Write (w)**: Allows the user to modify or delete the contents of a file.
3. **Execute (x)**: Allows the user to run a file, if it's a program or script.

### **⚙️ Levels of Permissions**

Permissions can be set at three different levels:

- **User (u)**: The owner of the file.
- **Group (g)**: Users who belong to the same group as the file owner.
- **Others (o)**: All other users on the system.

### **👀 Viewing File Permissions**

To see the permissions of a file or directory, you can use the `ls -l` command. Here’s an example of what you might see when running `ls -l`:

```bash
$ ls -l
-rw-r--r-- 1 user1 user1 1048576 Dec 17 10:00 example.txt
```

In this output:
- The first column shows the file type and permissions.
  - The first character (`-`) indicates it is a file (a `d` would indicate a directory).
  - The next three characters (`rw-`) indicate that the owner has read and write permissions.
  - The second set of three characters (`r--`) shows that the group has read permission only.
  - The final set (`r--`) shows that others also have read permission.

```plaintext
-rw-r--r--
|  |  |  |
|  |  |  +-- Others: Read
|  |  +----- Group: Read
|  +-------- User: Read & Write
+----------- File Type
```
The **`chmod`** command is used to modify the permissions of files and directories. It works by specifying a permission (read, write, or execute) for the user, group, or others.

#### **Example 1: Removing Write Permission from the Group**

```bash
# Command
chmod g-w example.txt

# Verify the change
ls -l example.txt
```

#### **Example 2: Removing Read Permission for Everyone**

```bash
# Command
chmod a-r example.txt

# Verify the change
ls -l example.txt
```

#### **Example 3: Granting Read and Write Permissions to User and Group**

```bash
# Command
chmod ug+rw example.txt

# Verify the change
ls -l example.txt
```

#### **Example 4: Granting Execute Permission**

To allow a script to be executed, you would add execute (`x`) permission. 

```bash
# Command
chmod u+x script.sh

# Verify the change
ls -l script.sh
```

If you want everyone to be able to execute the file, use:

```bash
chmod a+x script.sh
```

#### **Example 5: Changing Permissions Recursively**

If you want to change the permissions of all files and subdirectories within a directory, you can use the `-R` (recursive) option:

```bash
chmod -R u+rw directory/
```

> **⚠️ Warning**: Use `chmod -R` carefully, as it applies changes to all subdirectories and files.

### **📂 Directory Permissions**

The execute permission for directories is particularly important. It allows you to **enter** (i.e., `cd`) into the directory. For example, if a directory has execute permission for the user, you can use `cd` to navigate into it. If not, you will get a **permission denied** message.

#### **Example: Removing Execute Permission from a Directory**

```bash
# Command
chmod a-x projects

# Verify the change
ls -ld projects
```

To restore the permission:

```bash
chmod a+x projects
```

---

### **✅ Verifying Permission Changes**

After making changes to a file or directory’s permissions, always verify by running the `ls -l` command to ensure the changes took effect.

```bash
ls -l example.txt
```

### 🔢 Numerical Representation of Permissions

Each permission type is represented by a specific numerical value. These values are **added together** to create the numeric mode for each user (owner), group, and others.

| **Permission Type**             | **Numerical Value** | **Symbol** |
|----------------------------------|---------------------|------------|
| **No permission**               | 0                   | ---        |
| **Execute**                     | 1                   | --x        |
| **Write**                       | 2                   | -w-        |
| **Write + Execute**             | 3                   | -wx        |
| **Read**                        | 4                   | r--        |
| **Read + Execute**              | 5                   | r-x        |
| **Read + Write**                | 6                   | rw-        |
| **Read + Write + Execute**      | 7                   | rwx        |

You add these values together to assign multiple permissions. For example:
- `4` (Read) + `2` (Write) = `6` (Read + Write)
- `4` (Read) + `1` (Execute) = `5` (Read + Execute)


### 📂 Structure of Permissions

A file or directory’s permissions are divided into three groups:
1. **👤 User (Owner)**: The first digit in the numeric mode.
2. **👥 Group**: The second digit.
3. **🌍 Others (Everyone else)**: The third digit.

Each digit is the sum of the permission values (Read = 4, Write = 2, Execute = 1). For example, if you want the owner to have `read` and `write` permissions, the numeric value would be **6** (4 for read + 2 for write).

### 🛠️ Using `chmod` with Numeric Mode

To assign permissions using numerical values, use the `chmod` command followed by the numeric representation and the file or directory name.

#### 📋 Examples:

**Example 1: Assign `read`, `write`, and `execute` to the owner; `read` and `write` to the group; and `read` to others**

```bash
chmod 764 filename
```

- **7**: `read` (4), `write` (2), and `execute` (1) for the owner.
- **6**: `read` (4) and `write` (2) for the group.
- **4**: `read` (4) for others.

Run `ls -l filename` to verify the permissions:

```
-rwxrw-r-- filename
```

---

**Example 2: Remove all permissions**

```bash
chmod 000 filename
```

- **0**: No permissions for the owner, group, or others.

Run `ls -l filename` to verify the permissions:

```
---------- filename
```

---

**Example 3: Assign `read` and `write` to the owner, and no permissions to group and others**

```bash
chmod 600 filename
```

- **6**: `read` (4) and `write` (2) for the owner.
- **0**: No permissions for the group.
- **0**: No permissions for others.

Run `ls -l filename` to verify the permissions:

```
-rw------- filename
```

---

**Example 4: Assign `read` and `write` to the owner, and `read` to others**

```bash
chmod 604 filename
```

- **6**: `read` (4) and `write` (2) for the owner.
- **0**: No permissions for the group.
- **4**: `read` (4) for others.

Run `ls -l filename` to verify the permissions:

```
-rw----r-- filename
```

---

**Example 5: Assign `execute` to everyone**

```bash
chmod 111 filename
```

- **1**: `execute` (1) for the owner.
- **1**: `execute` (1) for the group.
- **1**: `execute` (1) for others.

Run `ls -l filename` to verify the permissions:

```
--x--x--x filename
```

---

**Example 6: Assign `read` and `execute` to the owner, group, and others**

```bash
chmod 555 filename
```

- **5**: `read` (4) and `execute` (1) for the owner.
- **5**: `read` (4) and `execute` (1) for the group.
- **5**: `read` (4) and `execute` (1) for others.

Run `ls -l filename` to verify the permissions:

```
-r-xr-xr-x filename
```
