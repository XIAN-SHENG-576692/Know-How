# Podman `--userns=keep-id` stuck issue

[[2025-08-27]]
- Podman 的 userns 卡住解決方法.mhtml 有提到 BUG 觸發原因及解決辦法

## Steps

1. Ensure fuse-overlayfs already installed
    ```bash
    which fuse-overlayfs
    ```

2. Add the following content to `~/.config/containers/storage.conf`
    ```ini
    [storage]
    driver = "overlay"

    [storage.options.overlay]
    mount_program = "/usr/bin/fuse-overlayfs"
    ```
