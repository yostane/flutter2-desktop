# myapp

A new Flutter project.

## Getting started on WSL2 Ubuntu

```sh
# install prerequisites
sudo apt install git unzip xz-utils zip libglu1-mesa ninja-build
# download the SDK into the current folder
wget https://storage.googleapis.com/flutter_infra/releases/stable/linux/flutter_linux_2.0.3-stable.tar.xz
# unzip the SDK
tar xf ~/Downloads/flutter_linux_2.0.3-stable.tar.xz
```

Add the flutter/bin folder to your path and open a new terminal.

```sh
flutter precache 
flutter config --enable-linux-desktop
```

