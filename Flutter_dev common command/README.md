# Flutter: Development common command

[[2025-09-03]] 11:31

```bash
adb kill-server
```

```bash
adb start-server
```

```bash
adb devices
```

---

[[2025-09-03]]
- NDK 安裝與配置.mhtml

```bash
cd android/
./gradlew tasks --all | grep externalNativeBuild
```

---

[[2025-09-03]] 16:32

Repair pub cache (usually not needed)
```bash
flutter pub cache repair
```

Delete the cache directly (it will take a while)
```bash
rm -rf ~/.pub-cache
```

```bash
flutter clean
```

```bash
flutter pub get
```

