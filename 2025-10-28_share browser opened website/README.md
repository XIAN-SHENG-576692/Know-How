[[2025-10-27]] 23:51
Android Chrome 網頁下載.mhtml

```bash
adb forward tcp:9222 localabstract:chrome_devtools_remote
wget -O tabs.json http://localhost:9222/json/list
```

```bash
adb shell
ls /dev/socket
ls /dev/socket/devtools_remote*
```
