# WallRaven

A Windows wallpaper manager for [Wallhaven](https://wallhaven.cc/). It sits in the
tray, changes your wallpaper on a timer, and gives you the same filters the site
does: resolution, aspect ratio, categories, purity, colours and tags.

Not affiliated with Wallhaven. It uses their public API.

**[Download the latest release](https://github.com/wallraven-app/wallraven/releases/latest)**
 · **[wallraven.app](https://wallraven.app)**

## What it does

- Rotates wallpapers from a Wallhaven search, one of your collections, a saved
  playlist, or folders on your PC. Dropbox, Google Drive and OneDrive folders
  work like any other folder.
- Runs on a simple timer, or on a timetable if you want different sources at
  different times of day.
- Likes and dislikes. Liked wallpapers are kept forever, disliked ones never
  come back.
- Per-monitor wallpapers, fit modes, lock screen mirroring and global keyboard
  shortcuts.
- Pauses while a fullscreen game is running, or while apps you choose are open.
- An optional account that syncs your settings, presets and playlists between
  machines, plus a gallery of presets other people have shared.

Everything works without an account. A Wallhaven API key is optional too, and is
only needed for your own collections and for NSFW content.

## Installing

Download the installer from the
[releases page](https://github.com/wallraven-app/wallraven/releases/latest) and
run it. It installs per user, so it needs no administrator rights.

### The SmartScreen warning

The installer is not code-signed yet, so Windows will show "Windows protected
your PC". Choose **More info**, then **Run anyway**. Signing is being worked on.
Until then, the checksum below is how you confirm you have the real file.

### Verifying your download

Every release publishes a `SHA256SUMS.txt` beside the installer. Check what you
downloaded against it before running it:

```
certutil -hashfile Wallraven-Setup-v1.2.1.exe SHA256
```

The value it prints should match the one in `SHA256SUMS.txt`. If it does not, do
not run the file.

### Updates

The app updates itself. It checks on launch, downloads only from a fixed list of
hosts, verifies the file against the published checksum, and will not install
anything that does not match.

## Reporting a problem

Open an issue here. If the app has recorded a crash, Settings will offer to
attach the details. It strips your username, folder paths and API key first.

## Repository layout

| Path | What it is |
| --- | --- |
| `electron/` | the tray app, which is the product |
| `src/` | the website: sign-in, device pairing, the shared preset gallery |
| `supabase/migrations/` | the database schema and its row-level security |
| `scripts/` | the build: packaging, the installer, the Store package |
| `.github/workflows/` | CI: tests, typecheck, installer build, release publishing |

## Building it yourself

```
npm install
npm test                                       # 15 test files, a few seconds
node scripts/build-desktop.mjs --platform win32 --arch x64
```

The installer step needs NSIS. Without it the build still produces the unpacked
app in `electron/app`.

To run the app straight from source while working on it, use `npm run app`, or
double-click `Run WallRaven.bat`.

## Licence and credit

Wallpapers belong to the people who made them. WallRaven displays them through
Wallhaven's public API and claims no ownership or endorsement. Please follow,
favourite and credit artists on Wallhaven.
