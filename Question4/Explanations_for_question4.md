## Task 1: System Uptime Verification

**Command:**
```shell
uptime -p
```

**Output:**

```
up 4 hours, 9 minutes
```

**Explanation:**
The system has been running for 4 hours and 9 minutes since the last boot.

---

## Task 2: User Process Listing

**Command:**

```shell
ps -u $USER -f
```

**Output:**

```
UID        PID  PPID  C STIME TTY          TIME CMD
suraj      298   297  0 03:27 pts/0    00:00:00 -bash
suraj      343   298  0 03:27 ?        00:00:00 /usr/lib/systemd/systemd --user
suraj      346   343  0 03:27 ?        00:00:00 (sd-pam)
suraj      370   299  0 03:27 pts/1    00:00:00 -bash
suraj     2054   298  0 07:37 pts/0    00:00:00 ps -u suraj -f
```

**Explanation:**
I listed all processes running under my account showing their PIDs, parent PIDs, and execution details.

---

## Task 3: CPU Usage Analysis

**Command:**

```shell
top -u $USER
```

**Output:**

```
top - 07:40:33 up 4:14, 1 user, load average: 0.00, 0.00, 0.00
Tasks: 24 total, 1 running, 23 sleeping, 0 stopped, 0 zombie
%Cpu(s): 0.2 us, 0.2 sy, 0.0 ni, 99.6 id, 0.0 wa, 0.0 hi, 0.0 si, 0.0 st
MiB Mem : 7921.2 total, 7365.8 free, 458.3 used, 249.8 buff/cache

  PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
 2059 suraj     20   0    9316   5504   3328 R   0.0   0.1   0:00.03 top
  298 suraj     20   0    6072   4992   3456 S   0.0   0.1   0:00.28 bash
  343 suraj     20   0   20320  11136   9088 S   0.0   0.1   0:00.18 systemd
```

**Explanation:**
The top command displayed real-time system statistics showing minimal CPU usage across my processes.

---

## Task 4: Background Process Execution

**Commands:**

```shell
sleep 300 &
jobs
ps -u $USER | grep sleep
```

**Output:**

```
 2070[^1]
+  Running                 sleep 300 &[^1]
2070 pts/0    00:00:00 sleep
```

**Explanation:**
I started a background process using \& and verified it was running with job and PID 2070.

---

## Task 5: Process Priority Management

**Commands:**

```shell
ps -u $USER | grep sleep
renice -n 10 -p 2070
```

**Output:**

```
2070 pts/0    00:00:00 sleep
2070 (process ID) old priority 0, new priority 10
```

**Explanation:**
I successfully changed the niceness value of the sleep process (PID 2070) from 0 to 10 using renice, which lowers its priority (higher nice values mean lower CPU priority).

---

## Task 6: Memory Usage Monitoring

**Command:**

```shell
free -h
```

**Output:**

```
              total        used        free      shared  buff/cache   available
Mem:          7.7Gi       453Mi       7.2Gi       3.5Mi       250Mi       7.3Gi
Swap:         2.0Gi          0B       2.0Gi
```

**Explanation:**
The system has 7.7GB RAM with only 453MB in use and 7.3GB available, showing excellent memory headroom.

---

## Task 7: Disk Space Inspection

**Command:**

```shell
df -h ~
```

**Output:**

```
Filesystem      Size  Used Avail Use% Mounted on
/dev/sdd       1007G  1.7G  954G   1% /
```

**Explanation:**
My home directory resides on a 1TB filesystem with only 1% utilization and 954GB available space.

---

## Task 8: Shell Identification

**Command:**

```shell
echo $SHELL
```

**Output:**

```
/bin/bash
+  Done                    sleep 300[^1]
```

**Explanation:**
I'm using Bash shell (/bin/bash), and during this task the background sleep job completed.

---

## Task 9: Output Redirection

**Command:**

```shell
uname -a > system_report.txt
cat system_report.txt
```

**Output:**

```
Linux DESKTOP-11T3744 6.6.87.2-microsoft-standard-WSL2 #1 SMP PREEMPT_DYNAMIC Thu Jun  5 18:30:46 UTC 2025 x86_64 x86_64 x86_64 GNU/Linux
```

**Explanation:**
I redirected system information into a file, capturing kernel details, hostname, and architecture information.

---

## Task 10: Disk Usage Visualization

**Command:**

```shell
ncdu ~
```

**Output:**

```
ncdu 1.19 ~ Use the arrow keys to navigate, press ? for help
--- /home/suraj -----------------------------------------------
  
1.9 MiB [###########################] /LinuxLabAssignment
16.0 KiB [           ] /project_documents
12.0 KiB [       ] /.local
8.0 KiB [       ] /.config
4.0 KiB [       ] /.cache
4.0 KiB [       ]  .bashrc
4.0 KiB [       ]  .bash_history
4.0 KiB [       ]  .viminfo
4.0 KiB [       ]  .profile
4.0 KiB [       ]  .bash_logout
4.0 KiB [       ]  .gitconfig
4.0 KiB [       ]  .lesshst
0.0   B [          ]  .sudo_as_admin_successful
0.0   B [          ]  .motd_shown
```

**Explanation:**
ncdu provides an interactive ncurses-based disk usage analyzer that visually displays directory sizes with navigation support, making it easy to identify which directories consume the most space.
