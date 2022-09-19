---
layout: post
title: "Playing Famicom Disk System games on PSP"
author: "Pierre L"
categories: emulators
tags: [PSP,homebrew]
image: /assets/img/random/fds_on_psp.webp
---

Not a lot of people know about this, but it is possible to play Famicom Disk System games on a PSP. And it can be done with any old NesterJ version.

### NesterJ

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/fds_psp_f1.webp) 

The version or fork of NesterJ does not seem to matter. For the test, I've tried [NesterJ AoEX](https://archive.org/details/nintendo-nester-j-ao-ex-r-3.7z) and [NesterJ RX Mod](https://archive.org/details/nester-j-112-rx-mod-20160324.7z) - neither seems to work any better or worse when it comes to FDS support.

The main thing to remember is that you need a `DISKSYS.ROM` file (the FDS bios, 8 KB in size) at the root of the emulator's folder. Otherwise when you try to load a .fds ROM, this will happen:

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/fds_no_bios.webp) 

Once the DISKSYS.ROM is in place, simply choose the FDS game from the ROM selection menu.

A lot of FDS games required the user to change from side A to side B of the disk during loading. When the game prompts you to do so, just select `DISK CHANGE` from the settings menu, then `CHANGE 1ST DISK SIDE B`. The game will then resume loading.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/fds_nesterj_disk_change.webp) 

There is a number of games (especially English-patched or ROM hacks) that simply won't work on NesterJ though, no matter how you try to load them.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/fds_unsupported_nesterj.webp) 

In those cases, do *not* contact the dev, as by now it has probably been at least a decade since they've last seen a PSP. 

Instead, it can be a good idea to resort to the PSP version of RetroArch (yes, it has its uses).

Just make sure to have `DISKSYS.ROM` in the `ms0:\PSP\RETROARCH\SYSTEM` folder before trying to launch anything.

If you need to flip the disk during loading, press R to emulate ejection, then L to change sides, then R again.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/fds_retroarch_flip.webp) 

The most recent version of the FCEUmm core should be able to handle even the trickier games.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/fds_retroarch_ingame.webp) 
