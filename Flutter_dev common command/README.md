# Flutter: Development common command

---

[[2025-09-03]] 11:31

Rescan real devices

```bash
adb kill-server
```

```bash
adb start-server
```

```bash
adb devices -l
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

---

[[2025-09-27]] 23:00
- NDK版本衝突解決.mhtml
- [Should the default ndkVersion be updated to support 16KB Page Size Requirement? · Issue #175022 · flutter/flutter](https://github.com/flutter/flutter/issues/175022?utm_source=chatgpt.com)
- [flutter/packages/flutter\_tools/gradle/src/main/kotlin/FlutterExtension.kt at 3.36.0-0.5.pre · flutter/flutter · GitHub](https://github.com/flutter/flutter/blob/3.36.0-0.5.pre/packages/flutter_tools/gradle/src/main/kotlin/FlutterExtension.kt)

```
"$FLUTTER_HOME/packages/flutter_tools/gradle/src/main/kotlin/FlutterExtension.kt"
```

---

```bash
dart run build_runner build
```

```bash
dart run build_runner build --delete-conflicting-outputs
```

```bash
dart run build_runner clean
```
