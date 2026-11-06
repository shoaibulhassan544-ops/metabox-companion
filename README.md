# MetaBox Companion

Android companion app for the MetaBox desktop tool (test builds).

- Pair the app with the PC test app (Settings > Mobile Companion) over
  Wi-Fi or Tailscale, then monitor the Dashboard, Queue, Jobs, Library,
  Pages, KartBrowser, Analytics, Accounts, Settings, Activity and
  Muse Connected from the phone.
- The app checks `version.json` (this repo, raw URL) for updates and
  downloads + installs new versions in-app. No Play Store needed.

## Install

1. Uninstall any older companion build first (v2.2 and older used a
   fresh debug key each build; v2.3+ uses one stable key, so future
   updates install over the old app).
2. Download the APK from the latest Release and install it.
3. On Android 8+, allow "Install unknown apps" for this app once.

## Files

- `version.json` — latest version (versionCode, versionName, apkUrl,
  changelog). The app reads this file to check for updates.
- Releases — APK assets (`MetaBox-Companion-vX.Y.apk`).- APKs live in `releases/` in this repo (e.g. `releases/MetaBox-Companion-v2.3.apk`) — the app downloads them from the raw URL in `version.json`.
- GitHub Releases are also created per version (notes only; the asset upload host rejects this account's API credential, so the APK file itself lives in `releases/`).

## Signing

The stable release keystore lives only in the builder's workspace
(`android-companion/keystore/`) and is NEVER committed or uploaded.
Losing it breaks in-app updates forever.
