# 在 Android Studio 搭建 Flutter 環境

1. 安裝 Android Studio
2. 依照 [在 Android Studio 或 IntelliJ 里开发 Flutter 应用 - Flutter 中文文档 - Flutter 中文开发者网站 - Flutter](https://flutter.cn/docs/development/tools/android-studio) 的指示完成安裝

## Windows 在 Android Studio 搭建 Flutter 環境

1. 依照 [[#在 Android Studio 搭建 Flutter 環境]] 的指示
2. 設定環境變數
	1. 根據 [Day 3 準備Flutter開發環境(一)](https://ithelp.ithome.com.tw/m/articles/10264355) 的指示
		1. 在[https://flutter.dev/docs/get-started/install/windows](https://flutter.dev/docs/get-started/install/windows) 下載最新的SDK版本。  
		2. 解壓縮(不要儲存於C槽)。  
		3. 設定環境變數：配置Flutter國內映象地址。  
			- 
				新增系統環境變數
				
				| User 變數                | System 變數                    |
				| ------------------------ | ------------------------------ |
				| PUB_HOSTED_URL           | https://pub.flutter-io.cn/     |
				| FLUTTER_STORAGE_BASE_URL | https://storage.flutter-io.cn/ 
			- 
				新增 User 的 Path 的變數
				- `D:\flutter_windows_3.16.0-stable\flutter\bin`
	1. 根據 [Day 4 準備Flutter開發環境(二)](https://ithelp.ithome.com.tw/m/articles/10265079) 的指示
		1. `File` -> `Settings` -> `Plugins` -> 搜尋 Flutter 並安裝 -> `重新啟動 IDE`
		2. `File` -> `New Projects Settings` -> `Default Project Structure` -> 複製這個 Path
		3. 
			- 
				新增系統環境變數 
				
				| User 變數        | System 變數         |
				| ---------------- | ------------------- |
				| ANDROID_HOME     | 貼上剛才複製的 Path |
				| ANDROID_SDK_ROOT | 貼上剛才複製的 Path |
			- 新增 System 的 Path 的變數
				- 貼上剛才複製的 Path\\build-tools
				- 貼上剛才複製的 Path\\platform-tools
				- 貼上剛才複製的 Path\\tools
1. 在 `cmd` 輸入 (參考 [I am getting error "cmdline-tools component is missing" after installing Flutter and Android Studio... I added the Android SDK. How can I solve them? - Stack Overflow](https://stackoverflow.com/questions/68236007/i-am-getting-error-cmdline-tools-component-is-missing-after-installing-flutter))
	```bash
	flutter doctor --android-licenses
	```

2. 在 `cmd` 輸入，確認沒有錯誤 (參考 [Set up \`flutter driver\` Run configuration on Android Studio · Issue #85769 · flutter/flutter · GitHub](https://github.com/flutter/flutter/issues/85769))
	```bash
	flutter doctor
	flutter doctor -v
	```

3. 如果還有問題
	1. 參考 [dart - Flutter doctor error - Android sdkmanager tool not found. Windows - Stack Overflow](https://stackoverflow.com/questions/60475481/flutter-doctor-error-android-sdkmanager-tool-not-found-windows)
		- 
			Android toolchain - develop for Android devices X cmdline-tools component is missing Run `path/to/sdkmanager --install "cmdline-tools;latest"`
			
			This error means your "**Android SDK Command-line Tools are missing**"
			
			1. Open Android Studio
			2. In the Menu bar , click **Tools**(4th last)
			3. choose **SDK Tools** panel
			4. Tick Android **SDK Command-line Tools**
			5. Click **Apply** at bottom of the window
			
			IT WILL START DOWNLOADING the missing component
	
	1. [flutter - Dart SDK is not configured - Stack Overflow](https://stackoverflow.com/questions/48650831/dart-sdk-is-not-configured)
		- 
			I had the same problem after importing a flutter project from git. These are the steps to solve the problem.
			
			1. File->Settings->Language & Framework->Flutter
			2. Choose flutter SDK path: the first time we install flutter, we choose the location where the flutter should be installed. Choose this location.
			3. Click OK and the android studio will refresh. Carry on if the problem is solved.
			4. If you are still stuck with the error.
			5. Goto [this](https://flutter.io/get-started/install/) link and install Dart.
			6. Goto the same place in settings, ..Language & Framework->Dart and chose the SDK location.
			
			This solved the issues for me.

# 如何建立新的 Flutter 專案

`File` -> `New` -> `New Flutter Project` -> `Flutter` -> `...`

參考 [How To Run Your Flutter App On Android, iOS, Web, And Macos In 2023 - YouTube](https://www.youtube.com/watch?v=lvq0J1W8OEY)

