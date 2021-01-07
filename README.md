# AndroidNDK-CMake

### Prerequisites

- [Android SDK CommandLine Tools](https://developer.android.com/studio?hl=ja#cmdline-tools)

### Build

```
set ANDROID_SDK=PATH_TO\android-sdk
set PATH=%ANDROID_SDK%\tools\bin;%PATH%
```

```
sdkmanager ndk;22.0.7026061 --sdk_root=%ANDROID_SDK%
sdkmanager cmake;3.10.2.4988404 --sdk_root=%ANDROID_SDK%
```

```
set PATH=%ANDROID_SDK%\cmake\3.10.2.4988404\bin;%PATH%

cmake ^
  -H. ^
  -B./build ^
  -G"Ninja" ^
  -DANDROID_ABI=x86_64 ^
  -DANDROID_NDK=%ANDROID_SDK%\ndk\22.0.7026061 ^
  -DCMAKE_MAKE_PROGRAM=%ANDROID_SDK%\cmake\3.10.2.4988404\bin\ninja.exe ^
  -DCMAKE_TOOLCHAIN_FILE=%ANDROID_SDK%\ndk\22.0.7026061\build\cmake\android.toolchain.cmake ^
  -DANDROID_PLATFORM=android-26 ^
  -DANDROID_STL=c++_shared ^
  -DCMAKE_INSTALL_PREFIX=install

cmake --build ./build --target install
```

