# DevMateKit code signing issue after version 1.6

Adding DevMateKit to any project after version 1.6 results in a broken build, because `com.devmate.UpdateInstaller.xpc` isn't signed (correctly).

This example project uses CocoaPods to add DevMateKit, but the problem occurs when adding it manually as well.

## Setup

1. Clone the project.
1. Run `pod install`.
1. Archive (or build) the project.
1. Check code signing on the binary, or simulate a download from a web server.

## Result

The binary does not pass code signing validation.

![RB Checker Lite](https://raw.github.com/boyvanamstel/DevMateKit-Code-Signing-Issue/master/screenshots/rbcheckerlite.jpg)
![RB Checker Lite Detail](https://raw.github.com/boyvanamstel/DevMateKit-Code-Signing-Issue/master/screenshots/rbcheckerlite-detail.jpg)

After downloading the binary, OS X will refuse to run it.

![After download](https://raw.github.com/boyvanamstel/DevMateKit-Code-Signing-Issue/master/screenshots/download.png)

## Cause

The issue appeared when `com.devmate.UpdateInstaller.xpc` was moved into DevMateKit.

## Solution

Not quite sure.
