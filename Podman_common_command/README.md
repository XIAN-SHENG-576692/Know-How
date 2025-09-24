# Podman: common command

```bash
podman info
```

---

```bash
grep "^$USER:" /etc/subuid /etc/subgid || echo "❗你的 subuid/subgid 沒配置，rootless 會不穩"
# 若沒配置，請用 root 執行（替換 <user> 為你的帳號）：
# usermod --add-subuids 100000-165535 --add-subgids 100000-165535 <user>
```
- [[2025-08-29]] 13:00 (Podman Dev Containers Issue.mhtml)

---

```bash
podman login ghcr.io
```
```bash
podman logout ghcr.io
```
- [[2025-09-02]] 16:16

---

```bash
podman pull <IMAGE>
```

---

```bash
podman image list
```
```bash
podman images
```

```bash
podman images --digests
```
- [[2025-08-28]]

---

```bash
podman container list
```

```bash
podman ps -a
```
- [[2025-08-27]] 17:40

---

```bash
podman system df    # 檢查 image、containers、volumes 磁碟佔用 
podman system df -v # 詳細顯示各 image 的共用與獨有佔用
```
- [[2025-09-03]] 19:11

---

```bash
podman image inspect <IMAGE_NAME_OR_ID> --format '{{ .Config.User }}'
```

```bash
podman image inspect <IMAGE_NAME_OR_ID>
```

```bash
podman run --rm --entrypoint '' <IMAGE_NAME_OR_ID> id
```

```bash
podman run --rm --entrypoint '' <IMAGE_NAME_OR_ID> cat /etc/passwd
```
- [[2025-09-04]] 10:39 (查看 Podman 預設用戶.mhtml)

---

```bash
podman tag <IMAGE_ID> <IMAGE_NEW_NAME>:<IMAGE_NEW_TAG>
```

```bash
podman tag <IMAGE_OLD_NAME>:<IMAGE_OLD_TAG> <IMAGE_NEW_NAME>:<IMAGE_NEW_TAG>
```
- [[2025-08-29]] 13:00 (Podman Dev Containers Issue.mhtml)

---

```bash
podman run --rm -it \
  --userns=keep-id \
  --group-add keep-groups \
  --device=/dev/bus/usb \
  -v <DIR_A>:/work:Z -w /work \
  <IMAGE> bash
```
- [[2025-08-27]] 16:47
- [[2025-08-28]] 10:39

---

```bash
podman stop -a
```
- [[2025-08-28]] 10:39

---

```bash
podman rmi <IMAGE>
```
- [[2025-08-28]] 10:39

---

```bash
podman system prune -a
```
- [[2025-08-29]] 11:19

---

```bash
podman rm -af
podman pod rm -af
podman network prune -f
podman system prune -af
```
- [[2025-08-29]] 13:00 (Podman Dev Containers Issue.mhtml)

---

```bash
podman volume rm -f <VOLUME> buildx_buildkit_default_state
```
- [[2025-08-29]] 13:00 (Podman Dev Containers Issue.mhtml)

---

```bash
rm -rf ~/.config/Code/User/globalStorage/<CONTAINERS>/*
```

```bash
rm -rf ~/.cache/Code/User/globalStorage/<CONTAINERS>/*
```
- [[2025-08-29]] 13:00 (Podman Dev Containers Issue.mhtml)

---

```bash
systemctl --user enable --now podman.socket
systemctl --user status podman.socket
```
- [[2025-08-29]] 13:00 (Podman Dev Containers Issue.mhtml)
