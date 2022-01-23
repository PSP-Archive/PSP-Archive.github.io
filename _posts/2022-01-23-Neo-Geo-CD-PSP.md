---
layout: post
title: "Emulating the Neo Geo CD on PSP"
author: "Pierre L"
categories: emulators
tags: [PSP,homebrew]
image: /assets/img/random/neocd.webp
---

After trying out [Amstrad CPC](https://psp-archive.github.io/emulators/Amstrad-CPC-on-PSP.html) emulation, it's time for some arcade games. 

### NCDZPSP

[NCDZPSP](https://archive.org/details/uo_ncdzpsp_2.3.1_1.5_kernel_mod_r5.7z) is the Neo Geo CD emulator by [NJ](https://web.archive.org/web/20071011004934/http://nj-emu.hp.infoseek.co.jp/), the Japanese coder who created the CPS1, CPS2 and MVS emulators as well. In fact, all four emulators are different builds from the same code base. 

The last official release was in October 2007. After that, it was picked up by [173210](https://github.com/173210/mvspsp) (who also worked on snes9xTYL) and later [phoe-nix](https://github.com/phoe-nix/NJEMU) (TempGBA4PSP-mod), who kept it up to date until 2018.

NJ's emulators are known for their solid performance, and this one is no different. The frame rate is stable at 60 most of the time, though it does drop in the 50s when the screen gets busy in games like Metal Slug.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/metalslug_nj.webp)

This is with the default settings though - 22 kHz audio, no raster effects and no vsync.

Activating such enhancements will have a cost in terms of performance, especially with the more demanding games.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/neodrift_nj.webp)

The only boring part here is the setup process. The ISOs need a bit of treatment, by extracting the ISO image (7Zip will do), and moving the resulting folder to 'roms'.

More annoyingly, the audio tracks need to be converted to MP3. Most hosting sites seem to offer converted tracks already though, so this wasn't an issue for me.

Beyond the unofficial version mentioned above, other developers released their own builds.

Theelf created a [version](https://archive.org/details/ngcdz-theelf.7z) with custom scaling options. More interestingly, AhMan - creator of [IR Shell](https://archive.org/details/pspirshell52.7z) - released a [build](https://archive.org/details/ncdzpsp_2.2.1a_adhoc_for_3x) with support for adhoc multiplayer back in 2007.

### NeoCD/PSP

[NeoCD/PSP](https://archive.org/details/neocd.-7z) - the first Neo Geo CD emulator for PSP - came in really early in the homebrew scene history.

This is a port of NeoCD/SDL, created by an anonymous Japanese developer. Why is it always the Japanese devs who are anonymous?

This emulator is every bit as acerbic as you would expect of something released less than a month after the first Hello World on PSP. It doesn't have a menu, and only works with a zipped version of an ISO dump with a specific file name.

This version does not boot on modern firmware, so I could not assess its performance.

### NeoCDPSP

[NeoCDPSP](https://archive.org/details/neocd.7z) was created just a month after the first one, in July 2005. 

I expected it to be a glorified coding exercise like the previous emulator but nope, this is actually pretty good.

The quality is probably explained by its lineage. It was created by [YoyoFR](http://yoyofr92.free.fr/), the same developer who would later release SnesPSP TYL, the best SNES emulator on the system.

NeoCDPSP is based on [Neo4All](http://chui.dcemu.co.uk/neo4all.html), an emulator for Dreamcast made by Chui. And yep, it runs pretty well. Many games run at full speed. It only real drawback compared to NJ's later work is a more limited compatibility - some sudden freezes, that sort of thing.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/neocd_yoyofr.webp)

[ZeLurker](https://archive.org/details/neocdpsp-091.7z) picked up on yoyo's work and continued it until February 2006, fixing a number of bugs.

There are no major differences beyond that. This updated version performs about the same as the original.
