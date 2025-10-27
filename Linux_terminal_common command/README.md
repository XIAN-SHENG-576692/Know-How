[[2025-08-28]]

### How to Check UID in Linux

| Method            | Command                                    | Description                        |
| ----------------- | ------------------------------------------ | ---------------------------------- |
| Direct            | `id -u`                                    | Show current user’s UID            |
| Specific user     | `id -u username`                           | Show UID of given account          |
| Full info         | `id`                                       | Show UID, GID, and groups          |
| From /etc/passwd  | `grep 'username' /etc/passwd`              | Check user info directly           |
| Extract field     | `grep 'username' /etc/passwd \| cut -d: -f3` | Only extract UID field             |

---

[[2025-09-16]]

[linux - Check free disk space for current partition in Bash - Stack Overflow](https://stackoverflow.com/questions/8110530/check-free-disk-space-for-current-partition-in-bash)

[disk usage - How do I find the amount of free space on my hard drive? - Ask Ubuntu](https://askubuntu.com/questions/73160/how-do-i-find-the-amount-of-free-space-on-my-hard-drive)

```bash
df -h --total
```

---

[[2025-09-24]] 21:58

[Linux man pages](https://linux.die.net/man/)

[善用 man 指令查詢 Linux 線上手冊（Man Page） – G. T. Wang](https://blog.gtwang.org/linux/linux-man-page-command-examples/)

---

[[2025-10-27]] 01:31
- Fedora kill PID方法.mhtml

```bash
kill <PID>
```

```bash
kill -9 <PID>
```

```bash
pkill <Process_Name>
```

```bash
pkill -9 <Process_Name>
```

```bash
ps aux | grep <Process_Name>
```

```bash
pgrep <Process_Name>
```

---

[[2025-10-27]] 11:21
mtp://<DEVICE_NAME>/Internal%20storage/Android/data/com.splendapps.voicerec/files/Recordings

