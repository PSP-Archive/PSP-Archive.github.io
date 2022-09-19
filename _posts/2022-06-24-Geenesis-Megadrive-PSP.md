---
layout: post
title: "Emulating Genesis / Megadrive games on PSP"
author: "Pierre L"
categories: emulators
tags: [PSP,homebrew]
image: /assets/img/random/genesis-emus.webp
---

The rediscovery of the PSP port of the Mednafen emulator is as good an excuse as any to revisit all the options for emulating Megadrive games on the go.

Picodrive is the most famous of the bunch, but even that one alone offers several builds and forks to choose from. On top of that, there are many other emulators that preceded Picodrive and might be worth trying out as well - if not for their present quality, for their historical value. 

I tried to have a quick look at all the Megadrive emulator ever made for PSP, from the early test releases in 2005 down to the most recent RetroArch core updates.

## Based on DGEN/SDL

### DGEN by Syn-k

[DGEN](https://archive.org/details/dgen-170-lite.-7z) was the first really usable Megadrive emulator for PSP, having its original public release in June 2005. 

Based on DGen/SDL, the PSP port was created by the Japanese coder [Syn-k](https://web.archive.org/web/20081205145355/http://syn-k.sakura.ne.jp/dgen_psp/index.html). The most recent version is 1.70 from August 2006, but the release of the source code made it possible for other developers to add their own improvements, such as support for later PSP models.

DGEN is also one of a handful of PSP emulators that offer support for ad-hoc multiplayer, though I could not test this particular feature.

### DGEN Lite by takka 

The original DGEN emulator no longer boots on modern firmware, so I had to test [DGEN Lite](https://archive.org/details/dgen-170-lite) by Takka (the guy behind the unofficial gpSP builds). By Takka's own account, his changes amounted to nothing more than a quick and dirty patch to add support for later PSP models and firmwares. 

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20220624140301.webp) 

This build manages to run at around 40 FPS with vsync and zero frame skip. Overall, DGEN was the best bet for Megadrive emulation on PSP before PicoDrive appeared on the scene.

### DGEN RX by Nekomune

[DGEN RX](https://archive.org/details/dgen-170-rx.-7z) is the work of another Japanese coder, [Nekomune](http://nekoyama2gillien.blog36.fc2.com/blog-entry-667.html?sp). Going by the readme, this update simply adds support for later PSP models and signs the EBOOT, so that it can work even without a custom firmware.

Puzzingly, I couldn't get this one to work on my PSP either. This is especially confusing because the build is really recent by PSP standards, dating back to 2012. The signing process was known to create incompatibilities with pre-existing code, so perhaps that plays a role.

## Based on Generator

### Generator PSP by Hotoke (仏様氏), PSP Wiki

[Generator PSP](https://archive.org/details/genpsp0_01_11.7z) is a very early Megadrive emulator created by "仏様氏" (Hotoke, according to Google Translate) at a time when the homebrew devs were still trying to gauge how much performance they could squeeze out of a PSP.

A port of James Ponder's Generator, this emulator had its only two releases in June 2005. There's no file selector, so changing a ROM is only possible by renaming the file to `gen.bin` each time. 

This is another emulator that doesn't seem to work on modern firmware, even with the LEDA plugin or eLoader.

### PSPGenesis by Sougen

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20220624111133.webp) 

[PSPGenesis](https://archive.org/details/pspgenesis.-7z) is another port of Generator by James Ponder, and is clearly way more polished than the other one. 

On top of that, it is one of a selected few PSP emulators that can boast a GUI created by Satoshi Arakawa. A [Chinese translation](https://archive.org/details/genesis-0.18c.-7z) also exists.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20220624111311.webp) 

This is another Megadrive emulator that was released early and discontinued early. The most recent version out there is from July 2005.

Among the early Megadrive emulators this is one of the better options, offering sound support, save states and vsync. Even then, a generous amount of frame skip is required to play even the simpler games.


## Based on Genesis Plus

### Mednafen PSP by Robert Szkutak

As mentioned above, it was the rediscovery of this emulator that occasioned this post. 

Mednafen is a well known multi-system emulator, but the existence of a [PSP port](https://archive.org/details/mednafenPSP) was only attested by a couple of websites - neither of which had a downloadable build. Now that I finally managed to recompile it from source, how does it work?

The user interface is - well, let's say very minimalistic. The only graphical element we see once the emulator starts is a directory listing of the Mednafen folder. 

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20220624111921.webp) 

Trying to reach any deeper level of the memory stick results in a hard freeze. Not a great start.

The emulation itself is... slower than the earliest Megadrive emulators for PSP. Is there something inherent to multi-system emulators that makes them less optimized than standalone options? 

The scaling doesn't look too great either - the resolution can be altered by editing a `.cfg` file in a text editor, but even when other emulators blow up the image to the full 16:9 screen it never looks this pixellated.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20220624121429.webp) 

Launching the usual Sonic game results in a crash within seconds. Time to move on. 

### Megadrive for PSP by Osakana

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20220624112219.webp) 

The developer of Megadrive for PSP is unusual in one way: emulator developers hardly ever work on homebrew games, and the reverse is also true. Our Osakana, on the other hand, also created the first of countless Touhou Project fan games for PSP - [TP03](https://archive.org/details/tp-03.7z).

The unimaginatively named [Megadrive for PSP](https://archive.org/details/mdp-02.7z) is another early PSP work that turned out to be a dead end. The same coder invested much of his time and energy on emulating the PC Engine with his [PCE for PSP](https://archive.org/details/pcep-083-d-6.7z), so that could be one reason why this one was abandoned.

So how is the emulator itself? First of all, it only seems to accept zipped ROMs - either that, or it requires some peculiar file extension. Aside from that, the on-screen statistics inform me that it runs at less than 10 frames per second, with a frame skip that flickers between three and four. Not quite sonic speed, is it?

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20220624112332.webp) 

Megadrive for PSP might be based on Genesis Plus by Charles MacDonald - I say *might* because the machine translation of the Japanese readme is not really clear on this point.

## PSPadrive by HamsterBert

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20220624115736.webp) 

[PSPadrive](https://archive.org/details/pspadrive.7z) is a port of Genesis Plus by Charles MacDonald. It was released by HamsterBert to compete in the 2006 [NeoFlash coding contest](https://www.neoflash.com/compo2006_3/compo-06-03.htm), where it was ranked 9th out of 15 entries.

From what I could tell, [the author](https://web.archive.org/web/20070617013513/http://hbert.dcemu.co.uk/) never released the source code of his port, which is a shame (and probably a GPL violation).

After launching the emulator, there are a number of things that are immediately noticeable. The screen is not centered, there is no sound and no settings to choose from. The only options after choosing a ROM are playing the game or exiting.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20220624115856.webp) 

I'll exit. Gameplay speed is really slow, without even a frame skip to help it limp along.

## Based on PicoDrive

### PicoDrive by Notaz

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20220624112914.webp) 

Easy to forget now, but this emulator by [Notaz](https://notaz.gp2x.de/pico_old.php) made its appearance relatively late in the PSP's lifespan. The first PSP version of this widely praised emulator only appeared in November 2007.

Unlike most everything on this list, [Picodrive](https://archive.org/details/pico-drive-psp-151b.-7z) isn't a port of a PC emulator. The original Picodrive code base targeted a Symbian candy bar phone, and it was ported to PSP by the original author - which no doubt simplified the optimization process.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20220624113502.webp) 

What's there to say about this one? PicoDrive is great, as millions of PSP owners already know. It was translated into [Chinese](https://archive.org/details/pico-drive-cn-bin.-7z) and [Russian](https://archive.org/details/pico-drive-rus.-7z) and it was forked by at least four other coders.

Development of the original PSP port ended in 2008, with version 1.51b. This last version works pretty great - full framerate with vsync and no frame skip. No wonder it became so popular.

### Pico-drive by ＰＳＰ開発幼稚園

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20220624113843.webp) 

I love the folks from PSP Development Kindergarten. Though their emulators aren't necessarily the best, they left behind some extensive write-ups on their emulation work with code, comments and the occasional humor that even Google Translate could not erase. Best of all, one of their (several) websites is [still online](https://ameblo.jp/pspdevblog/entry-10011395768.html).

By their own telling, in their quest for the perfect 'Megadora' emulation on PSP they tested several emulators, and picked the best as the basis for their work. In short, their [Pico-drive](https://archive.org/details/picodrivea14.7z) is a fork of an early version of PicoDrive for PSP.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20220624114101.webp) 

Without the automatic frame skip (enabled by default) this emulator runs at about half speed. No idea if this was much better or much worse than contemporary PicoDrive builds, but the glitchy menu that flickers on and off after pausing a game couldn't have been an improvement.

### PicoDrive by Robson Alcantara

This [version of PicoDrive](https://archive.org/details/picodrive-1.92.3.7z) has spread widely in recent years, almost displacing the original release in the process. The reason for that is probably down to the version number - 1.92 is greater than 1.51, so this version has to be at least +0.41 better, right?

This version backports some features that are absent in the last PSP release, but the trade-off is that overall performance takes a hit. Games run quite a bit slower, especially with vsync turned on. Nothing some light frame skip won't fix, but still an annoyance. 

The main advantage compared to the vanilla build is 32X support, but these games play too slow to be anything more than a one-off curiosity anyway.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20220624135726.webp) 

Downclocking the 32X CPUs is pretty much mandatory to go beyond the Sega logo without having to wait hours, but lower values too much and crashes become inevitable. 

### PicoDrive by irixxxx

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20220624112654.webp) 

This is the most recently compiled version of PicoDrive - [version 1.99](https://github.com/irixxxx/picodrive/releases) from November 2021. The coder who built it does not have a PSP, so it is probably thoroughly untested. Unlike version 1.92 from Robson Alcantara, this one doesn't seem to be well known in the PSP community yet.

One additional feature is the ability to play Master System and Game Gear games - though both systems have enough PSP emulators so that this change isn't really a selling point. 

The emulation itself is slow, and this time the fall in performance is quite drastic - only 20 FPS with vsync and no frameskip.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20220624131035.webp) 

Pressing the wrong button in the settings menu will crash the emulator instantly. Sometimes this happens by pressing X, sometimes circle - there seems to be no logic to this bug.

### Unofficial Picodrive R by davex 

Davex added rewind mods to many PSP emulators - hence his [Unofficial Picodrive R](https://archive.org/details/uoPicodrive135bR_by_davex-psp_slim.7z). This build is based on an obsolete version of PicoDrive, and comes in two different builds that support both fat and slim PSP models.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20220624120235.webp) 

This one is just as advertised. Pressing the R button rewinds gameplay, up to a few seconds. It runs a bit choppier than the latest official PicoDrive, but nothing too dramatic.

### RetroArch

The PSP port of RetroArch has a PicoDrive core - which is actually pretty decent for a change. It never quite reaches full speed without frame skip, but that's acceptable considering that most RetroArch PSP cores just don't boot at all. 

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20220624123355.webp) 

There is an annoying ghosting effect that is immediately noticeable. There is an option to filter it out, but it doesn't seem to do anything. 

This is the status as of RetroArch 1.10.3. Earlier builds had some annoying bugs, which may or may not resurface as the RetroArch code base is constantly changing. 

Once again, it's good to keep in mind that more recent builds of an emulator aren't necessarily any better. The PicoDrive core on RetroArch notionally supports 32X games, but version 1.10.3 runs out of memory before it even gets into the game - with a PSP 1000 at least. 

Version 1.7.0 can actually run 32X games on a fat PSP - not fast enough to be remotely playable, but they will run. 

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20220624151519.webp) 

Especially for RetroArch on PSP, it makes sense to check out the [changelog](https://github.com/libretro/RetroArch/blob/master/CHANGES.md) before updating. PSP-specific updates are (sadly) exceedingly sparse, and other changes to the code base might break PSP cores without offering anything new in the bargain.
