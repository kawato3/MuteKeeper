---
title: "MuteKeeper — Automatic Transport-Aware Volume Control for DAWs"
description: "Free VST3/AUv3 plugin that automatically controls volume based on DAW transport state. Perfect for talkback mics, reverb switching, and stage monitoring."
---

<div class="hero" markdown>

![MuteKeeper](assets/images/logo.png){ .hero-logo }

**Automatic volume control that responds to your DAW's transport state**

[Download (macOS) :material-apple:](https://github.com/kawato3/MuteKeeper/releases/download/v1.0.0/MuteKeeper-1.0.0-macOS.dmg){ .md-button .md-button--primary }
[Download (Windows) :material-microsoft-windows:](https://github.com/kawato3/MuteKeeper/releases/download/v1.0.1/MuteKeeper-1.0.1-Windows.exe){ .md-button .md-button--primary }

</div>

:material-translate: English | **[日本語](../)**

---

## What is MuteKeeper? { #about }

MuteKeeper is a **free** VST3 / AUv3 plugin that automatically controls audio signal levels based on your DAW's transport state — **Stopped**, **Playing**, or **Recording**.

Whether you're running PA for a live show, automating talkback mic control or managing monitor mixes in the studio, MuteKeeper handles the "change the mute status when the DAW state changes" workflow automatically. Transport-aware automatic volume control significantly reduces operational burden.

Unlike simple mute switches, MuteKeeper offers **gradual volume control at any dB level** and **configurable fade times** for smooth, natural transitions.

![MuteKeeper](assets/images/manual/talkback-basic.png){ .screenshot }

## Features { #features }

<div class="grid" markdown>

:material-volume-high: **Per-State Volume Control**
:   Set independent volume levels for Stopped, Playing, and Recording. From Mute to +10 dB.

:material-shield-check: **Transparent Audio**
:   Bit-perfect pass-through at 0 dB. Zero impact on audio quality.

:material-swap-horizontal: **Smooth Fades**
:   Configurable fade time from 0 to 5000 ms with a perceptual curve for natural-sounding transitions.

:material-record-rec: **Recording Mode**
:   Link recording volume to playback, or set an independent recording level.

:material-palette: **Dark Theme UI**
:   Low-brightness dark theme designed for stage-side use. 100% / 150% / 200% scale presets.

:material-surround-sound: **Multi-Channel Support**
:   Works with mono, stereo, surround (5.1 / 7.1), and any other multi-channel configuration.

:material-auto-fix: **Full DAW Automation**
:   Every parameter supports DAW automation for complete control.

</div>

## Use Cases { #use-cases }

### :material-microphone: Talkback Mic Control

Insert MuteKeeper on your talkback mic channel.

- **Stopped**: 0 dB (mic ON)
- **Playing / Recording**: Mute (mic OFF)

The talkback mic is automatically muted during playback and restored when the DAW stops.
If needed, you can mute talkback only during recording, then keep it active during playback to listen while conversing.

### :material-waves: Reverb / FX Switching

Place MuteKeeper on your reverb send channel, immediately before the reverb.

- **Playing / Recording**: 0 dB (reverb ON)
- **Stopped**: -20 dB (reduced reverb), or Mute

Full reverb during performance, automatically reduced or off during talk segments.

### :material-metronome-tick: Turning the click track

Keep the click track active during recording, then mute it when listening back. There are many patterns you can apply.

## Download { #download }

### macOS

[Download MuteKeeper v1.0.0 :material-download:](https://github.com/kawato3/MuteKeeper/releases/download/v1.0.0/MuteKeeper-1.0.0-macOS.dmg){ .md-button .md-button--primary }

Open the DMG and run the installer.
The VST3 plugin will be installed to `/Library/Audio/Plug-Ins/VST3/`, and the AUv3 plugin to `/Applications/MuteKeeper.app`.

### Windows

[Download MuteKeeper v1.0.1 :material-download:](https://github.com/kawato3/MuteKeeper/releases/download/v1.0.1/MuteKeeper-1.0.1-Windows.exe){ .md-button .md-button--primary }

Run the installer.
The VST3 plugin will be installed to `C:\Program Files\Common Files\VST3\`.

## Specifications { #specs }

| Item | Detail |
|------|--------|
| Plugin Format | VST3, AUv3 (macOS) |
| Supported OS | macOS (Intel / Apple Silicon), Windows 10/11 (64-bit) |
| Channel Layouts | Mono / Stereo / Surround (any channel count) |
| Volume Range | Mute to +10 dB |
| Fade Time | 0 to 5000 ms (perceptual curve) |
| Latency | 0 samples |
| License | MIT (free and open source) |

## For Muteomatic Users { #comparison }

MuteKeeper is inspired by **[Muteomatic](https://www.soundradix.com/products/mute-o-matic/)** (Mute-o-Matic), the free plugin by [Sound Radix](https://www.soundradix.com/).

Muteomatic is an excellent plugin for transport-aware mute control, trusted by engineers for years. **If simple mute ON/OFF control is all you need, Muteomatic remains a great choice.** We absolutely love Muteomatic.

MuteKeeper builds on Muteomatic's concept with the utmost respect, adding these capabilities for a wider range of use cases:

| | Muteomatic | MuteKeeper |
|---|:---:|:---:|
| Gradual volume control (Mute to +10 dB) | — | :material-check: |
| Configurable fade time (0–5000 ms) | — | :material-check: |
| Independent recording volume | — | :material-check: |
| Resizable UI | — | :material-check: |

If mute is enough, try [Muteomatic](https://www.soundradix.com/products/mute-o-matic/). If you want finer control, give MuteKeeper a try.

## Support { #support }

Bug reports and feature requests are welcome on [GitHub Issues](https://github.com/kawato3/MuteKeeper/issues).

## FAQ { #faq }

**Q: Does this plugin degrade audio quality or add latency?**

Nope. All it does is adjust the volume — no degradation, no extra CPU load, no added latency. And when set to 0 dB, the signal passes through completely untouched — bit-perfect. You're in good hands.

**Q: Isn't this just a Muteomatic ripoff?**

We love Muteomatic too! Even now that we've built MuteKeeper, there will still be times when we reach for Muteomatic's intuitive simplicity. But nobody wants Muteomatic itself to become more complex — and we don't think they should have to. We built MuteKeeper to fill the gap, deliberately stepping beyond simplicity where it makes sense.

**Q: I want an instant mute when playback starts or stops.**

Set the fade time to 0 ms and the switch will happen as fast as possible. Just keep in mind that cutting the signal abruptly can produce a small click, so we recommend setting it to around 5 ms if you can.

**Q: My DAW on Mac doesn't support AUv3. Will you offer a traditional AU plugin?**

If your DAW supports VST3, go with that. The AUv3 version is mainly intended for Logic Pro and GarageBand. We've decided not to offer AU v2 (legacy AU) due to technical limitations on our end.

**Q: I love this plugin. When can I buy you a coffee?**

Thanks for thinking of us! If your live event goes well, or you wrap up a great recording session, and you feel like saying "hey, grab yourself a coffee too" — that'd make our day. No obligation at all, of course.

---

<div class="bmc-section" markdown>

MuteKeeper is free to use. If you enjoy it, consider buying me a coffee :coffee:

[:material-coffee: Buy Me a Coffee](https://buymeacoffee.com/kawato3){ .md-button }

</div>

## License { #license }

MuteKeeper is released under the [MIT License](https://github.com/kawato3/MuteKeeper/blob/main/LICENSE). Free for personal and commercial use.
