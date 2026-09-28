# OBS Settings

Backup of my OBS Studio profiles and scene collections, exported for version control and easy restoration on a new machine.

## Structure

```
OBS-Settings/
├── Demo_Profile/
│   ├── basic.ini
│   ├── circ_mask.png
│   └── pngtree-modern-neon-circle-frame-design-png-image_6554572.png
├── Meeting_Profile/
│   └── basic.ini
├── Recording_Profile/
│   └── basic.ini
├── Demo_Scene.json
├── Meeting_Scene.json
├── Recording_Scene.json
└── .gitignore
```

- **`*_Profile/basic.ini`** — OBS profile settings (output, video, audio) exported from `%AppData%\obs-studio\basic\profiles\<Profile Name>\`.
- **`*_Scene.json`** — Scene collections exported from `%AppData%\obs-studio\basic\scenes\`.

## Profiles

| Profile | Output Resolution | Base Canvas | Recording Encoder | Recording Quality |
|---|---|---|---|---|
| Demo Profile | 1920x1080 | 1920x1080 | AMD (hardware) | Small |
| Meeting Profile | 3840x1080 | 3840x1080 | none (uses Advanced/AAC) | Small |
| Recording Profile | 1920x1080 | 1920x1080 | x264 (software) | Stream |

Common settings across all profiles:
- Simple output mode, 60 fps (common) target, 30 fps output
- Recording format: `hybrid_mp4`
- Video bitrate: 6000 kbps, Audio bitrate: 160 kbps
- Audio: AAC, 48 kHz, Stereo
- Recording path: `C:\Users\elmorc\Videos`
- Filename format: `%CCYY-%MM-%DD %hh-%mm-%ss`

## Scene Collections

### Demo Scene
Single scene (`Demo Scene`) with:
- Display Capture (with a "No Taskbar" variant)
- Video Capture Device (webcam)
- Audio Input/Output Capture
- `Neon` image overlay (paired with the circle-frame PNG assets in `Demo_Profile/`)

### Meeting Scene
Single scene (`Meeting Scene`) at a 3840x1080 canvas, combining multiple monitors into one wide layout:
- Monitor 1L + 2R
- Monitor 2L + 3R
- Monitor 2R + 1L
- Monitor 3R + 2L
- Audio Input/Output Capture

### Recording Scene
Single scene (`Recording Scene`) at 1920x1080, with individual monitor sources (each with a "No Taskbar" variant):
- Monitor 1, Monitor 2, Monitor 3
- Audio Input/Output Capture

## Restoring

1. Copy each `*_Profile` folder into `%AppData%\obs-studio\basic\profiles\`.
2. Copy each `*_Scene.json` file into `%AppData%\obs-studio\basic\scenes\`.
3. Launch OBS Studio and select the desired profile and scene collection from the **Profile** / **Scene Collection** menus.

> **Note:** Scene collections reference source names/devices by ID — capture devices (webcams, monitors) must match the same hardware/setup for sources to reconnect automatically.
