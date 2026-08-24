# Peleza Stream Android — GitHub Build Ready

This project wraps **https://pelezastream.top/** as the Peleza Stream Android app.

## What is already configured

- Android WebView app for Peleza Stream
- JavaScript and WordPress login/cookie sessions
- HTML5 video and full-screen playback
- File upload chooser for website upload fields
- Android Downloads integration
- Back-button navigation
- External app links such as `mailto:`, `tel:` and `intent:`
- GitHub Actions cloud build
- Automatic installable APK artifact on every push to `main` or `master`
- Manual **Run workflow** option in GitHub Actions

## Upload to GitHub

1. Create a new empty GitHub repository.
2. Extract this ZIP on your phone/computer.
3. Upload **all files and folders inside this project folder** to the repository root. Make sure `.github/workflows/build-android.yml` is included.
4. Commit the files to `main`.
5. Open the repository's **Actions** tab.
6. The workflow **Build Peleza Stream Android APK** starts automatically after the push.
7. When the run turns green, open it and download the **Peleza-Stream-APK** artifact.
8. Extract the downloaded artifact ZIP. Inside is `Peleza-Stream-v1.0.0.apk`.

No Android Studio or local Android SDK is required for the GitHub build.

## Change the website URL

Edit:

`app/src/main/res/values/strings.xml`

Change the value of `site_url`, then commit. GitHub rebuilds the APK automatically.

## Change app version

Edit `app/build.gradle`:

- `versionCode` — increase this integer for every Play Store release.
- `versionName` — visible app version, for example `1.0.1`.

For the Play Store, a signed release AAB should use your permanent upload keystore. The current workflow deliberately builds an installable debug APK without requiring any GitHub secrets.
