---
layout: post
title: "SNES emulators on PSP and their history"
author: "Pierre L"
categories: emulators
tags: [PSP,homebrew]
image: /assets/img/random/TYL_splash.webp
---

Explaining the history of SNES emulation on PSP is no easy task, but giving a recommendation on the best one is very simple: use the most recent.

If you just want to play the games, grab a copy from [esmjanus's repo](https://github.com/esmjanus/snes9xTYL/releases) and never look back. If you're interested in the scene-history lesson though, feel free to stay.

### Family tree

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/random/snes9x_PSP_famtree.webp)

### The proof of concept

The history of SNES emulation on PSP, like many other PSP scene stories, begins in May 2005. 

After nem's [Hello World](https://archive.org/details/hellopsp_R1.7z) and Mirakichi's [Game Boy emulator](https://archive.org/details/gbemu.7z), everyone's expectations were unbridled, awaiting a new system to be emulated every day.

For the most part, they were not disappointed. Emulators for all sorts of systems were being released on the Japanese [PSPwiki](https://web.archive.org/web/20050517083941/http://psp.holybell.to:80/) almost daily, and the SNES was no exception.

Barely two weeks after Hello World, Bifuteki released the [first working port](https://archive.org/details/snes-9-x.-7z) of Snes9x to PSP.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/bifuteki.webp)

Snes9x was then one of the two major SNES emulators at the time, along with ZSNES. 

And while ZSNES was coded in x86 assembly, the C codebase of Snes9x made it far more amenable to porting.

For the first time, a mass-market portable device could run Super Nintendo games. 

The achievement was meaningful enough to warrant a mention in the October 2005 issue of Popular Science.

[![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/random/PopSci_Oct05_trim.webp)](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/random/PopSci_Oct05.webp)

They weren't running well, though. Even the simplest games required a generous amount of frameskip to be playable. 

After two updates, Bifuteki abandoned the PSP scene, never to return. He was around for just a month altogether - enough to leave his mark in scene history.

There was no shortage of coders willing to take his place - [Andon](https://archive.org/details/uo_Snes9x-0.02pd2-20050728.7z), [Yoshihiro](https://archive.org/details/snes-9-x-yoshihiro-optimized.-7z) and the NesterJ developer [Ruka](https://archive.org/details/y33Ruka0034.7z) all released bug fixes and improvements for the fledgling emulator. 

But Snes9x for PSP needed more than patches. It needed a healthy speed boost if it was to become really usable.

### TYL

The PSP scene didn't have to wait long for such an improvement. 

August 2005 saw the release of [snes9xTYL](https://archive.org/details/s9xTYL-0.4.2me.7z), the work of ThunderZ, [YoyoFR](http://yoyofr92.free.fr/psp/snespsp.html) and Laxer3a. 

Although ThunderZ's name was removed in later versions, for whatever reason.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/tyl_042_mario.webp)

Rather than building on Bifuteki's port, they had the idea of porting a PalmOS version of Snes9x 1.39 to PSP. 

More importantly, their code made use of the PSP's GU for hardware acceleration. 

For the most part, the homebrew development community embraced the TYL version and never looked back. 

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/tyl_042.webp)

By February 2006 the emulator was already using the Media Engine for sound emulation, and even saw the addition of a (shamefully underused) netplay feature.

The original TYL team abandoned PSP development by May 2006, having turned mobile SNES emulation from a concept into an everyday reality. 

### Modern TYL builds

While a coder known as 'y' continued to work on Bifuteki's port, and [Ruka](https://web.archive.org/web/20070220052141/http://rukapsp.hp.infoseek.co.jp/) went back and forth between TYL and the original port, most homebrew developers focused exclusively on improving TYL.

Their efforts have certainly had an impact. Over the years, more and more SNES games have become playable. 

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/esmjanus_dkc3.webp)

Developers such as Ruka, the puzzlingly named 33(76)氏, 173210 and esmjanus all managed to improve performance and accuracy, in part by implementing game-specific speed hacks and importing code from more recent versions of Snes9x.

The latest TYL build, known as [s9xTYLme Mod](https://archive.org/details/s9xTYLme_mod.7z), provides decent performance even with the harder to emulate titles.

You can get some playtime even from the SuperFX titles, such as StarFox 2.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/esmjanus_sf2.webp)

### Euphoria detour

A coder known as Zack decided to build on Ruka's TYL code (apparently eschewing 33(76)氏's additions) by releasing the [Euphoria fork](https://web.archive.org/web/20091023065110/http://www.retroemu.com/forum/index.php?/topic/13-release-snes9x-euphoria-r1-speed/
) in October 2009.

Euphoria ran considerably better than the last official release by ThunderZ, YoyoFR and Laxer3a. 

And it did not rely on the Media Engine, which later made it popular among Vita owners - until they finally had a good SNES emulator of their own.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/euphoria.webp)

But ultimately, the fork died out with the last official release by Zack, in 2011. The later work on the main TYL branch has eclipsed its - once considerable - speed advantages.

The Euphoria fork was one of the few emulators to enter a PSP coding contest, in August 2010. 

That created a rather awkward moment, when one of the jury members realized that he was called to [evaluate a project](https://www.neoflash.com/forum/index.php?topic=6346.0) that was in part his own work.

### Hissorii

2011 saw the launch of the third port of Snes9x to the PSP. 

The Japanese coder ひっそりぃ (hissorii) is best remembered for his work on emulators for Japanese home computers, such as the PC98 and X68000. 

In April 2011 though, he decided to attempt a direct port of version 1.52.81 of Snes9x to PSP. 

A laudable initiative, no doubt. But the result wasn't pretty. The [resulting emulator](https://archive.org/details/snes9x-1.52.81-psp.7z) runs considerably worse than Bifuteki's release from six years earlier. 

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/hissorii.webp)

And while Hissorii named the first version of his port WIP-1, the work never... progressed beyond that.

### Retroarch

The last chapter in the history of SNES emulation on PSP was written in 2015, when the Snes9x 2005 core had its PSP port.

There isn't much to say about this one. Unlike many other Retroarch PSP cores it actually works, I'll grant it that much.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/retroarch_snes9x.webp)

But it never ran as well as any of the standalone emulators. I see no reason to prefer it over any of the available TYL builds.
