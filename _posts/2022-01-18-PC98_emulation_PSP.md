---
layout: post
title: "(attempted) PC-98 emulation on PSP"
author: "Pierre L"
categories: emulators
tags: [PSP,homebrew]
image: /assets/img/random/dokyusei-2-pc-98.gif
---

**Update**: I found a [Japanese guide](https://kuronousagi.info/retrogamer/2019/02/08/psp-3000-yu-no/) that does an adequate work of explaining how to get the emulator up and running. 

You think [DOSBox for PSP](https://archive.org/details/dosbox-psp.-7z) is user-unfriendly? How about trying something like DOSBox, but in Japanese?

[NP2](https://archive.org/details/np-2-for-psp-v-0.39.7z) is the PSP port of Neko Project II, the most widely used PC-98 emulator.

The best-known PC-98 titles are visual novels, few of which ever got an English translation. Dead of the Brain is one of a handful of exceptions, making it a good starting point for my test.

### It does not fit

Dead of the Brain comes in four files - floppy disk images with an `.hdm` extension. Loading the games was surprisingly intuitive. Unlike DOSBox PSP, NP2 has a GUI - in English, even. 

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/np2_gui.webp)

It is enough to point the emulator to the first two of the four files, and select Reset from the Emulate menu.

Soon after loading the game though, I hit a brick wall. The PC-98 had a screen resolution of 640×400 pixels. To fit the image into a PSP screen (480x272), the emulator has to nearly halve the resolution.

None of this would much matter if we were playing a Doom or Mario. But these are visual novels. If downscaling makes the text unreadable, there is no point in playing them.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/np2_dotb_text.webp)

Some scaling options are available, but none make much of a difference when it comes to text readability. There is an option to display the screen at full resolution and pan around with the analog stick. 

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/np2_zoom.webp)

But that makes for a less than ideal experience.

### Puyo to the rescue?

I decided that it might make more sense to test an arcade-style game instead - like Puyo Puyo.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/puyo_title.webp)

Surely, playing Puyo Puyo doesn't require reading any text on screen? It doesn't, but the screen is still causing trouble.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/np2_puyo_2.webp)

Resolution seems to have nothing to do with it this time. I tried changing a number of settings - to no avail. 

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/np2_puyo_3.webp)

This is the second PC-98 game in a row that I couldn't even begin to play.

### Third try

Having been let down by Puyo Puyo, I was feeling less than optimistic about the potential for PC-98 emulation on PSP.

As next test subject, one of the Touhou games seemed appropriate, since the series is one of the things the PC-98 is known for. The Touhou game came as a hard drive image, not a floppy. 

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/touhou_load.webp)

After loading it through the appropriate menu, it played a short introductory animation and... crashed to command prompt.

### 4th try

I lowered my expectations - again. Arkanoid. If it doesn't boot Arkanoid, there's no point in trying with anything else.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/np2_arkanoid.webp)

Well - the scaling looks as dreadful as ever, and the game runs way too fast, even at the lowest CPU settings. But it works. 

### Burning Dragon

After managing to boot Arkanoid, I tried to raise the bar just a little. Burning Dragon is a shmup that is just a step above Arkanoid in terms of complexity. NP2 should be able to handle it.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/np2_dragon.webp)

Or not. I get that the error message is saying something about 2.5 MHz, but the CPU is set to 8 - that should be enough to cover it. Either way, it does not play.

### NP2 RIP 

That's the end of my portable PC-98 experience - for now. In short, I would only recommend it to Japanese speakers, or masochists. 

Or Japanese-speaking masochists.

### RetroArch Finale

Oh yeah. RetroArch PSP actually has a PC-98 core. And - wouldn't you know it - it doesn't even boot. 

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/np2_retroarch.webp)

Throw BIOS files at it all you want, it doesn't care.
