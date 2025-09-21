[[2023-07-29]] 01:59

[[2025-08-31]] 08:32

[[2025-09-01]] 06:26 to [[2025-09-01]] 07:39

# Install Flatpak and Bottles

1. Install Flatpak (Reference : [Linux系統如何安裝Flatpak軟體套件？使用教學 · Ivon的部落格](https://ivonblog.com/posts/linux-flatpak-introduction/))

    1. 請到Flatpak官網查詢各大Linux發行版的安裝方法，例如Ubuntu LTS，執行以下指令安裝Flatpak套件：
        ```bash
        sudo apt update
        sudo apt install flatpak
        ```
    2. (Optional) 
        建議不想每次更新應用程式都打密碼的使用者，加上--user給個別使用者加入套件庫。這樣使用者就能免密碼安裝應用程式，且Flatpak只會安裝程式到該名使用者的家目錄。解除安裝應用程式亦不需要sudo。

        ```bash
        flatpak remote-add --user --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
        ```
        或者，將套件庫加入到整個系統，這樣所有使用者都可以使用該軟體（有時可能要加上sudo）：

        ```bash
        flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
        ```
    3. 做完以上措施後，重開機後就能用Flatpak安裝軟體。

2. Install Bottles (Reference: [如何在Linux執行Windows exe檔，用Bottles管理多版本的Wine容器 · Ivon的部落格](https://ivonblog.com/posts/setup-linux-bottles/))

    1. 安裝Bottles，輸入y確認
        ```bash
        flatpak install flathub com.usebottles.bottles
        ```

    2. 建議預先開放權限，允許Bottles給Linux新增桌面捷徑
        ```bash
        flatpak override com.usebottles.bottles --user --filesystem=xdg-data/applications
        ```

    3. 開放Bottles讀取你的常用目錄，例如「下載」目錄，避免在執行exe的時候出現權限問題
        ```bash
        flatpak override com.usebottles.bottles --user --filesystem=xdg-download
        ```

# How to Add Shortcuts

Some exe file is installation program, You need to create a shortcuts for future to use instead of reinstalling.

1. Press `Add Shortcuts`
2. Select the launch file.

# How to add Desktop Entry

1. Your target bottle Details page -> Programs -> Kebab menu icon -> Add Desktop Entry
2. A new desktop file will be created at this path
    ```
    /home/<USER>/.local/share/applications
    ```

## How to create Desktop Shortcuts

```bash
cp ~/.local/share/applications/<DESKTOP_FILE> ~/Desktop
```

# How to backup a bottle

[如何在Linux安裝電腦版Line，使用Bottles管理Wine容器](https://ivonblog.com/posts/linux-bottles-install-line/)

1. Download your target bottle Details page -> kebab menu icon -> Full Backup...

2. kebab menu icon -> Import...

# How to auto launch you bottle while power on

[如何在Linux安裝電腦版Line，使用Bottles管理Wine容器](https://ivonblog.com/posts/linux-bottles-install-line/)

```bash
cp ~/.local/share/applications/<DESKTOP_FILE> ~/.config/autostart/
```


