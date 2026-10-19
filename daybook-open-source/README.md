# Daybook Offline

Open-source, offline-first personal finance app. No login, backend, analytics or cloud sync. Data lives in the Android app's local WebView storage (localStorage). Includes JSON export and restore. Source uses MIT license.

## Build APK without Android Studio
1. Upload all files (including hidden `.github/workflows/android.yml`) to a GitHub repository. Keep `.github` at repository root.
2. Open GitHub repository > Actions > Build Android APK > Run workflow.
3. Wait for green checkmark, open the workflow run and download artifact `daybook-debug-apk`.
4. Unzip artifact and transfer `app-debug.apk` to your Android phone; allow install from that source if prompted.

The workflow builds a debug-signed APK for personal testing. To distribute publicly, create a securely signed release build and preserve your signing key.

## Privacy and backup
- App assets are bundled in the APK; there is no server URL in the Capacitor config.
- Records and goal are stored on the phone in the app's private WebView localStorage. No financial data is sent to the repository or GitHub Actions; only source code is uploaded.
- Export backup downloads JSON; store it safely. Import replaces all current data.
- Uninstalling or clearing app storage may erase records. The existing hosted website's storage does not automatically migrate.
- Building downloads dependencies from npm/Gradle on GitHub's runner; using the installed app does not require an internet connection.
