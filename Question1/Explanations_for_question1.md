## Task 1: User Identity Verification

### Part A: Display Current Username

**Command:**
```bash
whoami
```

**Output:**

```
suraj
```

** Explanation:**
When I typed `whoami`, it showed "suraj" which is my current username on this Linux system.

---

### Part B: Display User and Group Information

**Command:**

```bash
id
```

**Output:**

```
uid=1000(suraj) gid=1000(suraj) groups=1000(suraj),4(adm),24(cdrom),27(sudo),30(dip),46(plugdev),100(users)
```

** Explanation:**
The `id` command showed me my user ID is 1000 and I belong to several groups including `sudo`, which gives me admin rights on this system.

---

## Task 2: Workspace Validation

### Part A: Print Working Directory

**Command:**

```bash
pwd
```

**Output:**

```
/home/suraj/LinuxLabAssignment/Question1
```

** Explanation:**
This showed me I'm currently working inside the Question1 folder in my home directory.

---

### Part B: List Directory Contents

**Command:**

```bash
ls -la
```

**Output:**

```
total 8
drwxr-xr-x 2 suraj suraj 4096 Jan  2 14:14 .
drwxr-xr-x 3 suraj suraj 4096 Jan  2 14:14 ..
```

** Explanation:**
The `ls -la` command listed all files with details, and right now my directory only has the current (`.`) and parent (`..`) directory entries.

---

## Task 3: Environment Confirmation File

**Commands:**

```bash
echo "Linux user environment verified" > user_info.txt
cat user_info.txt
```

**Output:**

```
Linux user environment verified
```

** Explanation:**
I successfully created the `user_info.txt` file with the required text and verified it by viewing the contents with `cat`.

---

## Task 4: File Integrity Check

**Command:**

```bash
wc -m user_info.txt
```

**Output:**

```
32 user_info.txt
```

** Explanation:**
The word count command with `-m` flag counted 32 characters in my file including spaces and the newline character.

---

## Task 5: Learning the Tools

**Command:**

```bash
man mkdir
```

**Key Option Found:**

```
-p, --parents
    no error if existing, make parent directories as needed
```

** Explanation:**
I found that `mkdir -p` is really useful because it creates all nested directories at once without giving errors. For example, `mkdir -p folder1/folder2/folder3` creates all three directories in one command.

---

## Task 6: Home Directory Inspection

**Command:**

```bash
ls ~
```

**Output:**

```
LinuxLabAssignment
```

** Explanation:**
This listed everything in my home directory, and I currently have just one folder called `LinuxLabAssignment`.

---

## Task 7: Log Investigation

**Commands:**

```bash
echo -e "System started\nadmin logged in\nUser error\nadmin performed backup" > log.txt
grep "admin" log.txt
```

**Output:**

```
admin logged in
admin performed backup
```

** Explanation:**
I created a sample log file and then used `grep` to search for lines containing "admin", which showed me only the two matching lines.

---

## Task 8: System Information Check

**Command:**

```bash
uname -r
```

**Output:**

```
6.6.87.2-microsoft-standard-WSL2
```

** Explanation:**
This displayed the kernel version showing I'm running WSL2 with Linux kernel 6.6.87.2 provided by Microsoft.

---

##  Task 9: Network Connectivity Test

**Command:**

```bash
ping -c 4 www.google.com
```

**Output:**

```
PING www.google.com (142.251.221.132) 56(84) bytes of data.
64 bytes from cgk03s04-in-f4.1e100.net (142.251.221.132): icmp_seq=1 ttl=117 time=26.5 ms
64 bytes from cgk03s04-in-f4.1e100.net (142.251.221.132): icmp_seq=2 ttl=117 time=27.3 ms
64 bytes from cgk03s04-in-f4.1e100.net (142.251.221.132): icmp_seq=3 ttl=117 time=27.1 ms
64 bytes from cgk03s04-in-f4.1e100.net (142.251.221.132): icmp_seq=4 ttl=117 time=27.9 ms

--- www.google.com ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3125ms
rtt min/avg/max/mdev = 26.539/27.204/27.899/0.487 ms
```

** Explanation:**
I sent 4 ping requests to Google and got all 4 replies back with average time around 27ms and zero packet loss, so my network is working fine.

---

## Task 10: System Health Awareness

**Command:**

```bash
uptime
```

**Output:**

```
14:43:20 up 28 min, 1 user, load average: 0.00, 0.00, 0.00
```

** Explanation:**
The system has been running for 28 minutes with 1 user logged in. The load averages are all 0.00 which means the CPU isn't busy right now and the system is running smoothly.

