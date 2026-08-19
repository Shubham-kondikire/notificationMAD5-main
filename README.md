# Experiment 5: Displaying Notifications in Android

## Student Details

**Name:** Shubham Shivaji Kondikire  
**USN:** 25MCAR0102  
**Experiment No.:** 5

---

## Aim

To develop an Android application for displaying notifications in Android.

---

## Objective

The objective of this experiment is to understand how notifications work in Android, how to create a Notification Channel, and how to display notifications to the user using `NotificationCompat`.

---

## Concept / Technology Used

### Notifications

Notifications are messages displayed outside the app's UI to alert users about events, updates, or information.

From **Android 8.0 (API 26)** onward, notifications must be posted through a **Notification Channel**.

From **Android 13 (API 33)** onward, apps must request the runtime permission `POST_NOTIFICATIONS` before displaying notifications.

`NotificationCompat.Builder` is used to construct the notification (icon, title, text), and `NotificationManagerCompat` is used to display it.

Example:

```kotlin
val builder = NotificationCompat.Builder(this, CHANNEL_ID)
    .setSmallIcon(R.drawable.ic_notification)
    .setContentTitle("Hello!")
    .setContentText("This is a sample notification")
    .setPriority(NotificationCompat.PRIORITY_DEFAULT)

NotificationManagerCompat.from(this).notify(NOTIFICATION_ID, builder.build())
```

---

## Scenario

The application has a single button, **"Show Notification"**.

On click, the app checks/requests the `POST_NOTIFICATIONS` permission (for Android 13+), then builds and displays a notification with a title and message in the system notification tray.

### Application Flow

```text
MainActivity
     |
     | Click "Show Notification"
     ↓
Check/Request POST_NOTIFICATIONS permission
     |
     ↓
Build Notification (NotificationCompat.Builder)
     |
     ↓
Display Notification (NotificationManagerCompat)
     |
     ↓
Notification visible in Status Bar / Tray
```

---

## Software Requirements

- Android Studio
- Kotlin
- Android SDK
- Gradle
- Android Emulator or Physical Android Device (Android 13+ recommended)

---

## Technologies Used

- Kotlin
- Notification Channel
- NotificationCompat
- NotificationManagerCompat
- Runtime Permissions (POST_NOTIFICATIONS)
- XML Layouts
- Android Manifest

---

## Project Folder and File Structure

```text
NotificationDemo/
│
├── app/
│   │
│   ├── src/
│   │   │
│   │   └── main/
│   │       │
│   │       ├── java/
│   │       │   └── com/example/notificationdemomad5/
│   │       │       └── MainActivity.kt
│   │       │
│   │       ├── res/
│   │       │   ├── drawable/
│   │       │   ├── layout/
│   │       │   │   └── activity_main.xml
│   │       │   ├── mipmap/
│   │       │   └── values/
│   │       │
│   │       └── AndroidManifest.xml
│   │
│   └── build.gradle.kts
│
├── gradle/
│   └── wrapper/
│
├── build.gradle.kts
├── gradle.properties
├── settings.gradle.kts
├── gradlew
├── gradlew.bat
└── README.md
```

---

## Important Files and Their Purpose

### MainActivity.kt

Creates the Notification Channel, handles the runtime permission request, and builds and sends the notification when the button is clicked.

### activity_main.xml

Defines the UI containing the "Show Notification" button.

### AndroidManifest.xml

Declares the `POST_NOTIFICATIONS` permission required for Android 13 and above.

### build.gradle.kts

Contains the Android application build configuration and required dependencies.

---

## Working / Implementation

### 1. Create Notification Channel

A Notification Channel is created in `MainActivity` (required for Android 8.0+) to categorize the notification.

### 2. Request Permission

On Android 13+, the app checks and requests the `POST_NOTIFICATIONS` runtime permission before sending a notification.

### 3. Build and Show Notification

When the button is clicked, `NotificationCompat.Builder` constructs the notification with an icon, title, and message, and `NotificationManagerCompat` displays it in the system tray.

