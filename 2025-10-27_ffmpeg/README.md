你可以用 ffmpeg（免費又強大的影片工具）很輕鬆地把 .mkv 影片在指定時間點分成兩段。下面是最常用的做法 👇

# 🧰 一、安裝 ffmpeg
如果你還沒安裝：
- Windows：到 ffmpeg.org/download.html 下載並設定到環境變數。
- macOS：輸入 `brew install ffmpeg`
- Linux (Ubuntu)：輸入 `sudo apt install ffmpeg`
- Fedora
    1. Fedora 由於預設沒帶 ffmpeg（授權原因），要先啟用 RPM Fusion：
    2. 
        ```bash
        sudo dnf install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm
        ```
    3. 
        ```bash
        sudo dnf install ffmpeg ffmpeg-devel
        ```

✅ 完成後可用以下指令確認：
```bash
ffmpeg -version
```

# 🎬 二、分割影片的指令
假設你的影片叫做 video.mkv，想在 1 小時 23 分 45 秒（也就是 01:23:45）分成兩段：
```bash
ffmpeg -i video.mkv -t 01:23:45 -c copy part1.mkv
ffmpeg -ss 01:23:45 -i video.mkv -c copy part2.mkv
```
- `-i` video.mkv → 指定輸入影片
- `-t` 01:23:45 → 輸出前半段長度（到這個時間為止）
- `-ss` 01:23:45 → 從該時間點開始截取後半段
- `-c` copy → 不重新編碼（超快，也不會壓損畫質）

⚠️ 小提醒
若想要更精確（例如切在非關鍵影格），可以改用：

```bash
ffmpeg -ss 01:23:45 -i video.mkv -to 02:00:00 -c copy part2.mkv
```
或在第二段加上 `-avoid_negative_ts 1`。

如果輸出後音畫不同步，可加上 `-async 1` 或去掉 `-c copy` 改成 `-c:v libx264 -c:a aac`（這樣會重新編碼，速度慢但最穩）。

⚠️ 小提醒
若影片時間點不是關鍵影格（GOP 開頭），可能會造成切點不精準或音畫略不同步。
→ 想要最穩定可改成重新編碼：
```bash
ffmpeg -i movie.mkv -t 00:45:00 -c:v libx264 -c:a aac part1.mkv
ffmpeg -ss 00:45:00 -i movie.mkv -c:v libx264 -c:a aac part2.mkv
```
想切多段的話，可以重複以上方式，只要調整 -t 和 -ss 的時間即可。
