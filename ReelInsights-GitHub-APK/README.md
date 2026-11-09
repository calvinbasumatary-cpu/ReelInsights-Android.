# Reel Insights – Android APK (GitHub Actions)

This repository packages the supplied `www/index.html` into an Android app using Capacitor and builds a debug APK on GitHub Actions.

## What is included
- `www/index.html` – your original editable Reel Insights HTML file
- `package.json` – Capacitor dependencies
- `capacitor.config.json` – Android app ID and web asset folder
- `.github/workflows/build-apk.yml` – automatic APK build workflow

## Build your APK using GitHub (no Android Studio required)

1. Sign in to https://github.com/.
2. Click **New repository**.
3. Name it `ReelInsights-Android`.
4. Choose **Public** or **Private**, then click **Create repository**.
5. Upload the contents of this project ZIP to the repository root. Make sure `.github/workflows/build-apk.yml` is included. If uploading through the browser, GitHub may hide `.github`; create the `.github/workflows` folders in the repository using **Add file → Create new file** and create `build-apk.yml`, then paste the workflow contents from this ZIP.
6. Commit the files to the `main` branch.
7. Open the repository's **Actions** tab.
8. Select **Build Reel Insights APK**. If it has not started automatically, click **Run workflow → Run workflow**.
9. Wait for the workflow to finish successfully (green check mark).
10. Open the completed workflow run, scroll to **Artifacts**, and download `Reel-Insights-debug-APK`.
11. Extract the downloaded artifact ZIP. It contains `app-debug.apk`.
12. Transfer `app-debug.apk` to your Android phone and install it. You may need to allow installation from that file manager/browser.

## Updating the app later

Edit `www/index.html` in GitHub and commit the change. A new APK build starts automatically on pushes to `main`.

## Important notes
- This is a basic wrapper: the HTML layout and existing JavaScript are preserved.
- The app loads its HTML locally and does not need a website or internet connection for the simulator itself.
- The APK produced is a **debug APK**, suitable for testing and personal installation. A signed release APK is a separate step.
- The current HTML stores edits in the page DOM only; it does not implement persistent saving across app restarts.
- The existing HTML's image upload control is included. Test image selection on your device after installing.
- This is an independent simulator using clearly simulated insights, not an official Instagram app and not connected to Instagram accounts.
