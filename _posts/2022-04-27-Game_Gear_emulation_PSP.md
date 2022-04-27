---
layout: post
title: "Game Gear emulators for PSP"
author: "Pierre L"
categories: emulators
tags: [PSP,homebrew]
image: /assets/img/random/gg_tv.webp
---

Emulating a handheld on another handheld seems like a good idea - cheaper than a screen mod for the original at any rate. Just like the case of the Game Boy though, the wider aspect ratio of the PSP's screen sort of gets in the way. Which emulator can negotiate this restriction best, and provide the best PSP experience for this Sega handheld from the 90s?

The Game Gear is basically a portable Master System, and many Master System emulators will run Game Gear ROMS without any issues. In this overview, we will look at both dedicated emulators, as well as compatible options.

### EmuGG by Consolius 

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20110127001428.webp) 

The main claim to fame of Consolius in the PSP scene is having created the only [Magnavox Odyssey 2 emulator](https://archive.org/details/pspemuodd-10.7z) for the system. How did he do with this port of the SMS Plus emulator?

Not great, frankly. Just like his other emulators, [EmuGG](https://archive.org/details/emugg10.7z) only had one, initial revision, with much left unfinished. Even the title of the EBOOT was left as 'Simple flames', which is one of the coding samples in the PSP unofficial dev kit.

In other words, EmuGG was released in a hurry, and it shows. There is a menu for selecting ROMs, but none for the options. The only way to change settings such as picture scaling and frame skip is to edit a text file. 

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20110127001408.webp)

The button mapping is also bizarre. The start button on the Game Gear is emulated by pressing L, while the PSP's actual start button is left unassigned.

### MasterBoy by Florian Brönnimann (Brunni)

[MasterBoy](https://archive.org/details/masterboy.-7z) is well known as a Game Boy emulator, but it can play Game Gear games pretty damn well. In fact, it might be the best Game Gear emulator for PSP.

This emulator is also based on SMS Plus, and features a generous amount of screen scaling options, including 2x (which will crop out a bit of the image) and 1.5x. 

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20110127001545.webp)

By default, a smoothing filter is applied to the video renderer, but it can be turned off in the settings. 

Such filters seem to be widespread on PSP emulators. I remember reading that the PSP has an inbuilt hardware function that makes pixel smoothing easy to implement, so maybe that is the reason?

Just as in Game Boy emulation, MasterBoy is stunningly frugal in its use of system resources. Games like OutRun will play at full speed, with zero frame skip, with the PSP's CPU clocked at 150 MHz.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20110127001949.webp)

A reminder: MasterBoy 2.10, EmuMaster 3.10 and the like are not real updates. The only change is that some guy altered the title and slapped his name on the release. The last actual update was 2.02 in 2007.

### e[mulator] by e (T. Kawamorita)

[e[mulator]](https://archive.org/details/emulator_082f.7z) was RetroArch before RetroArch: this oddly named creation will play ROMs for a bunch of low-powered systems, Game Gear included. 

The downside, in this case, is the lack of any real system-specific settings. There are four video rendering options common to all systems to choose from: one CPU-driven mode, and three for GPU. The x1 CPU renderer looks alright, but the GPU modes are all a bit of a blurry mess. 

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20110127001020.webp)

The lowest CPU clock setting, 266 MHz, will play Alien Syndrome at full speed. Not as impressive as MasterBoy, but still not bad.

### MMSPlus by Florian Brönnimann (Brunni)

[MMSPlus](https://archive.org/details/mmsplus.-7z) is an early version of Brunni's port of the SMS Plus emulator, before it was merged with his Game Boy emulator to create MasterBoy. 

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20110127002909.webp)

It runs about as well as MasterBoy, but there is no reason to use this outdated, standalone build.

### PSPMaster by [Bo]Trops

[PSPMaster](https://archive.org/details/pspm.-7z) is another port of Charles MacDonald's SMS Plus emulator, and the only PSP work by the otherwise unknown [Bo]Trops.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20110127003219.webp)

This emulator does not have an FPS counter among its settings, but it seems to perform just as well as MasterBoy when downclocked to lower CPU frequencies.

It does have a 'high resolution' video renderer, which does not seem to do anything much to the games I tested. The other screen modes are quite good, though.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20110127003502.webp)

The only factor that keeps this emulator from achieving greatness is the occasional heavy glitching that affects some games.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20110127003800.webp)

