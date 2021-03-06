# Building GAPID

To build GAPID, Android SDK, Android NDK, and JDK 8 are needed. The `do` script
will try to deduce their locations and populate the default paths via the
environment variable `ANDROID_HOME`, `ANDROID_NDK_ROOT`, and `JAVA_HOME`,
respectively. If these environment variables are not defined, you will need to
manually specify the locations for the *DKs during the `do config` step.
When manually specifying locations, please note that the `do` script cannot
resolve paths containing environment variables currently.

Please see the following for detailed steps on each platform.

## Windows

### Install [Go 1.8](https://storage.googleapis.com/golang/go1.8.windows-amd64.msi)

### Install Mingw-w64 Toolchain
* Install [msys2](http://repo.msys2.org/distrib/x86_64/msys2-x86_64-20161025.exe).
* Open the `MSYS2 MinGW 64-bit` terminal.
* Type: `pacman -Syu --noconfirm` and press enter.
* Close and reopen the msys2 terminal.
* Note that pacman may need to update itself before updating other packages, so repeat the above two steps until pacman no longer updates anything.
* Type: `pacman -S mingw-w64-x86_64-gcc --noconfirm` and press enter.
* Close the msys2 terminal

### Install Android SDK
* Unzip the [Android SDK](https://dl.google.com/android/repository/tools_r25.2.3-windows.zip) to a directory of your choosing.
* Using the unzipped `tools\android.bat` download:
  * Android 5.0.1 (API 21)
    * SDK Platform
  * Android SDK Build-tools 21.1.2

### Install the Android NDK
* Unzip the [Android NDK](https://dl.google.com/android/repository/android-ndk-r13b-windows-x86_64.zip) to a directory of your choosing.

### Install [CMake](https://cmake.org/files/v3.7/cmake-3.7.1-win32-x86.msi).

### Install Ninja
* Unzip the [Ninja executable](https://github.com/ninja-build/ninja/releases/download/v1.7.2/ninja-win.zip) to a directory of your choosing.

### Install [Python 3.6](https://www.python.org/ftp/python/3.6.0/python-3.6.0-amd64.exe)

### Install [JDK 8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)

### Get the source
In a terminal type:
```
go get github.com/google/gapid
cd %GOPATH%\src\github.com\google\gapid
git submodule update --init
```
The `go get` and `git submodule` commands will fetch the source of this project and all third party repositories, so it may take a while to complete.

### Configure build
In a terminal type:
```
cd %GOPATH%\src\github.com\google\gapid
do config
```
And follow the instructions to configure the build.

### Building
In a terminal type:
```
cd %GOPATH%\src\github.com\google\gapid
do build
```
The build output will be in the directory you specified with `do config`.

---

## MacOS

### Install [Go 1.8](https://storage.googleapis.com/golang/go1.8.darwin-amd64.pkg)

### Install Android SDK
* Unzip the [Android SDK](https://dl.google.com/android/repository/tools_r25.2.3-macosx.zip) to a directory of your choosing.
  * Instead, if you have Homebrew, you can install via `brew install android-sdk` and the default installation location would be
    `$HOMEBREW_PREFIX/opt/android-sdk`, where `$HOMEBREW_PREFIX` can be found using `brew config`.
* Using `tools/android` download:
  * Android 5.0.1 (API 21)
    * SDK Platform
  * Android SDK Build-tools 21.1.2

### Install Android NDK
* Unzip the [Android NDK](https://dl.google.com/android/repository/android-ndk-r13b-darwin-x86_64.zip) to a directory of your choosing.
  * Instead, if you have Homebrew, you can install via `brew install android-ndk` and the default installation location would be
    `$HOMEBREW_PREFIX/opt/android-ndk`, where `$HOMEBREW_PREFIX` can be found using `brew config`.

### Install [CMake](https://cmake.org/files/v3.7/cmake-3.7.1-Darwin-x86_64.dmg)
  * Instead, if you have Homebrew, you can install via `brew install cmake`.

### Install Ninja
* Unzip the [Ninja executable](https://github.com/ninja-build/ninja/releases/download/v1.7.2/ninja-mac.zip) to a directory of your choosing.
  * Instead, if you have Homebrew, you can install via `brew install ninja`.

### Install [Python 3.6](https://www.python.org/ftp/python/3.6.0/python-3.6.0-macosx10.6.pkg)
  * Instead, if you have Homebrew, you can install via `brew install python3`.

### Install [JDK 8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
* You can inspect JDK home locations via the `/usr/libexec/java_home` utility.
  * For JDK 8, the command is `/usr/libexec/java_home -v 1.8`.

### Get the source
In a terminal type:
```
go get github.com/google/gapid
cd $GOPATH/src/github.com/google/gapid
git submodule update --init
```
The `go get` and `git submodule` commands will fetch the source of this project and all third party repositories, so it may take a while to complete.

### Configure build
In a terminal type:
```
cd $GOPATH/src/github.com/google/gapid
./do config
```
And follow the instructions to configure the build.

### Building
In a terminal type:
```
cd $GOPATH/src/github.com/google/gapid
./do build
```
The build output will be in the directory you specified with `do config`.

---

## Linux

### Install [Go 1.8](https://storage.googleapis.com/golang/go1.8.linux-amd64.tar.gz)

### Install Android SDK
* Unzip the [Android SDK](https://dl.google.com/android/repository/tools_r25.2.3-linux.zip) to a directory of your choosing.
* Using `tools/android` download:
  * Android 5.0.1 (API 21)
    * SDK Platform
  * Android SDK Build-tools 21.1.2

### Install Android NDK
* Unzip the [Android NDK](https://dl.google.com/android/repository/android-ndk-r13b-linux-x86_64.zip) to a directory of your choosing.

### Install [CMake](https://cmake.org/files/v3.7/cmake-3.7.1-Linux-x86_64.sh).

### Install Ninja
* Unzip the [Ninja executable](https://github.com/ninja-build/ninja/releases/download/v1.7.2/ninja-linux.zip) to a directory of your choosing.

### Install Python 3.6

### Install [JDK 8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)

### Get the source
In a terminal type:
```
go get github.com/google/gapid
cd $GOPATH/src/github.com/google/gapid
git submodule update --init
```
The `go get` and `git submodule` commands will fetch the source of this project and all third party repositories, so it may take a while to complete.

### Configure build
In a terminal type:
```
cd $GOPATH/src/github.com/google/gapid
./do config
```
And follow the instructions to configure the build.

### Building
In a terminal type:
```
cd $GOPATH/src/github.com/google/gapid
./do build
```
The build output will be in the directory you specified with `do config`.
