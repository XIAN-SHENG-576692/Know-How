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

---

[[2025-09-26]] 12:00
- NDK 配置錯誤解決.mhtml
- [java - Keystore file does not exist - Stack Overflow](https://stackoverflow.com/questions/42663114/keystore-file-does-not-exist)

```bash
keytool -list -v -keystore <KEYSTORE_PATH>
```
