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
