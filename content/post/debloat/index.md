---
title: Android debloat
description: Debloating android phone
slug: debloat
date: 2024-07-07
image:
categories:
    - Tech
tags:
    - android
weight: 1       # You can add weight to some posts to override the default sorting (date descending)
---

I recently came across Universal Android Debloater repo on GitHub.
Android debloating refers to the process of removing or disabling unnecessary pre-installed applications (often called bloatware) that come with Android devices. These pre-installed apps are usually added by the device manufacturer and can consume system resources such as storage, memory, and battery. Essentially, this application aims to improve the overall performance and user experience by getting rid of these unwanted apps.

Installation
I installed the app using Homebrew:
```shell
brew install android-platform-tools
```
Next, I connected my Android phone to my Mac using a USB-C cable. You can launch the application to access a GUI, and the usage is quite self-explanatory. However, if you want to delve deeper, there are many ADB commands available (use the adb help command). You can search and find a command for almost every use case.

## Here are some commands
```bash
### Adb Server
adb kill-server
adb start-server 

### Adb Reboot
adb reboot
adb reboot recovery 
adb reboot-bootloader
adb root //restarts adb with root permissions
### Shell
adb shell    // Open or run commands in a terminal on the host Android device.

### Devices
adb usb
adb devices   //show devices attached
adb devices -l //devices (product/model)
adb connect ip_address_of_device

### Get device android version
adb shell getprop ro.build.version.release 

### Files
adb push [source] [destination]    // Copy files from your computer to your phone.
adb pull [device file location] [local file location] // Copy files from your phone to your computer.

### Uninstalling app from device
adb uninstall com.myAppPackage
adb uninstall <app .apk name>

### Emulate device

adb shell wm size 2048x1536
adb shell wm density 288
// And reset to default
adb shell wm size reset
adb shell wm density reset
```

## images
![Packages list](a.png)
![Apps selection](b.png)
![App details](c.png)


## conclusion
The application provides a description of each app, explaining why you might want to delete it. I’ve removed almost all the recommended apps to reduce bloatware. It’s important to avoid deleting the apps listed under the "unsafe" and "expert" categories unless you know exactly what you’re doing.

Have fun with the application, and enjoy a cleaner, more efficient Android experience!