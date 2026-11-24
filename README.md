# Namaz Attendance Android App

This repository converts the existing `www/index.html` Namaz Attendance web app into an Android APK using Capacitor and GitHub Actions.

## Build an APK on GitHub

1. Create a GitHub repository named `Namaz-Attendance-App`.
2. Upload all files and folders from this project to the repository root.
3. Make sure the default branch is named `main`.
4. Open the repository's **Actions** tab.
5. Select **Build Namaz Attendance APK**.
6. Press **Run workflow** (or push a new commit to `main`).
7. When the workflow finishes, open the completed run and download the `Namaz-Attendance-APK` artifact.
8. Extract the downloaded ZIP file. It contains `app-debug.apk`.

## Build locally (optional)

Install Node.js and Android Studio, then run:

```bash
npm install
npx cap add android
npx cap sync android
cd android
./gradlew assembleDebug
```

The debug APK is created at:

`android/app/build/outputs/apk/debug/app-debug.apk`

## Important notes

- The app currently saves records in the device's local browser storage (`localStorage`). Data is local to each device; it does not automatically synchronize between phones.
- Keep the same `appId` (`com.qureshi.namazattendance`) for future updates to this app. Changing it creates a different Android app.
- This workflow creates a **debug APK** for testing and direct installation. A Play Store release requires a separately signed release build.
- Test attendance saving, CSV/JPG downloads, and printing on a real Android device. Browser printing may need a native Android print integration for consistent results.
