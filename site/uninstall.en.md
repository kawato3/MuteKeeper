---
title: "Uninstall — MuteKeeper"
description: "How to completely uninstall MuteKeeper from macOS and Windows."
---

# Uninstall

This page explains how to remove MuteKeeper from your system.

---

## Windows

### Uninstall via Apps & Features (Recommended)

1. Open **Settings** > **Apps** > **Installed apps** (on Windows 10: "Apps & features")
2. Find **MuteKeeper** in the list
3. Click **Uninstall** and follow the on-screen instructions

This will automatically remove all files that were installed by the installer.

### Manual Removal

Delete the following folders using File Explorer. Administrator privileges are required.

```
C:\Program Files\Common Files\VST3\MuteKeeper.vst3
C:\Program Files\Common Files\CLAP\MuteKeeper.clap
```

---

## macOS

No uninstaller is provided for macOS. Please delete the files manually.

### 1. Remove Plugin Files

Delete the files corresponding to the formats you installed.

#### VST3

```bash
sudo rm -rf "/Library/Audio/Plug-Ins/VST3/MuteKeeper.vst3"
```

#### AUv3 (Standalone App)

The AUv3 plugin is embedded inside the Standalone app. Removing the app also removes the AUv3 plugin.

```bash
sudo rm -rf "/Applications/MuteKeeper.app"
```

#### AAX

If you installed the AAX version, remove it as well:

```bash
sudo rm -rf "/Library/Application Support/Avid/Audio/Plug-Ins/MuteKeeper.aaxplugin"
```

#### CLAP

If you installed the CLAP version, remove it as well:

```bash
sudo rm -rf "/Library/Audio/Plug-Ins/CLAP/MuteKeeper.clap"
```

!!! tip "Using Finder instead of Terminal"
    You can also delete these files using Finder. From the menu bar, choose **Go** > **Go to Folder…**, enter the path above, and move the folder to the Trash. An administrator password is required for operations in the `/Library` folder.

### 2. Reset the AudioUnit Cache

macOS caches information about AudioUnit plugins. After deleting the plugin files, MuteKeeper may still appear in your DAW's plugin list if the cache has not been updated.

Normally, restarting your DAW after deleting the plugin files will refresh the cache automatically. If MuteKeeper still appears, reset the cache manually:

```bash
# Delete the AudioUnit cache
rm -rf ~/Library/Caches/AudioUnitCache/

# Restart AudioComponentRegistrar (it will relaunch automatically)
killall -9 AudioComponentRegistrar
```

After resetting, restart your DAW to trigger a full plugin rescan.

!!! note "AUv3 deregistration"
    AUv3 plugins are managed by macOS PluginKit. Deleting the Standalone app (`/Applications/MuteKeeper.app`) will automatically deregister the AUv3 extension. If the change is not reflected immediately, log out or restart your Mac.

### 3. Remove Preferences (Optional)

MuteKeeper stores its preferences in the following location. You may delete these for a complete removal, but leaving them causes no harm.

```bash
rm -f ~/Library/Preferences/to.kawa.MuteKeeper.plist
```

---

## DAW-Specific Settings

Some DAWs may retain MuteKeeper entries in their plugin blocklists, favorites, or other settings. These are managed by the DAW itself — use your DAW's plugin manager to remove them.
