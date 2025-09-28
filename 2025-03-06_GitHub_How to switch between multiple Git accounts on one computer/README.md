# How to switch between multiple Git accounts on one computer

[Git 踩坑紀錄（三）一台電腦切換多個 Git 帳號. 公司的 Git 帳號與個人的 Git 帳號傻傻分不清。 | by TSENG FU CHUN / 豆腐 | Medium](https://tsengbatty.medium.com/%E4%B8%80%E5%8F%B0%E9%9B%BB%E8%85%A6%E5%88%87%E6%8F%9B%E5%A4%9A%E5%80%8B-git-%E5%B8%B3%E8%99%9F-561351700876)

[[2025-03-06]] 18:35

1. Clear cached credentials

    ```bash
    git credential reject https://github.com
    ```

2. Generate a new SSH key

    ```bash
    ssh-keygen -t rsa -b 4096 -C <GITHUB_EMAIL>
    ```
    - You will then be asked for `<FILE_NAME>`.
    - When it's completed, two file `<FILE_NAME>` and `<FILE_NAME>.pub` will be generated at `~/.ssh`

3. Modify `~/.ssh/config`

    Add this content to `~/.ssh/config`

    ```plaintext
    Host <HOST_NAME>
        HostName github.com
        User git
        IdentityFile ~/.ssh/<FILE_NAME>
    ```
4. Add the SSH key to your GitHub account

    1. Copy `<FILE_NAME>.pub` full content
    2. `Login you GitHub` -> `Settings` -> `SSH and GPG keys` -> `New SSH key`
    3. Paste the `<FILE_NAME>.pub` full content

5. Testing

    ```bash
    ssh -T git@<HOST_NAME>
    ```

# Check user config

```bash
git config --list | grep user
```

or

```bash
git config --global user.name
git config --global user.email
```

# Modify global user config

```bash
git config --global user.name <NEW_USER_NAME>
git config --global user.email <NEW_USER_EMAIL>
```

# Modify remote

```bash
git remote set-url origin git@<HOST_NAME>:<REPO>
```
