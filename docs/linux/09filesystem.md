### **Understanding File System Hierarchy and Structure**

The **Linux file system hierarchy** defines how files and directories are organized and accessed within the operating system.
Unlike Windows, which uses drive letters (C:, D:), Linux has a **single root directory (`/`)** under which all other directories and files are contained.

This structure is crucial for system organization, file management, and administrative tasks.

---

#### **The Root Directory (`/`)**

The root directory is the **top-most level** of the Linux file system.
Every other file or directory branches out from `/`.

Example:

```
/
├── bin
├── boot
├── dev
├── etc
├── home
├── lib
├── media
├── mnt
├── opt
├── root
├── sbin
├── tmp
├── usr
└── var
```

---

#### **Key Directories and Their Functions**

| Directory | Description                                                       |
| --------- | ----------------------------------------------------------------- |
| `/bin`    | Contains essential user binaries (commands like `ls`, `cp`, `mv`) |
| `/boot`   | Stores bootloader files and the Linux kernel                      |
| `/dev`    | Represents hardware devices as files (e.g., `/dev/sda`)           |
| `/etc`    | Holds system configuration files                                  |
| `/home`   | Contains personal directories for each user                       |
| `/lib`    | Shared libraries required for system programs                     |
| `/media`  | Mount point for removable media (e.g., USB drives, CDs)           |
| `/mnt`    | Temporary mount point for external file systems                   |
| `/opt`    | Optional software packages installed manually                     |
| `/root`   | Home directory of the root (superuser) account                    |
| `/sbin`   | System binaries used for administrative tasks                     |
| `/tmp`    | Temporary files created by users and applications                 |
| `/usr`    | User applications, libraries, and documentation                   |
| `/var`    | Variable data files such as logs, caches, and spool files         |

---

#### **Relative vs Absolute Paths**

* **Absolute Path:** Specifies the complete path from the root directory (`/`).

  ```
  /home/cyberadmin/Documents/report.txt
  ```
* **Relative Path:** Specifies the path relative to the current working directory.

  ```
  Documents/report.txt
  ```

---

#### **Special Directory Symbols**

| Symbol | Meaning                             |
| ------ | ----------------------------------- |
| `.`    | Refers to the current directory     |
| `..`   | Refers to the parent directory      |
| `~`    | Refers to the user’s home directory |
| `/`    | Refers to the root directory        |

---

#### **Navigating the File System**

* View current directory:

  ```
  pwd
  ```
* Change directory:

  ```
  cd /home/cyberadmin
  ```
* List files and directories:

  ```
  ls -l /
  ```

---
