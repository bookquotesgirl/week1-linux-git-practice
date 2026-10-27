# Week 1 Linux Hands-on Lab: First Project Workspace

## Overview
This project demonstrates basic Linux command-line operations using the macOS Terminal. The tasks include directory creation, file management, searching for files, and inspecting running processes.

## Project Structure

```text
cloud-devops/
└── week1/
    ├── README.md
    └── scripts/
        └── notes.txt
```

## Tasks and Commands

### 1. Create the Project Workspace

Created the `cloud-devops` directory on the Desktop and navigated into it. Then created the `week1` directory.

```bash
cd ~/Desktop
mkdir cloud-devops
cd cloud-devops
mkdir week1
cd week1
```

**Result:** Created the project workspace at `~/Desktop/cloud-devops/week1`.

### 2. Create a File

Created a file named `notes.txt`.

```bash
touch notes.txt
```

**Result:** An empty `notes.txt` file was created in the `week1` directory.

### 3. Add Text to the File

Added text to the file using the `echo` command and the output redirection operator (`>`).

```bash
echo "this is notes" > notes.txt
```

**Result:** The file now contains the text `this is notes`.

### 4. Create a Directory

Created a directory named `scripts`.

```bash
mkdir scripts
```

**Result:** The `scripts` directory was created inside `week1`.

### 5. Move the File

Moved `notes.txt` into the `scripts` directory using the `mv` command.

```bash
mv notes.txt scripts/
```

**Result:** The file is now located at `week1/scripts/notes.txt`.

### 6. Search for the File

Initially, I tried:

```bash
find notes.txt
```

This returned an error because `find` expects a search starting point, and the file had already been moved into the `scripts` directory.

I then tried:

```bash
find . notes.txt
```

The command displayed the current directory and its contents, including `./scripts/notes.txt`, but also reported an error because `notes.txt` was interpreted as an additional starting path.

The correct command for searching for the file recursively from the current directory is:

```bash
find . -name "notes.txt"
```

**Expected result:**

```text
./scripts/notes.txt
```

**What I learned:** The `find` command searches for files and directories. The `.` specifies the current directory, while `-name` specifies the filename to search for.

### 7. Inspect Running Processes

Used the `ps aux` command to list running processes.

```bash
ps aux
```

The output included process information such as:

- **USER:** The user running the process.
- **PID:** The process identification number.
- **%CPU:** CPU usage.
- **%MEM:** Memory usage.
- **COMMAND:** The command or application associated with the process.

**Result:** Identified running processes and their corresponding PIDs. For example, the output included a process with PID `23830`.

*Note: Process IDs can change whenever applications restart, so the PID shown above is specific to the captured session.*

## Commands Learned

| Command | Purpose |
|---|---|
| `cd` | Navigate between directories |
| `mkdir` | Create a directory |
| `touch` | Create an empty file |
| `echo` | Print text or write text to a file |
| `>` | Redirect output into a file, replacing its contents |
| `mv` | Move or rename files and directories |
| `find` | Search for files and directories |
| `ps aux` | Display running processes and their details |

## Skills Practiced

- Navigating the filesystem using Terminal.
- Creating directories and files.
- Writing text to a file.
- Moving files between directories.
- Searching for files using `find`.
- Inspecting running processes and identifying their PIDs.
- Understanding command syntax and troubleshooting errors.


