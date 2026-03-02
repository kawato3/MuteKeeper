---
title: "MuteKeeper — Automatic Transport-Aware Volume Control for DAWs"
description: "Free, open-source VST3 plugin that automatically controls volume based on DAW transport state. Perfect for talkback mics, reverb switching, and stage monitoring."
---

<div class="hero" markdown>

![MuteKeeper](assets/images/logo.png){ .hero-logo }

**Automatic volume control that responds to your DAW's transport state**

[Download (macOS) :material-apple:](https://github.com/kawato3/MuteKeeper/releases/download/v1.0.0/MuteKeeper-1.0.0-macOS.dmg){ .md-button .md-button--primary }

</div>

:material-translate: English | **[日本語](../)**

---

## What is MuteKeeper? { #about }

MuteKeeper is a **free, open-source** VST3 plugin that automatically controls audio signal levels based on your DAW's transport state — **Stopped**, **Playing**, or **Recording**.

Whether you're running PA for a live show, managing monitor mixes in the studio, or automating talkback mic control, MuteKeeper handles the "change the volume when the DAW state changes" workflow automatically.

Unlike simple mute switches, MuteKeeper offers **gradual volume control at any dB level** and **configurable fade times** for smooth, natural transitions.

## Features { #features }

<div class="grid" markdown>

:material-volume-high: **Per-State Volume Control**
:   Set independent volume levels for Stopped, Playing, and Recording. From Mute to +10 dB.

:material-swap-horizontal: **Smooth Fades**
:   Configurable fade time from 0 to 5000 ms with a perceptual curve for natural-sounding transitions.

:material-record-rec: **Recording Mode**
:   Link recording volume to playback, or set an independent recording level.

:material-palette: **Dark Theme UI**
:   Low-brightness dark theme designed for stage-side use. 100% / 150% / 200% scale presets.

:material-auto-fix: **Full DAW Automation**
:   Every parameter supports DAW automation for complete control.

:material-shield-check: **Transparent Audio**
:   Bit-perfect pass-through at 0 dB. Zero impact on audio quality.

</div>

## Use Cases { #use-cases }

### :material-microphone: Talkback Mic Control

Insert MuteKeeper on your talkback mic channel.

- **Stopped**: 0 dB (mic ON)
- **Playing**: Mute (mic OFF)

The talkback mic is automatically muted during playback and restored when the DAW stops. Set a fade time to avoid abrupt switching noise.

### :material-waveform: Reverb / FX Switching

Place MuteKeeper on your reverb send channel.

- **Playing**: 0 dB (reverb ON)
- **Stopped**: -20 dB (reduced reverb), or Mute

Full reverb during performance, automatically reduced or off during talk segments.

### :material-record: Recording Monitor Optimization

Set an independent recording volume to create different monitor balances for playback and recording. Toggle between linked and independent recording volume with one click.

### :material-speaker: Stage Monitoring

For manipulators and monitor engineers, transport-aware automatic volume control significantly reduces operational burden. The dark theme UI is perfect for use in dimly lit stage wings.

## Download { #download }

### macOS

[Download MuteKeeper v1.0.0 :material-download:](https://github.com/kawato3/MuteKeeper/releases/download/v1.0.0/MuteKeeper-1.0.0-macOS.dmg){ .md-button .md-button--primary }

Open the DMG and run the installer.
The VST3 plugin will be installed to `/Library/Audio/Plug-Ins/VST3/`.

### Windows

Windows support is planned. (TBD)

## Specifications { #specs }

| Item | Detail |
|------|--------|
| Plugin Format | VST3 |
| Supported OS | macOS (Intel / Apple Silicon) |
| Supported DAWs | Any VST3-compatible DAW |
| Volume Range | Mute to +10 dB |
| Fade Time | 0 to 5000 ms (perceptual curve) |
| Anti-Click Ramp | 5 ms (for same-state volume changes) |
| Latency | 0 samples |
| License | MIT (free and open source) |
| Framework | JUCE 8 / C++17 |

## For Muteomatic Users { #comparison }

MuteKeeper was inspired by **[Muteomatic](https://www.soundradix.com/products/mute-o-matic/)** (Mute-o-Matic), the free plugin by [Sound Radix](https://www.soundradix.com/).

Muteomatic is an excellent plugin for transport-aware mute control, trusted by engineers for years. **If simple mute ON/OFF control is all you need, Muteomatic remains a great choice.**

MuteKeeper builds on Muteomatic's concept with the utmost respect, adding these capabilities for a wider range of use cases:

| | Muteomatic | MuteKeeper |
|---|:---:|:---:|
| Mute control | :material-check: | :material-check: |
| Gradual volume control (Mute to +10 dB) | — | :material-check: |
| Configurable fade time (0–5000 ms) | — | :material-check: |
| Independent recording volume | — | :material-check: |
| Resizable UI | — | :material-check: |
| Open source (MIT) | — | :material-check: |

If mute is enough, try [Muteomatic](https://www.soundradix.com/products/mute-o-matic/). If you want finer control, give MuteKeeper a try.

## Support { #support }

Bug reports and feature requests are welcome on [GitHub Issues](https://github.com/kawato3/MuteKeeper/issues).

---

<div class="bmc-section" markdown>

MuteKeeper is free to use. If you enjoy it, consider buying me a coffee :coffee:

[:material-coffee: Buy Me a Coffee](https://buymeacoffee.com/kawato3){ .md-button }

</div>

## License { #license }

MuteKeeper is released under the [MIT License](https://github.com/kawato3/MuteKeeper/blob/main/LICENSE). Free for personal and commercial use.
