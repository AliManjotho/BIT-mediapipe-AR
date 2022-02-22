# BIT-MediaPipe-AR

## Installation on Windows

1.  Install MSYS2 

    https://www.msys2.org/

2.  Add C:\msys64\usr\bin to your %PATH% environment variable.

3.  Install necessary packages (Command Prompt).

    C:\> pacman -S git patch unzip

4.  Download and install Python (Check Add python to PATH).

    https://www.python.org/ftp/python/3.10.2/python-3.10.2-amd64.exe

5.  Download and install Visual C++ Build Tools 2019 (Also check to install Visual C++ desktop development & Windows 10 SDK).

    https://visualstudio.microsoft.com/visual-cpp-build-tools/

6.  Download and install Microsoft Visual C++ 2019 Redistributable.

    https://docs.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170

7.  Download the WinSDK and install it.

    https://developer.microsoft.com/en-us/windows/downloads/windows-sdk/

8.  Download and install Android Studio.

    https://developer.android.com/studio
    
9.  Install Bazel 4.2.1 or higher.
    
    https://github.com/bazelbuild/bazel/releases/download/5.0.0/bazel-5.0.0-windows-x86_64.zip
    
    Extract the file in C:\bazel
    
10.  Add bazel path to PATH environment variable.
    
11.  Download and install Visual C++ Redistributable for Visual Studio 2015.

     https://www.microsoft.com/en-us/download/details.aspx?id=48145  
     
12.  Check bazel installation in command prompt.

     C:\>bazel --version
     
13.  Set Bazel variables (Run in command prompt).

     C:\> set BAZEL_VS=C:\Program Files (x86)\Microsoft Visual Studio\2019\BuildTools

     
     C:\> set BAZEL_VC=C:\Program Files (x86)\Microsoft Visual Studio\2019\BuildTools\VC
     
     
     C:\> set BAZEL_VC_FULL_VERSION=14.31.31103.0

    
     C:\> set BAZEL_WINSDK_FULL_VERSION=10.0.19041.0
    
14.  Download and install OpenCV 3.4.10 at C:\opencv.
    
     https://opencv.org/releases/

15.  Set Android SDK and NDK paths in environment variables.

     ANDROID_HOME=C:\Users\Ali\AppData\Local\Android\Sdk
     ANDROID_NDK_HOME=C:\Users\Ali\AppData\Local\Android\Sdk\ndk

16.  Append WORKSPACE file in root directory with:

     android_sdk_repository(name="androidsdk")

     android_ndk_repository(name="androidndk")
	
	
17.  Build android apk (BIT-AR).

     bazel build -c opt --config=android_arm64 --action_env PYTHON_BIN_PATH="C://Users//Ali//AppData//Local//Programs//Python//Python310//python.exe" mediapipe/examples/android/src/java/com/google/mediapipe/apps/posetrackinggpu:posetrackinggpu
	 
	 
18.  Push Bit-AR.apk to device.

     adb install bazel-bin/mediapipe/examples/android/src/java/com/google/mediapipe/apps/posetrackinggpu/posetrackinggpu.apk

