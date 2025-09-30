# Flutter

[[2025-09-25]]

[[2025-09-28]]

[Continuous delivery with Flutter | Flutter](https://docs.flutter.dev/deployment/cd)
- [GitHub - nabilnalakath/flutter-githubaction: This is a flutter project featured on the official website, for CI-CD integration using Github Actions.](https://github.com/nabilnalakath/flutter-githubaction#)
    - [GitHub - subosito/flutter-action: Flutter environment for use in GitHub Actions. It works on Linux, Windows, and macOS.](https://github.com/subosito/flutter-action)

---

[[2025-09-24]]

[github action搭建flutter流水线 | Distant Vicinity](https://kzs.moe/blog/015-flutter-github-workflow)
- [GitHub - realth000/tsdm\_client: 天使动漫论坛官方跨平台客户端](https://github.com/realth000/tsdm_client)

---

[[2025-09-25]]

[为应用签名  |  Android Studio  |  Android Developers](https://developer.android.com/studio/publish/app-signing?hl=zh-cn)

---

[[2025-09-25]]

[GitHub - cirruslabs/docker-images-flutter: Docker Images for Flutter](https://github.com/cirruslabs/docker-images-flutter)

[Package flutter · GitHub](https://github.com/cirruslabs/docker-images-flutter/pkgs/container/flutter)

---

[[2025-09-02]]

[[2025-09-03]]

[[2025-09-04]]

[[2025-09-25]]

[hub.docker.com/r/mingc/android-build-box/dockerfile](https://hub.docker.com/r/mingc/android-build-box/dockerfile)

[GitHub - mingchen/docker-android-build-box: An optimized docker image includes Android, Kotlin, Flutter sdk.](https://github.com/mingchen/docker-android-build-box)

# Melos

[[2025-09-29]]

```bash
#!/bin/bash
# install_melos.sh
# Install Melos, then create a profile script under /etc/profile.d/ to add "$HOME/.pub-cache/bin" to your PATH.

set -e

# Install melos
dart pub global activate melos

# Create a profile script under /etc/profile.d/ to add "$HOME/.pub-cache/bin" to your PATH.
echo 'PATH="$PATH":"$HOME/.pub-cache/bin"' | sudo tee /etc/profile.d/add_pub_cache_bin_to_path.sh
sudo chmod +x /etc/profile.d/add_pub_cache_bin_to_path.sh
```

---

[[2025-09-29]] 17:24

[melos/.gitignore at main · invertase/melos · GitHub](https://github.com/invertase/melos/blob/main/.gitignore)

[GitHub - bluefireteam/melos-action: An environment with Melos activated for use in GitHub Actions.](https://github.com/bluefireteam/melos-action)
