### Basic Commands in Linux

Linux commands are the fundamental building blocks for interacting with the operating system through the terminal.
They allow users to navigate directories, manage files, and perform system operations efficiently.

---

#### **1. `pwd` — Print Working Directory**

Displays the **current directory path** where the user is located.

**Syntax:**

```
pwd
```

**Example Output:**

```
/home/cyberadmin/Documents
```

---

#### **2. `ls` — List Directory Contents**

Lists files and directories in the current or specified directory.

**Syntax:**

```
ls [options] [directory]
```

**Common Options:**

* `-l` → Long format listing (shows permissions, owner, size, etc.)
* `-a` → Shows hidden files (files starting with `.`)
* `-h` → Displays sizes in human-readable format

**Example:**

```
ls -lah /home/cyberadmin
```

---

#### **3. `cd` — Change Directory**

Moves between directories.

**Syntax:**

```
cd [directory_path]
```

**Examples:**

```
cd /home/cyberadmin/Documents
cd ..        # Move one level up
cd ~         # Go to the home directory
```

---

#### **4. `mkdir` — Make Directory**

Creates new directories.

**Syntax:**

```
mkdir [directory_name]
```

**Example:**

```
mkdir projects
```

To create nested directories:

```
mkdir -p projects/python/scripts
```

---

#### **5. `rmdir` — Remove Empty Directory**

Deletes an **empty directory**.

**Syntax:**

```
rmdir [directory_name]
```

**Example:**

```
rmdir old_folder
```

For non-empty directories, use `rm -r`.

---

#### **6. `touch` — Create Empty Files or Update Timestamps**

Creates a new empty file or updates an existing file’s modification date.

**Syntax:**

```
touch [file_name]
```

**Example:**

```
touch report.txt
```

---

#### **7. `cp` — Copy Files or Directories**

Copies files or directories from one location to another.

**Syntax:**

```
cp [options] source destination
```

**Common Options:**

* `-r` → Recursively copy directories
* `-v` → Verbose mode (shows progress)

**Example:**

```
cp file.txt /home/cyberadmin/backup/
cp -rv project/ /home/cyberadmin/backup/
```

---

#### **8. `mv` — Move or Rename Files**

Moves files to another location or renames them.

**Syntax:**

```
mv [source] [destination]
```

**Examples:**

```
mv file.txt /home/cyberadmin/Documents/
mv oldname.txt newname.txt
```

---

#### **9. `rm` — Remove Files or Directories**

Deletes files or directories permanently.

**Syntax:**

```
rm [options] [file_name]
```

**Common Options:**

* `-r` → Remove directories and their contents recursively
* `-f` → Force removal (no prompt)
* `-v` → Verbose mode

**Examples:**

```
rm oldfile.txt
rm -rf temp_folder/
```

