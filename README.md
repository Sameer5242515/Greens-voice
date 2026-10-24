# Voice Duty Assistant (Android)

Android Studio/Gradle project for the Voice Duty Assistant, designed to be built from GitHub Actions when you only have an Android phone.

## Features in this project
- Pick a date using Android's calendar picker and set start/end times.
- Save a duty entry per date; entries are kept in the app's local storage.
- Ask by voice about dates such as “October 26”.
- Light/dark mode.
- Configure a wake phrase (default `hello duty`) and a custom voice code (default `blue seven`). Either phrase activates the assistant; say the date question after the greeting.
- Customize the spoken greeting.
- Optional foreground microphone service with a persistent notification while listening.

## Important limitations
- Android's normal speech-recognition service is not a dedicated hotword engine. It may pause, restart, make system sounds, need network access, or be stopped by battery management. Continuous Siri-style hotword detection is not guaranteed on every phone.
- On Android 14+, microphone foreground services have while-in-use permission restrictions. Start background listening from the open app after granting microphone permission. See Android's official documentation: https://developer.android.com/develop/background-work/services/fgs/restrictions-bg-start
- This starter app stores dated shifts locally; it does not yet create an automatic weekly recurring pattern.

## Build the APK from your phone using GitHub
1. Extract this ZIP using a file manager that supports ZIP archives.
2. Upload the project files/folders to a GitHub repository (keep the `.github/workflows/build-apk.yml` file and project folder structure).
3. In the repository, open **Actions** → **Build Android APK** → **Run workflow**.
4. When it finishes, open the workflow run, scroll to **Artifacts**, and download `VoiceDutyAssistant-debug-apk`.
5. Extract the artifact ZIP, tap `app-debug.apk`, and allow installation from that source if Android asks.
6. Open the app, allow microphone permission, save duty dates, then open the three-dot menu to set wake word/code and enable background listening.

If the repository already contains this project, replace the existing project files with the contents of this ZIP and commit the changes, or upload it to a new branch first.
