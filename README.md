# PMA - Programování mobilních aplikací 

>Cílem předmětu je poskytnout studentům základní přehled o problematice vývoje mobilních aplikací napříč aktuálně používanými platformami (iOS, Android, Windows). Studenti se seznámí s architekturami nejpoužívanějších mobilních operačních systémů a s konkrétními technologiemi, které se při vývoji mobilních aplikací používají. Náplní seminářů je praktická aplikace - studenti samostatně navrhnou a vytvoří vlastní mobilní aplikaci pro zvolenou platformu.
## Table of Contents
- [PMA - Programování mobilních aplikací](#pma---programování-mobilních-aplikací)
  - [Table of Contents](#table-of-contents)
  - [Prerequisites](#prerequisites)
    - [1. MacOs development setup](#1-macos-development-setup)
    - [2. VsCode Setup](#2-vscode-setup)
    - [3. Install Checklist:](#3-install-checklist)


## Prerequisites
This guide covers the steps and commands required to set up Android development on macOS without the need of **Android Studio.**

### 1. MacOs development setup 
1. Download Commandline tools: [Tutorial](https://developer.android.com/tools/)
2. After downloading the Android SDK Command Line tools, unzip it and place it in the following path:
   - ``/Users/cyrils/Library/Android/sdk/cmdline-tools/latest/bin``
3. Add the cmdline tools to your PATH (.zshrc)
``` bash
  export PATH="$PATH:/Users/cyrils/Library/Android/sdk/cmdline-tools/latest/bin"
```
   - *Note:* now you can use sdkmanager command in your terminal
4. Install the required Android SDK components for development
   - [**READ**](https://developer.android.com/tools/sdkmanager) and [**UPDATE**](https://developer.android.com/tools/sdkmanager#devsite-terminal) THE command before running 
```bash
sdkmanager --install "cmdline-tools;latest" sdkmanager "platform-tools" "build-tools;34.0.0" "platforms;android-34" 
```
5. Add **ADB** and **Emulator** to your PATH (.zshrc)
- ``export PATH="$PATH:/Users/cyrils/Library/ 
  export PATH="$PATH:/Users/cyrils/ Library/Android/sdk/platform-tools" ``
- ``export PATH="$PATH:/Users/cyrils/Library/Android/sdk/emulator"
``
6. Create Virtual Device through [avdmanager](https://developer.android.com/tools/avdmanager)
   - [HELP](https://stackoverflow.com/questions/42792947/how-to-create-android-virtual-device-with-command-line-and-avdmanager)
   - Again you might need to update the system_image and platform..
   ```bash 
   avdmanager create avd -n Pixel8_Emulator -k "system-images;android-34;google_apis_playstore;arm64-v8a" -d pixel_8
   ```
- Finally start the emulator..
  - `` emulator -avd Pixel8_Emulator ``
- **Congrats!** You have Android Device without Android studio and other junk. 
### 2. VsCode Setup 
1. Use VSCode to setup Flutter SDK in your environment: [Docs](https://docs.flutter.dev/get-started/install/macos/mobile-ios)
2. Install DART extension [link](https://marketplace.visualstudio.com/items?itemName=Dart-Code.dart-code)
3. run ``flutter doctor`` to check all requirements
4. run flutter New project from Vscode Command Pallete
   - >flutter new project
### 3. Install Checklist:
- To create Android apps with Flutter, verify that the following Android components have been installed.

- [x] Android SDK Platform, API 35.0.1
- [x] Android SDK Command-line Tools
- [ ] Android SDK Build-Tools
- [x] Android SDK Platform-Tools
- [x] Android Emulator
