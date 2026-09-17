# WallRaven

A Wallhaven-backed wallpaper manager for Windows. It fetches wallpapers from
[Wallhaven](https://wallhaven.cc), changes them on a schedule you set, and gets
out of your way.

**[Download the latest release](../../releases/latest)**

This repository holds the installers. The source lives elsewhere.

## Verifying your download

Every release includes `SHA256SUMS.txt`. Check the installer against it before
running it:

```
certutil -hashfile Wallraven-Setup-v1.1.0.exe SHA256
```

The value it prints should match the one in `SHA256SUMS.txt`. If it does not,
do not run the file.

## About the SmartScreen warning

The installer is not code-signed yet, so Windows will show "Windows protected
your PC". Choose **More info**, then **Run anyway**. Signing is being worked on;
until then the checksum above is how you confirm you have the real file.

## What it does

- Fetches wallpapers from Wallhaven using your own search, filters and tags
- Changes them on a timer, or on a timetable that varies through the day
- Playlists, likes and dislikes, and presets you can share with other people
- Per-monitor wallpapers, and optional lock screen matching
- Pauses while you are playing a game or using apps you choose
- Optional account, to sync settings and playlists between machines

## Reporting a problem

Open an issue here. If the app has recorded a crash, Settings will offer to
attach the details; it strips your username, folder paths and API key first.
