## Note:
Though Project_documents was initially created in the home directory, I am moving that to the Question2 folder for uploading in git as I am using different folders for different question answers and not uploading the whole home directory.

## Task 1: Project Workspace Setup

**Command:**
```shell
mkdir ~/documents
```

**Verification:**

```shell
ls -ld ~/documents
```

**Output:**

```
drwxr-xr-x 2 suraj suraj 4096 Jan  4 04:54 /home/suraj/documents
```

**Explanation:**
I created a new directory called "documents" in my home directory using mkdir command to serve as my project workspace.

---

## Task 2: File Creation

**Command:**

```shell
cd ~/documents
touch plan.txt
```

**Verification:**

```shell
ls -la
```

**Output:**

```
total 8
drwxr-xr-x 2 suraj suraj 4096 Jan  4 04:55 .
drwxr-xr-x 5 suraj suraj 4096 Jan  4 04:54 ..
-rw-r--r-- 1 suraj suraj    0 Jan  4 04:55 plan.txt
```

**Explanation:**
I navigated into the documents directory and created an empty file named plan.txt using the touch command.

---

## Task 3: Content Addition

**Command:**

```shell
echo "This is my project plan for building a trading system using Python and React" > plan.txt
```

**Verification:**

```shell
cat plan.txt
```

**Output:**

```
This is my project plan for building a stocks trading system using Python and React
```

**Explanation:**
I added content to plan.txt using echo with output redirection, writing my project plan about building a trading system.

---

## Task 4: File Metadata Verification

**Command:**

```shell
ls -l plan.txt
```

**Output:**

```
-rw-r--r-- 1 suraj suraj 77 Jan  4 04:59 plan.txt
```

**Explanation:**
The ls -l command displayed detailed metadata including permissions (rw-r--r--), owner (suraj), file size (77 bytes), and modification timestamp.

---

## Task 5: File Duplication

**Command:**

```shell
cp plan.txt plan_copy.txt
```

**Verification:**

```shell
ls -la
```

**Output:**

```
total 16
drwxr-xr-x 2 suraj suraj 4096 Jan  4 05:00 .
drwxr-xr-x 5 suraj suraj 4096 Jan  4 04:54 ..
-rw-r--r-- 1 suraj suraj   77 Jan  4 04:59 plan.txt
-rw-r--r-- 1 suraj suraj   77 Jan  4 05:00 plan_copy.txt
```

**Explanation:**
I created a backup copy of plan.txt named plan_copy.txt using the cp command, which preserved both content and file size.

---

## Task 6: Directory Renaming

**Command:**

```shell
cd ~
mv documents project_documents
```

**Verification:**

```shell
ls -ld project_documents
```

**Output:**

```
drwxr-xr-x 2 suraj suraj 4096 Jan  4 05:00 project_documents
```

**Explanation:**
I first changed to the home directory (got outside the directory to rename it), then renamed documents to project_documents using the mv command.

---

## Task 7: Archival Structure

**Command:**

```shell
cd ~/project_documents
mkdir archive
```

**Verification:**

```shell
ls -la
```

**Output:**

```
total 20
drwxr-xr-x 3 suraj suraj 4096 Jan  4 05:01 .
drwxr-xr-x 5 suraj suraj 4096 Jan  4 05:00 ..
drwxr-xr-x 2 suraj suraj 4096 Jan  4 05:01 archive
-rw-r--r-- 1 suraj suraj   77 Jan  4 04:59 plan.txt
-rw-r--r-- 1 suraj suraj   77 Jan  4 05:00 plan_copy.txt
```

**Explanation:**
I created a subdirectory named "archive" inside project_documents for organizing backup and old files.

---

## Task 8: File Organization

**Command:**

```shell
mv plan_copy.txt archive/
```

**Verification:**

```shell
ls -la archive/
```

**Output:**

```
total 12
drwxr-xr-x 2 suraj suraj 4096 Jan  4 05:02 .
drwxr-xr-x 3 suraj suraj 4096 Jan  4 05:01 ..
-rw-r--r-- 1 suraj suraj   77 Jan  4 05:00 plan_copy.txt
```

**Explanation:**
I moved the backup file plan_copy.txt into the archive subdirectory using mv command to better organize my project files.

---

## Task 9: Recursive Listing

**Command:**

```shell
cd ~/project_documents
ls -R
```

**Output:**

```
.:
archive  plan.txt

./archive:
plan_copy.txt
```

**Explanation:**
The ls -R command displayed the complete directory structure recursively, showing all files and subdirectories with their contents in a tree-like format.

---

## Task 10: Path Verification

**Command:**

```shell
readlink -f ~/project_documents/archive/plan_copy.txt
```

**Output:**

```
/home/suraj/project_documents/archive/plan_copy.txt
```

**Explanation:**
I used readlink -f to display the absolute full path of plan_copy.txt, confirming its exact location in the filesystem after being moved to the archive directory.

