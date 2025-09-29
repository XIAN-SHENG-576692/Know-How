# How to Configure VS Code to Use Podman

Make VS Code/Dev Containers point to **Podman’s Docker-compatible API**:

### 1. Enable Podman’s rootless API socket

Get user uid
```bash
id -u <USER_NAME>
```

Set Podman socket
```bash
systemctl --user enable --now podman.socket
# Socket will be at: /run/user/<USER_UID>/podman/podman.sock
```

Check
```bash
systemctl --user status podman.socket
```

If needed, point tools’ Docker endpoint to this socket:
```bash
export DOCKER_HOST=unix:///run/user/<USER_UID>/podman/podman.sock
```

> This is the recommended method from Red Hat’s official documentation. [Red Hat Docs](https://docs.redhat.com/en/documentation/red_hat_enterprise_linux/8/html/building_running_and_managing_containers/using-the-container-tools-api#enabling-the-podman-api-using-systemd-in-rootless-mode_using-the-container-tools-api)

> Community blog posts have full examples. 
> - [blog.while-true-do.io](https://blog.while-true-do.io/podman-configure-vscode-for-containers/)  
> - [Red Hat Developer](https://developers.redhat.com/articles/2023/02/14/remote-container-development-vs-code-and-podman)

> You can also install `podman-docker`, which makes the system’s `docker` command actually call Podman (useful if an extension calls `docker` directly and bypasses Podman). [butui.me](https://butui.me/posts/podman-compose-quick-guide/)

### 2. Configure `dev.containers.dockerPath` in VS Code

System-level setting (stable & secure)

In VS Code **User Settings** (`settings.json`), add:
```json
"dev.containers.dockerPath": "podman"
```

This tells the Dev Containers extension to use `podman` instead of the Docker CLI. This is the officially recommended way. [VS Code Docs](https://code.visualstudio.com/remote/advancedcontainers/docker-options)

⚠️ **Note:** This setting is **application scope only**, meaning it must be defined in user settings, not in `.devcontainer/devcontainer.json` or `.vscode/settings.json`. [GitHub issue](https://github.com/microsoft/vscode-remote-release/issues/8728)

| Platform          | How to do it                                                  | Advantage                          |
| ----------------- | ------------------------------------------------------------- | ---------------------------------- |
| Inside VS Code    | `Ctrl + Shift + P` → `Preferences: Open User Settings (JSON)` | Quick and precise editing          |
| File Explorer/CLI | Edit `~/.config/Code/User/settings.json`                      | Easier to back up or sync settings |

---

### 3. (Optional) Add environment-related settings in `devcontainer.json`

In your `.devcontainer/devcontainer.json`:
```json
{
  "settings": {
    "dev.containers.dockerPath": "podman"
  },
  "containerEnv": {
    "container": "podman"
  },
  "runArgs": ["--userns=keep-id"],
  "remoteUser": "vscode"
}
```
> This approach (mentioned in community articles) helps VS Code detect that you’re using Podman and adjust container permissions accordingly. [Reference Blog](https://blog.mirochiu.page/2022/01/vscodepodmanremote-developementcontainer.html)

# Others

### Configure `devcontainer.json` with Podman flags
For example:
- `--userns=keep-id` is specific to Podman.  
- On Fedora/SELinux, often add `--security-opt=label=disable`.  

Docs: [Podman Documentation](https://docs.podman.io/en/v4.6.1/markdown/options/userns.container.html), [Red Hat Portal](https://access.redhat.com/solutions/7082427)
