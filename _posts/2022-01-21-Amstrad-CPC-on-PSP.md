---
layout: post
title: "The CPC on PSP"
author: "Pierre L"
categories: emulators
tags: [PSP,homebrew]
image: /assets/img/random/CPC.webp
---

Time to try another home computer on the PSP - the Amstrad CPC. We have three native emulators to choose from here, though they are all ultimately ports of Caprice 32.

And emulation aside, two of the better CPC games have homebrew ports on PSP: [BombJack](https://archive.org/details/jack.7z) and [Rick Dangerous](https://archive.org/details/psprick.-7z).

### Caprice32

[Caprice32](https://archive.org/details/cpc-300750-00000) is another Karapetyan emulator that has been kept up to date in recent years by DelayedQuasar.

The UI takes care of the ROM loading process, but we still have to resort to the on-screen keyboard to start the game in most cases.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/cap32_osk.webp)

Having to hold down the R trigger to type on the virtual keyboard is somewhat annoying, but hardly a dealbreaker.

Most games require 266 MHz to run at full speed. 

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/cap32_bruce.webp)

There are only two scaling options to choose from - original resolution, and stretched to the full 16:9 ratio.

### CPCPSP 

[CPCPSP](https://archive.org/details/cpcpsp-v-01.7z) is the only PSP work of coder Nige. This was the first CPC emulator for PSP, having been released on time for Christmas 2005.

That was also when it was last updated - and it shows. 

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/cpcpsp.webp)

There's no GUI to load games from. Instead, we have to create snapshot files from the PC version of the emulator, and supply them to CPCPSP.

According to the author himself, the emulation won't reach full speed even with the PSP clocked at 300 MHz.

In short, I see no reason to bother with this one, now that better options are available.

### PSPCAP32

Ludovic Jacomme's port of Caprice is known as [PSPCAP32](https://archive.org/details/pspcap32.7z). 

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/fruity_pspcap.webp)

Just like Karapetyan's port, this is also a cookie-cutter creation, reusing the same UI featured in all of Jacomme's PSP works. But it works here, so no complaints about that. 

PSPCAP32 addresses most of the concerns I had with Caprice32. 

We have a good number of scaling options to choose from - fit height, fit width, x1.5 and so on. The virtual keyboard is also less of a pain to use.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/pspcap_ikar.webp)

The games I tested run at full speed already at 222 MHz.

### RetroArch

CrocoDS is a core available on the PSP version of RetroArch. 

This emulator is supposed to have an on-screen keyboard, but I couldn't get it to work.

Pressing Select shows a menu, but none of the buttons I pressed seemed to do anything here.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/crocods_menu.webp)

And that frame-rate counter already doesn't look so good.
