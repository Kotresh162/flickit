# Flutter Real-Time Object Detection App

This is a Flutter app that uses **Google ML Kit** for real-time object detection, implemented natively for Android via **Platform Channels**. The app detects objects using the camera and plays an alarm sound when any object is detected. You can start and stop the detection with a simple UI.

---

## 📱 Features

- Real-time object detection using Google ML Kit (native Android)
- Flutter UI with Start/Cancel control
- Centered camera preview
- Alarm sound when an object is detected
- Clean permission handling
- Communication between Flutter and native code using `MethodChannel`

---

## 🚀 Getting Started
![welcomescreen.jpeg](..%2F..%2F..%2FDownloads%2Fwelcomescreen.jpeg)
![camerascreen.jpeg](..%2F..%2F..%2FDownloads%2Fcamerascreen.jpeg)
### Prerequisites

- Flutter (3.x+ recommended)
- Android Studio / VS Code
- Android device or emulator with camera support
- Android SDK 21+

---

### 📦 Dependencies

**pubspec.yaml**


dependencies:
  flutter:
    sdk: flutter
  permission_handler: ^11.0.1

### 📦 Structure
lib/
  └── main.dart
android/
  └── MainActivity.kt
  └── (ML Kit object detection logic)
📷 Permissions
Ensure the following permissions are in AndroidManifest.xml:

xml
Copy
Edit
<uses-permission android:name="android.permission.CAMERA"/>

Platform Channel Setup
Channel name: object_detector

Supported methods:

startObjectDetection

stopObjectDetection

## Object Detection Logic
* Uses CameraX for camera feed.

* Uses ML Kit Object Detection API.

* Plays a sound using ToneGenerator when an object is detected.

* Welcome Screen → Shows Start button.

* Start Button Pressed → Requests permission, launches native detection.

* Detection Started → Camera preview appears with “Cancel” button.

* Object Detected → A short alarm tone plays.

* Cancel Pressed → Stops camera and goes back to welcome screen.
