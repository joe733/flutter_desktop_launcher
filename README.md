# Desktop Launcher

Flutter Desktop Mac OS / Linux Launcher

## Coming from [Official Docs](https://flutter.dev/docs/get-started/install/linux)?

If you've alread download [flutter-sdk](https://storage.googleapis.com/flutter_infra/releases/stable/linux/flutter_linux_v1.12.13+hotfix.8-stable.tar.xz)(v1.12.13+hotfix.8-stable) from the official docs and do want to run flutter apps natively, you can follow the steps given below:

Assuming you've alread set-up the path:
1. `$ flutter channel master` - swithces the channel to the master branch
2. `$ flutter upgrade` - (optional) you may want to upgrade
3. `$ flutter config --enable-linux-desktop` or `$ export ENABLE_FLUTTER_DESKTOP=true`
4. `$ flutter devices` after which you should be able to see:<br>
![](https://miro.medium.com/max/374/1*gty3MXYLAS41l93vTAqfjQ.png)
5. `$ flutter run` to run flutter in Native Mode.

---
> The following is the fork from putraxor/flutter_desktop_launcher


## Getting Started
You can view how to setup this launcher on Youtube: [Run Flutter on Desktop Platform without Emulator](https://www.youtube.com/watch?v=QFD2r4C3fHs).

![Flutter Desktop Hot Reload](https://github.com/putraxor/flutter_macos_launcher/blob/master/demo.gif)

How to setup for VSCode:
- Download for [Linux/Debian](https://github.com/putraxor/flutter_desktop_launcher/raw/master/linux_launcher.zip) or [Mac OS](https://github.com/putraxor/flutter_desktop_launcher/releases/download/v0.0.1-mac/Archive.zip)
- Extract zip archive
- Copy `Flutter.app` (Mac) / `linux_launcher + all files` (Linux) to your project
- Modify your `main.dart` add target platform to `Fuchsia`

  ```java
  import 'package:flutter/foundation.dart'

  show debugDefaultTargetPlatformOverride; // for desktop embedder

  void main() {
    debugDefaultTargetPlatformOverride = TargetPlatform.fuchsia; // for desktop embedder
    runApp(MyApp());
  }
  ```

- Build flutter bundle inside your project `flutter build bundle`
- Run `Flutter.app` or `./linux_launcher`
- In VS Code create Launch Configuration:
  ```javascript
  {
    "version": "0.2.0",
    "configurations": [
      {
        "name": "Flutter Desktop",
        "request": "attach",
        "deviceId": "flutter-tester",
        "observatoryUri": "http://127.0.0.1:49494/",
        "type": "dart"
      }
    ]
  }
  ```
- Run `Flutter Desktop` now `Hot Reload` is working

## How to setup for Android Studio:
[![Flutter Desktop on Android Studio](https://img.youtube.com/vi/imgl0GTopYM/0.jpg)](https://www.youtube.com/watch?v=imgl0GTopYM)
