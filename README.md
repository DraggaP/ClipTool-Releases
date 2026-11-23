# ClipTool

ClipTool is a background replay recorder. It keeps the last few minutes of your screen and audio in memory. A hotkey saves them as an MP4 clip, which you can trim, upload or copy a link to.

Written in Rust. The interface uses egui, and capture and encoding use FFmpeg.

## Platforms

| Platform | Install |
|---|---|
| Windows 10/11 (beta) | Download `DraggaP.ClipTool-win-Setup.exe` from Releases. Updates install automatically. |
| Linux, X11 | Build from source (below) |
| Linux, Wayland | Build from source (below). Uses the ScreenCast portal and PipeWire. |

Hardware encoding: NVENC and AMF on Windows, VAAPI and Quick Sync on Linux. CPU x264, x265 and SVT-AV1 are the fallback.

## Features

- Replay buffer with a global hotkey. On Wayland, use the GlobalShortcuts portal or bind `ClipTool --save` to a key.
- Editor for trimming and cropping. Enter saves a copy. Ctrl+Enter also uploads it.
- System audio and microphone.
- Optional input overlay.
- Game detection, so clips go into per-game folders.
- Upload to catbox.moe, with the link copied to your clipboard.

## Install on Windows

1. Download the Setup file from the latest release and run it.
2. Earlier 1.0.x installs update to 2.0 automatically. Settings and clips carry over.

## Build on Linux

```
./install-linux.sh
```

This installs to `~/.local/share/cliptool`. You need `ffmpeg` at runtime, plus `pkg-config clang libpipewire-0.3-dev` to build.

## Files

- Settings: `%APPDATA%\ClipTool\config.json` on Windows, `~/.config/cliptool/config.json` on Linux
- Clips: `~/Videos/Clips/<Game>/`

Source code is maintained separately and is not published in this repository.
