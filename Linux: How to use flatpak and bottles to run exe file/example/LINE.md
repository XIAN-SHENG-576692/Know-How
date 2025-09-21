[[2023-07-29]] 01:59
[[2025-08-31]] 08:32
[[2025-09-01]] 06:26 to [[2025-09-01]] 07:39

# Download

[如何在Linux安裝電腦版Line，使用Bottles管理Wine容器](https://ivonblog.com/posts/linux-bottles-install-line/)

1. Download LineInst.exe
    按這個連結 https://desktop.line-scdn.net/win/new/LineInst.exe 下載最新版 LineInst.exe。
    這個連結你大可放心點選，因為我是直接從Line官網複製下來的。如果你不放心，請用偽裝成Windows User-Agent的瀏覽器造訪Line官網，自行複製取得exe下載連結。


# Details

[如何在Linux安裝電腦版Line，使用Bottles管理Wine容器](https://ivonblog.com/posts/linux-bottles-install-line/)


1. Create New Bottle
    - Application

2. Set details
    - Settings
        - Runner
            - kron4ek-wine-10.13-am...
        - DXVK
            - Disabled
        - VKD3D
            - Disabled
        - Windows Version
            - Windows 11
    - Dependencies
        - cjkfonts
        - d3dcompiler_47
        - vcredist2022

3. Run Executable
    - LineInst.exe

# Shortcuts

```
/home/<USER>/.var/app/com.usebottles.bottles/data/bottles/bottles/LINE/drive_c/users/<USER>/AppData/Local/LINE/bin/LineLauncher.exe
```

# How to backup LINE chat history

[如何在Linux安裝電腦版Line，使用Bottles管理Wine容器](https://ivonblog.com/posts/linux-bottles-install-line/)

根據網路上說法，電腦版Line備份聊天記錄是直接將Line的目錄複製下來，重裝Line後再把資料覆蓋。

Bottles建立的「假C槽」位於~/.var/app/com.usebottles.bottles/data/bottles/bottles/Line/drive_c/，Line下載的照片影片會放到假C槽下的/users/user/Downloads目錄。

而Line的聊天紀錄資料位於假C槽下的/users/user/AppData/Local/LINE，要備份就是複製整個LINE目錄。「理論上」這裡的聊天紀錄可以移到Windows上繼續用。
