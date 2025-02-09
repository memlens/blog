+++
date = '2025-02-09T01:27:32+01:00'
draft = false
title = 'Welcome to Linux 5: Mastering Redirection & Pipelines'
description = "Take control of data flow in the terminal! Learn how to redirect input, output, and errors, and combine commands with pipelines for efficient workflows."
tags = ["Linux", "Redirection", "Pipelines", "Linux Commands", "Terminal", "Command Line"]
categories = ["Linux Tutorials", "Welcome to Linux"]
+++

### **1. Introduction: Control the Data Flow Like a Pro!** 🚀

Now that you know how to navigate the filesystem and work with files, it’s time to **unlock the full power of the command line** by mastering **redirection** and **pipelines**. These features let you control where output goes, how errors are handled, and how commands interact with each other.

Ready? Let’s dive in! 🔥

---

### **2. Standard Input, Output, and Error Streams**

Every command in Linux interacts with three data streams:

| **Stream** | **Description** | **File Descriptor** |
|-----------|---------------|----------------|
| **stdin** | Standard input (keyboard or file) | `0` |
| **stdout** | Standard output (default: terminal) | `1` |
| **stderr** | Standard error messages | `2` |

You can **redirect** these streams using special operators.

---

### **3. Redirecting Output: Save Command Results to a File**

#### **3.1 Overwriting Output (`>`)**
Redirect a command’s output to a file (overwriting existing content):
```bash
$ ls > files.txt  # Saves output of 'ls' into files.txt
```
Now, `files.txt` contains the directory listing.

#### **3.2 Appending Output (`>>`)**
Use `>>` to **append** output to an existing file instead of overwriting:
```bash
$ echo "New log entry" >> logs.txt
```

---

### **4. Redirecting Input: Use a File as Command Input (`<`)**
Some commands accept input from a file instead of the keyboard:
```bash
$ sort < names.txt  # Sorts the contents of names.txt
```
This sends `names.txt` as input to `sort`, which then outputs the sorted results.

---

### **5. Redirecting Errors: Handle Error Messages (`2>`, `2>>`)** 🚨
#### **5.1 Redirecting Errors to a File**
Sometimes, errors clutter your screen. Redirect them to a file instead:
```bash
$ ls /nonexistent 2> error.log  # Save error message to error.log
```
#### **5.2 Redirecting Errors and Output Together (`&>` or `2>&1`)**
To **save both output and errors** in the same file:
```bash
$ command &> output.log
```
Or:
```bash
$ command > output.log 2>&1
```

---

### **6. The Power of Pipelines (`|`): Connect Commands** 🔗
A pipeline (`|`) **connects multiple commands**, passing the output of one command as input to another.

#### **6.1 Example: Counting Files**
```bash
$ ls | wc -l  # Counts the number of files in a directory
```
- `ls` lists the files.
- `wc -l` counts the number of lines.

#### **6.2 Example: Filtering Output with `grep`**
```bash
$ ps aux | grep firefox  # Find running Firefox processes
```
- `ps aux` lists all processes.
- `grep firefox` filters for processes related to Firefox.

#### **6.3 Example: Sorting and Removing Duplicates**
```bash
$ cat names.txt | sort | uniq
```
- `sort` sorts the lines alphabetically.
- `uniq` removes duplicate entries.

---

### **7. Using `tee`: View and Save Output Simultaneously** 📄
Normally, when you redirect output to a file, you **don’t see it** on the terminal. The `tee` command **displays output while saving it**:
```bash
$ ls | tee filelist.txt
```
Now you can see the list **and** save it to `filelist.txt`.

---

### **8. Discarding Unwanted Output (`/dev/null`)**
To **suppress** output, redirect it to `/dev/null`:
```bash
$ command > /dev/null 2>&1  # Ignore both output and errors
```
This is useful in scripts when you **only care about success/failure**.

---

### **9. Practical Examples** 🛠️

#### **9.1 Find the Most Common Word in a File**
```bash
$ cat file.txt | tr ' ' '\n' | sort | uniq -c | sort -nr | head -10
```
- `tr ' ' '\n'` replaces spaces with newlines.
- `sort` sorts the words.
- `uniq -c` counts occurrences.
- `sort -nr` sorts by frequency.
- `head -10` shows the top 10 words.

#### **9.2 Monitor System Resource Usage**
```bash
$ ps aux | sort -rk 3,3 | head -5
```
This sorts processes by CPU usage (`-rk 3,3`) and shows the top 5.

---

### **10. Next Steps: Leveling Up!** 🚀
Now you know how to **redirect output, handle errors, and chain commands together** with pipelines! Next, we’ll dive into **process management**, where you’ll learn how to control running programs effectively. Stay tuned! 🎯

