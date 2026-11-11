# TeleCRM Calls – Android app
Open this folder in Android Studio (Hedgehog or newer) → *Build > Build APK(s)* → install on each telecaller's phone.

**One-time setup on the phone (in the app):** log in with the telecaller email/password, allow phone + call-log access, pick the folder where the
phone's own call recorder saves files, and turn off battery optimisation for the app. After that everything is automatic:
call ends → app reads the call log → finds the recording → uploads it → it appears in the admin panel.

Turn on call recording in the phone's Dialer settings first (Samsung: Phone > Settings > Record calls; Xiaomi/Realme/Pixel: Dialer > Settings > Call recording).
Typical folders: `Recordings/Call`, `MIUI/sound_recorder/call_rec`, `Music/Recordings/Call`. Android does not let third-party apps record calls themselves.
Server must be HTTPS. Only calls to numbers of enquiries assigned to that telecaller are uploaded; all other calls are ignored.

## Getting the APK (no Android Studio needed)
1. Create a free GitHub account → New repository (private) → upload the *contents* of this `android-app` folder (keep the `.github` folder).
2. Open the repo → **Actions** tab → "Build APK" → wait ~5 minutes (or click *Run workflow*).
3. Open the finished run → download **TeleCRM-Calls-apk** → unzip → `app-debug.apk`.
4. Send the APK to the telecaller's phone and install (allow "Install unknown apps").
Or with Android Studio: *Build > Build APK(s)*. Command line: `./gradlew assembleDebug`.
