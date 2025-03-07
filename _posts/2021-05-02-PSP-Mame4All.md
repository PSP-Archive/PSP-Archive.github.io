---
layout: post
title: "PSP Mame4All 5.1"
author: "Pierre L"
categories: emulators
tags: [PSP,homebrew]
image: /assets/img/snaps/2021-05-02-PSP-Mame4All.webp
---

[PSP Mame4All](https://github.com/PSP-Archive/PSP-MAME4ALL/releases) is the portable version of MAME, the venerable PC emulator of arcade games. 

This PSP version of MAME has been around since 2006, and over the years it has gained a reputation for being hard to get up and running.

There are two main things to keep in mind while trying to get it to work. First, each version of MAME requires slightly different ROM dumps for each of the games. This is unlike console emulators, where any ROM of the same game can be expected to work with basically any emulator.

Beyond this caveat, which applies to any MAME build, there are limits intrinsic to the PSP itself. Arcade games from the 1980s tended to be more technically demanding than contemporary console games, which means that the PSP will struggle to emulate them, even where it can play NES or Master System games without breaking a sweat.

PSP Mame4All targets arcade games from the early 1980s, and can play most of them at quite a good speed.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/sega_1983.webp)

Within those tight limits, the emulator performs just fine. But even slightly later games, like the 1985 Space Harrier, run too slow to be playable.

## Alternatives

PSP Mame4All is not always the best choice to emulate arcade titles on the PSP. While the work that developers put into this project is commendable, there are several scenarios where other alternatives are preferable.

- For Capcom **CPS1**, **CPS2**, **NeoGeo CD** and **MVS** games: the [emulators created by NJ](https://archive.org/details/psp-homebrew-library?query=nj&and[]=subject%3A%22emulator%22) are the superior option.

- The various **Final Burn Alpha** builds also offer a better experience than Mame4All. The list of games supported by FBA4PSP is [available here](https://github.com/PSP-Archive/FBA4PSPmod/blob/master/docs/gamelists/full-gamelist.md).

- the [PSPMAME](https://archive.org/details/psp-homebrew-library?query=PSPMAME) ports are based on a later version of MAME (0.97) and thus notionally support more games, but generally run *worse* than PSP Mame4All.

As a rule of thumb, Mame4All is the advisable option mostly for early arcade games created by western manufacturers. Games like Tapper.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/mame4all_tapper.webp)

## Setup guide

### Step 1: get the ROMs 

As mentioned, the setup process for Mame4All isn't the most user-friendly. Just like other versions of MAME, it requires some very specific sets of ROMs - copying random games into the 'roms' folder will most likely yield an error screen like this one:

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/mame4all_error.webp)

These errors are fixable most of the time by using [RomCenter](https://www.romcenter.com/).

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/mame4all_dk.webp)

The romset of PSP Mame4All is a mix of MAME 0.34 and 0.36. Out of the commonly available romsets, MAME 2000 is the closest to Mame4All's specs. But even that one is based on a significantly more recent version of MAME - 0.37b5.

So get the MAME 2000 romset or older - downloading any newer sets is a waste of time, because the emulator won't be able to read many of the ROMs.

### Step 2: .dat file and RomCenter

The [PSP Mame4All release](https://github.com/PSP-Archive/PSP-MAME4ALL/releases) includes a `clrmame_roms.dat` file, to be used with programs like RomCenter (or other ROM managing apps) to make sure the ROMs you'll be feeding to Mame4All will match the (rather ancient) romset of the emulator.

The .dat file exists to address this issue. Open RomCenter, select New, then 'Get data from'. Next, select the `clrmame_roms.dat` contained in the Mame4All release.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/random/romcenter_mame4all_1.webp)

After creating the database, drag the folder with your ROMs onto the RomCenter window.

The games that appear in green are good to go. The ones in yellow require a fix. RomCenter will take care of the fixing process after selecting the appropriate option.

The ROMs shown in red are not compatible with Mame4All. The only solution is to find another ROM dump of the same game.

## Settings

There aren't many options to choose from in this emulator. There are no save states, and most of the settings that are available should be left at their default values.

You can adjust the aspect ratio by pressing L+R. There are four scaling options to choose from: Fixed, Fixed DIV2, SW scaled, SW stretched. 

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/mame4all_scaling.gif)

The software scaling modes look like a wobbly mess. DIV2 is good for games that have a resolution bigger than the PSP screen.

Holding L and R gets you a pause menu, from which you can exit the emulator.

## History of the port

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/random/mame4all_famtree.webp)

PSP Mame4All was created by [TTYman](http://ttyman.free.fr/) and is based on the Dreamcast emulator [Mame4All](http://chui.dcemu.co.uk/mame4all.html), which was ported from MAME GP2X by [Franxis](https://web.archive.org/web/20060615053415/http://www.talfi.net/gp32_franxis/), which is itself a port of MAME 0.34. The last release from the TTYman himself was 4.9r2 Hires, back in November 2007. 

The source code for version 5.1 was found by yours truly, late in 2020, on a rickety German website. The code base dates back to 2010, but the PSP-specific parts of the code are almost certainly even older. 

The code was compiled - with a lot of help from Sajattack - and distributed on Reddit. To the best of my knowledge, this version had never been circulated before.

According to the documentation, turning off the graphical elements in the menus saves 1Mb of memory. Given how ugly they were, I would have gladly disabled them regardless. If you want them back, the source code is in the [PSP Archive on GitHub](https://github.com/PSP-Archive/PSP-MAME4ALL), waiting to be compiled.

<video class="center" width="480" height="272" controls>
	<source type="video/mp4" src="https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/video/2021-05-02-PSP-Mame4All.mp4">
</video>

## Other versions of Mame4All

Mame4All has been ported to PSP a number of times over the years, but TTYman's version is the only one worth trying today.

- The first port was in May 2006 - [MAME4ALLPSP](https://archive.org/details/mame-4-allpsp.-7z_202107) by sasuke2911. It only works on firmware 1.50.

- After that, we have [MAME4ALL-PSP](https://archive.org/details/mame-4-allpsp.-7z) by Kech, which was discontinued a month later, in June 2006.

- A later version, from August 2011, is [MAME4ALL for PSP](https://archive.org/details/mame-4-all-v-4.9r-2-jp.-7z). But it was created for a Japanese audience, and the interface is all in Japanese.

## Download

<p class="download-btn">
    <a href="https://github.com/PSP-Archive/PSP-MAME4ALL/releases/tag/5.1">
	<img border="0" alt="Download the homebrew" src="/assets/img/icon0/2021-05-02-PSP-Mame4All.webp" width="130" height="70">
	Download the homebrew
	</a>
</p>