### SMS PSP by Yoshihiro

[SMS PSP](https://archive.org/details/sms-psp-v-0.3.7z) is a rather early, rather crude attempt at Game Gear emulation on PSP. Unlike many of the emulators on this list, it is not a port of SMS Plus, but rather of Marat Fayzullin's MasterGear.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20110127014112.webp)

While it is definitely good to have some variety, the complete lack of any settings, as well as the constantly crackling sound, make this no more than a forgotten detour on the way that led to proper Game Gear emulation on PSP.

### SMS Plus PSP by Akop Karapetyan

[SMS Plus PSP](https://archive.org/details/smsplus-1.3.1-1.0.7z) was the biggest surprise on the list - and not in a good way. 

I expected that any emulator from Akop Karapetyan would be a serious rival to MasterBoy's dominance of the Game Gear emulation crown. Instead, it is nothing but dead weight on my Memory Stick - it won't launch any games at all. I tried turning off plugins, using an official Sony Memory Stick, all in vain. 

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20220427204613.webp)

Even PPSSPP, which will normally run just about anything so long as it is compiled, shows an invalid memory access with this one.

Earlier versions of this emulator had [a Japanese translation](https://archive.org/details/smsppsp_jp.7z) and even an [ad-hoc build](https://archive.org/details/smsplusadhoc.7z), which suggests that it stopped working as a result of a later firmware upgrade.

### SMS Plus PSP by theelf

This [SMS Plus PSP](https://archive.org/details/smsplus.-7z_202107) is a modified version of Akop's emulator mentioned above. 

Theelf is a modder who added overlays and custom scaling to some PSP emulator, and I generally don't much care for his work. In this case it was a godsend, however.

Theelf's mod of SMS Plus PSP only works with zipped ROMs, but work it does. 

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20220427203619.webp)

The overlay is not too obtrusive in this case, and it can be turned off in the options. 

A good amount of scaling options are on offer, and a full-speed game of OutRun can be played at 222 MHz.

### SMSPlus by Chris Swindle. Last updated in 2005.

[SMSPlus](https://archive.org/details/smsplus.-7z) is another early Game Gear emulation that has not been updated since 2005. And for its time, it is not bad at all. 

It has two screen scaling options to choose from (full and stretched), a plain but functional settings menu, and even ad-hoc multiplayer? This might be the earliest PSP emulator which supports it.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20220427202739.webp)

The screen has a smoothing filter with no way to disable it and in general, it is not as good as later Game Gear emulators, which is natural enough. 

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20220427202848.webp)

The same Chris Swindle later worked on the [first port of Quake](https://archive.org/details/pspquake.7z) to the PSP.

### RetroArch

RetroArch cores on PSP have a bad rep in terms of performance, accuracy and well, basic ability to actually function. Does the same apply to the Game Gear cores?

Well, kinda. For Game Gear ROMs, RetroArch 1.10.3 provides us with three options to choose from: the GearSystem, PicoDrive and SMS Plus GX cores.

GearSystem is slow. Alien Syndrome at less than 35-40 FPS would be respectable if we were talking of emulating the arcade game. But the Game Gear port?

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20220427205339.webp)

Next, PicoDrive. This one freezes right after the title screen. 

And SMS Plus GX. This one is actually pretty decent, reaching full speed. 

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20220427205844.webp)

Granted, it powers through at the full 333 MHz - RetroArch cores don't care about your PSP's battery life. But unlike the other two cores, this one is actually playable, which makes it the clear winner in the RetroArch realm. 
