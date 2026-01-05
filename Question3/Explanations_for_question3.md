## Note:
Though sample_data and sample_hard files were initially created in the home directory, I have moved those to the Question3 folder for uploading in git as I am using different folders for different question answers and not uploading the whole home directory.

## Task 1: File Creation

**Command:**
```shell
cd ~
echo "This is sample data for testing hard and symbolic links in Linux filesystem" > sample_data.txt
```

**Output:**

```
This is sample data for testing hard and symbolic links in Linux filesystem
```

**Explanation:**
I created a file named sample_data.txt in my home directory with sample text for testing links.

---

##Task 2: Hard Link Creation

**Command:**

```shell
ln sample_data.txt sample_hard.txt
```

**Explanation:**
I created a hard link sample_hard.txt that points directly to the same inode as sample_data.txt, so both names reference identical data on disk.

---

## Task 3: Symbolic Link Creation

**Command:**

```shell
ln -s sample_data.txt sample_soft.txt
```

**Output:**

```
lrwxrwxrwx 1 suraj suraj 15 Jan  4 06:41 sample_soft.txt -> sample_data.txt
```

**Explanation:**
I created a symbolic link sample_soft.txt using ln -s, which stores just a path reference to sample_data.txt rather than the actual data.

---

## Task 4: Inode Verification

**Command:**

```shell
ls -i sample_data.txt sample_hard.txt sample_soft.txt
```

**Output:**

```
37089 sample_data.txt
37089 sample_hard.txt
37090 sample_soft.txt
```

**Explanation:**
The command showed that sample_data.txt and sample_hard.txt share the same inode (37089), while sample_soft.txt has a different inode (37090).

---

## Task 5: Inode Analysis

**Command:**

```shell
ls -li sample_data.txt sample_hard.txt sample_soft.txt
```

**Output:**

```
37089 -rw-r--r-- 2 suraj suraj 76 Jan  4 06:38 sample_data.txt
37089 -rw-r--r-- 2 suraj suraj 76 Jan  4 06:38 sample_hard.txt
37090 lrwxrwxrwx 1 suraj suraj 15 Jan  4 06:41 sample_soft.txt -> sample_data.txt
```

**Explanation:**
sample_data.txt and sample_hard.txt share inode 37089 because hard links point to the same physical data, while sample_soft.txt has inode 37090 since it's just a pointer file storing the path to the original file.

---

## Task 6: File Metadata Inspection

**Command:**

```shell
stat sample_data.txt
```

**Output:**

```
  File: sample_data.txt
  Size: 76              Blocks: 8          IO Block: 4096   regular file
Device: 8,48    Inode: 37089      Links: 2
Access: (0644/-rw-r--r--)  Uid: ( 1000/  suraj)   Gid: ( 1000/  suraj)
Access: 2026-01-04 06:39:56.274962466 +0000
Modify: 2026-01-04 06:38:36.034550052 +0000
Change: 2026-01-04 06:40:57.045051335 +0000
 Birth: 2026-01-04 06:38:36.034550052 +0000
```

**Explanation:**
The stat command displayed complete metadata including permissions (644), size (76 bytes), inode number (37089), link count (2), and all timestamps.

---

## Task 7: Disk Usage Check

**Command:**

```shell
du -sh ~
```

**Output:**

```
1.2M    /home/suraj
```

**Explanation:**
The du -sh command showed my home directory uses 1.2 MB of disk space in a human-readable format.

---

##Task 8: File Size Overview

**Command:**

```shell
ls -lh ~
```

**Output:**

```
total 16K
drwxr-xr-x 6 suraj suraj 4.0K Jan  4 06:27 LinuxLabAssignment
drwxr-xr-x 3 suraj suraj 4.0K Jan  4 05:32 project_documents
-rw-r--r-- 2 suraj suraj   76 Jan  4 06:38 sample_data.txt
-rw-r--r-- 2 suraj suraj   76 Jan  4 06:38 sample_hard.txt
lrwxrwxrwx 1 suraj suraj   15 Jan  4 06:41 sample_soft.txt -> sample_data.txt
```

**Explanation:**
The command listed all files and directories in my home directory with their sizes in human-readable format, showing both the 76-byte files and larger directories.

---

## Task 9: Link Deletion Test

**Commands:**

```shell
rm sample_soft.txt
ls -l sample_data.txt
cat sample_data.txt
ls -l sample_data.txt sample_hard.txt
```

**Output:**

```
-rw-r--r-- 2 suraj suraj 76 Jan  4 06:38 sample_data.txt
This is sample data for testing hard and symbolic links in Linux filesystem
-rw-r--r-- 2 suraj suraj 76 Jan  4 06:38 sample_data.txt
-rw-r--r-- 2 suraj suraj 76 Jan  4 06:38 sample_hard.txt

```

**Explanation:**
After deleting the symbolic link, I verified that sample_data.txt was completely unaffected by displaying its contents and checking both hard links, confirming they still share the same inode and data.

---

## Task 10: Disk Utility Demonstration

**Commands:**

```shell
du -sh ~
df -h
df -h ~
```

**Output:**

```
# du -sh ~
1.2M    /home/suraj

# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/sdd       1007G  1.7G  954G   1% /
none            3.9G     0  3.9G   0% /usr/lib/modules/6.6.87.2-microsoft-standard-WSL2
tmpfs           793M   20K  793M   1% /run/user/1000
C:\             223G   92G  132G  42% /mnt/c
D:\             252G   14G  239G   6% /mnt/d
E:\             403G   22G  381G   6% /mnt/e
F:\             277G   13G  264G   5% /mnt/f

# df -h ~
Filesystem      Size  Used Avail Use% Mounted on
/dev/sdd       1007G  1.7G  954G   1% /
```

**Explanation:**
The du command shows space used by my home directory (1.2M), while df -h displays all mounted filesystems with their total size, used space, and availability showing the main Linux filesystem using only 1% of 1007G.
