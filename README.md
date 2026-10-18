# Lunaro Client — Minecraft Java Edition for Android

A rebranded build of [ZalithLauncher2](https://github.com/ZalithLauncher/ZalithLauncher2)
(GPL-3.0) with its own name, moon icon and dark purple theme.
Lunaro Client is an independent project. It is not affiliated with Lunar Client, Mojang or Microsoft.

## Get the APK (works from a phone browser)
1. Create a free GitHub account and a new empty repository (e.g. `lunaro-client`).
2. Add these 6 text files with the same paths (on GitHub: Add file → Create new file; typing `/` in the name makes folders):
   `.github/workflows/build-lunaro-apk.yml`, `patch/apply_lunaro.py`, `patch/make_icons.py`,
   `patch/kotlin/GroupEdit.kt`, `patch/kotlin/GroupEditBar.kt`, `patch/kotlin/SmartSetup.kt`.
   (On a PC you can simply drag the whole folder in.)
3. Open the **Actions** tab → **Build Lunaro Client APK** → **Run workflow** (leave `arm64`).
4. After ~10-25 minutes open the finished run and download the **Lunaro-Client-apk-arm64** artifact (a zip containing the APK).
5. Unzip, install the APK (allow "install unknown apps"). It installs next to Zalith Launcher (different package id).

## CurseForge ("you don't have permission")
CurseForge only works with an API key. Get a free one at https://console.curseforge.com (API keys),
then in your GitHub repo: Settings -> Secrets and variables -> Actions -> New repository secret,
name `CURSEFORGE_API_KEY`, value = your key. Run the workflow again and install the new APK.
(Microsoft login additionally needs your own `OAUTH_CLIENT_ID` secret from an Azure app registration; offline accounts work without it.)

## New features
- **Controls editor, multi-select:** select a control, then double-tap the **Multi-select** button quickly.
  A banner says "Multi-select mode ON". Tap controls to add or remove them, then use the bottom bar to move,
  resize, align, space out or delete them together. Press **Done** to leave.
- **Smart Setup (rocket button, top bar):** reads your phone's RAM, chip and cores, guesses Low / Mid / High,
  and suggests renderer, render distance, shader and mods. It is a rule-based estimate that runs on the phone, not an online AI.
- **Downloads:** Zalith already downloads with 64 parallel connections, so the only change is a larger read buffer (small gain).
  Speed is mostly limited by your connection; pick a mirror in Settings if downloads are slow.

## What the patch changes
- App name -> Lunaro Client, new package id suffix `.lunaro`
- New moon icon (original artwork)
- Default theme: dark + Lunaro purple palette (no wallpaper colours); you can still change themes in Settings
- Faster-feeling UI by default: page animations and festival effects off (re-enable in Settings)
- Nothing else: all launcher/game code is upstream ZalithLauncher2 at a pinned commit (see workflow)

## License
GPL-3.0, same as upstream. If you share the built APK, also share this repository (it is the source of the changes) and keep the upstream credits.