```text
Click Button
     ↓
Check Permission
     ↓
Build Notification
     ↓
Show in Notification Tray
```

---

# Test Cases

## Test Case 1: Permission Request

### Test Objective

To verify that the app requests the notification permission on Android 13+ devices.

### Test Steps

1. Open the app on an Android 13+ device.
2. Click the **"Show Notification"** button.

### Expected Result

The system permission dialog should appear, asking the user to allow notifications.

### Actual Result

The system permission dialog appeared as expected.

### Status

**PASS ✅**

---

## Test Case 2: Notification Displayed

### Test Objective

To verify that the notification is displayed after permission is granted.

### Test Steps

1. Allow the notification permission.
2. Click the **"Show Notification"** button again if needed.
3. Swipe down the status bar.

### Expected Result

A notification with the title "Hello!" and a message should be visible in the notification tray.

### Actual Result

The notification appeared successfully with the expected title and message.

### Status

**PASS ✅**

---

## Test Case 3: Verify Student Name and USN

### Test Objective

To verify the student's name and USN.

### Test Data

**Name:** Shubham Shivaji Kondikire  
**USN:** 25MCAR0102

### Test Steps

1. Open the app screen/notification content.
2. Verify the student's name is displayed.
3. Verify the USN is displayed.

### Expected Result

The correct student name and USN should be displayed on screen/notification, confirming authorship.

### Actual Result

The student's name and USN were verified successfully.

### Status

**PASS ✅**

---

# Output

The application successfully demonstrates creating a Notification Channel, requesting runtime permission, and displaying a notification.

### Output Screenshot

<img width="1080" height="2358" alt="screenshot5 png" src="https://github.com/user-attachments/assets/3b4aac2f-7a31-4c7a-8781-22f854598b2b" />
<img width="720" height="1600" alt="mad exp 5 (1)" src="https://github.com/user-attachments/assets/9fe4d8cb-929d-4e33-9f14-f9925b87813c" />
<img width="720" height="1600" alt="mad exp 5 (2)" src="https://github.com/user-attachments/assets/1ee3a5fc-1cdd-4af1-a26d-90fcab9400fe" />



---

# Steps to Run the Project

1. Open the project in Android Studio.
2. Allow Gradle synchronization to complete.
3. Connect an Android device (Android 13+ recommended) or start an Android Emulator.
4. Select the application from the Run Configuration.
5. Click the **Run ▶** button.
6. Click **"Show Notification"** and allow the permission when prompted.
7. Swipe down the status bar to view the notification.

---

# Requirements

## Hardware Requirements

- Laptop/Desktop
- Android Device or Android Emulator
- USB Cable if using a physical Android device

## Software Requirements

- Android Studio
- Kotlin
- Android SDK
- Gradle

---

# Learning Outcomes

After completing this experiment, the following concepts were understood:

- Android Notifications
- Notification Channels
- `NotificationCompat.Builder`
- `NotificationManagerCompat`
- Runtime permissions (`POST_NOTIFICATIONS`)
- Android 13 permission handling
- AndroidManifest.xml permission declaration
- XML Layouts

---

# Result

The Android application was successfully developed and executed to demonstrate displaying notifications, including permission handling for Android 13+.

---

# Conclusion

The experiment successfully demonstrated how to create a Notification Channel, request the runtime `POST_NOTIFICATIONS` permission, and display a notification using `NotificationCompat` and `NotificationManagerCompat`.

Thus, the objective of implementing an Android application to display notifications was successfully achieved.

---

# Student Information

**Name:** Shubham Shivaji Kondikire  
**USN:** 25MCAR0102

---

# GitHub Repository

**Repository Name:** NotificationDemo

**GitHub Link:**  
https://github.com/Shubham-kondikire/NotificationDemo

---

# Reference

- Android Developers – Notifications Overview
- Android Developers – Notification Permission
- Android Developers – NotificationCompat

---

## Author

**Shubham Shivaji Kondikire**  
**USN:** 25MCAR0102
