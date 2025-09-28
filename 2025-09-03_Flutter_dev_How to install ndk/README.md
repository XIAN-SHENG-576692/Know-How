# Flutter: How to install NDK

## Reference

[[2025-09-03]]
- NDK 安裝與配置.mhtml

[[2025-09-23]]
- [Environment variables  |  Android Studio  |  Android Developers](https://developer.android.com/tools/variables)
- [Install and configure the NDK and CMake  |  Android Studio  |  Android Developers](https://developer.android.com/studio/projects/install-ndk)
- [sdkmanager  |  Android Studio  |  Android Developers](https://developer.android.com/tools/sdkmanager)

## Steps

There are several ways to install the Android NDK, as shown below.

You can choose one of the following.

### Install in "$ANDROID_HOME/ndk"

1. Ensure "$ANDROID_HOME/ndk" have write permission

2. Install NDK and CMake

    ```bash
    yes | "$ANDROID_HOME/cmdline-tools/latest/bin/sdkmanager" "ndk;<NDK_VERSION>" "cmake;<CMAKE_VERSION>" --install
    ```

### Install in custom path

- [[2025-09-03]]
    - NDK 安裝與配置.mhtml

---

1. 選一個你有寫入權限的 SDK 根目錄，並指定給 sdkmanager：

    ```bash
    mkdir -p "<CUSTOM_SDK_PATH>"
    ```

    ```bash
    yes | "$ANDROID_HOME/cmdline-tools/latest/bin/sdkmanager" --sdk_root="<CUSTOM_SDK_PATH>" "ndk;<NDK_VERSION>" "cmake;<CMAKE_VERSION>" --install
    ```
    - [Install and configure the NDK and CMake  |  Android Studio  |  Android Developers](https://developer.android.com/studio/projects/install-ndk)

2. 讓 Gradle/AS 找得到這個新 SDK：

    設 環境變數（擇一）：

    ```bash
    export ANDROID_SDK_ROOT="<CUSTOM_SDK_PATH>"
    ```

    ```bash
    export ANDROID_HOME="<CUSTOM_SDK_PATH>"
    ```

    ANDROID_SDK_ROOT/ANDROID_HOME 皆可指向 SDK；重要的是指到可寫入的路徑。
    - [sdkmanager  |  Android Studio  |  Android Developers](https://developer.android.com/tools/sdkmanager)

    或在 `android/local.properties` 設：
    ```BASH
    sdk.dir=/home/vscode/Android/Sdk
    ```

3. 重建：

    ```bash
    cd android
    ./gradlew :app:assembleDebug
    ```

    這做法符合官方建議：用 NDK side-by-side 在 SDK 目錄安裝多個 NDK，專案再以 android.ndkVersion 指定版本，建置就會自動挑對版。 
    - [Install and configure the NDK and CMake  |  Android Studio  |  Android Developers](https://developer.android.com/studio/projects/install-ndk)

## Others

### Check Environment variables

```bash
echo "$ANDROID_HOME"
```

### Check "$ANDROID_HOME" write permission

```bash
ls -la "$ANDROID_HOME"
```

```bash
ls -la "$ANDROID_HOME/ndk"
```

### Change owner

```bash
echo "$USER"
```

```bash
sudo chown -R "$USER":"$USER" "$ANDROID_HOME"
```

### Set write permission

```bash
chmod u+w "$ANDROID_HOME"
```

### List NDK

```bash
"$ANDROID_HOME/cmdline-tools/latest/bin/sdkmanager" --list
```

```bash
"$ANDROID_HOME/cmdline-tools/latest/bin/sdkmanager" --list_installed
```

```bash
"$ANDROID_HOME/cmdline-tools/latest/bin/sdkmanager" --sdk_root=<CUSTOM_SDK_PATH> --list
```
