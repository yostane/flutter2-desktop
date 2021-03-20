# myapp

A new Flutter project.

## Getting started on WSL2 Ubuntu

https://flutter.dev/desktop

On WSL2, follow [this tutorial](https://medium.com/@japheth.yates/the-complete-wsl2-gui-setup-2582828f4577) to enable GUI apps 

```sh
sudo apt update
# install prerequisites
sudo apt install git unzip xz-utils zip libglu1-mesa ninja-build libgtk-3-dev build-essential
# download the SDK into the current folder
wget https://storage.googleapis.com/flutter_infra/releases/stable/linux/flutter_linux_2.0.3-stable.tar.xz
# unzip the SDK
tar xf ~/Downloads/flutter_linux_2.0.3-stable.tar.xz
```

Add the flutter/bin folder to your path and open a new terminal.

```sh
flutter precache 
flutter config --enable-linux-desktop
flutter crteate . # add linux support for existing projet
flutter run -d linux --verbose
```


## Troubleshooting

```log
[  +92 ms] Building Linux application...
[  +28 ms] <- compile package:myapp/main.dart
[   +3 ms] executing: [build/linux/debug/] cmake -G Ninja -DCMAKE_BUILD_TYPE=Debug /mnt/d/dev/flutter/flutter2_desktop/linux
[ +203 ms] -- Checking for module 'gtk+-3.0'
[        ] --   No package 'gtk+-3.0' found
[   +1 ms] CMake Error at /usr/share/cmake-3.16/Modules/FindPkgConfig.cmake:463 (message):
[   +4 ms]   A required package was not found
[        ] Call Stack (most recent call first):
[        ]   /usr/share/cmake-3.16/Modules/FindPkgConfig.cmake:643 (_pkg_check_modules_internal)
[        ]   flutter/CMakeLists.txt:24 (pkg_check_modules)
```

```log
[ +126 ms] -- Checking for module 'liblzma'
[   +3 ms] --   No package 'liblzma' found
[   +1 ms] CMake Error at /usr/share/cmake-3.16/Modules/FindPkgConfig.cmake:463 (message):
[   +1 ms]   A required package was not found
[        ] Call Stack (most recent call first):
[        ]   /usr/share/cmake-3.16/Modules/FindPkgConfig.cmake:643 (_pkg_check_modules_internal)
[        ]   flutter/CMakeLists.txt:28 (pkg_check_modules)
[  +12 ms] -- Configuring incomplete, errors occurred!
```


- Fix by `flutter clean`

```log
[   +8 ms] CMake Error at cmake_install.cmake:61 (file):
[   +2 ms]   file INSTALL cannot copy file
```

