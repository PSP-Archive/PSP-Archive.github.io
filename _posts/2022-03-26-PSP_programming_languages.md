---
layout: post
title: "PSP programming languages"
author: "Pierre L"
categories: apps
tags: [PSP,homebrew]
image: /assets/img/random/hello_rust.webp
---

Here's a brief overview of the language options available to would-be PSP programmers.

### Lua

Lua is far and away the most popular choice for PSP programming, judging by the quantity (if not necessarily quality) of homebrews coded in this language. 

Beyond the original [Lua Player](https://luaplayer.org/), which struggles to work with modern firmware revisions, there are tons of interpreters to choose from.

Each one implements PSP-specific functions a bit differently, so code written for one interpreter won't necessarily work with another.

Homebrew games and apps coded in Lua get a bad rep, but in the right hands, results can be impressive. The 3D rail shooter [Gcrew's Defense Patrol](https://archive.org/details/gdp.-7z) is entirely coded in Lua.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/20210627160102.webp)

[ONELua](http://onelua.x10.mx/) is the most recent out of all the Lua interpreters for PSP, as well as the best documented.

### C / C++

C and C++ are what you would use with the [unofficial PSP SDK](https://github.com/pspdev/pspdev). The choice languages of coders who want to go beyond the limits of Lua. There is plenty of PSP code in C stored on the [PSP Archive](https://github.com/PSP-Archive), as well as elsewhere on GitHub.

There used to be dozens of sites and webpages devoted solely to C/C++ coding and tutorials for PSP, but nearly all have vanished over the years. A few surviving resources are gathered [on this page](https://github.com/PSP-Archive/docs#learning-resources).

More recently, Iridescence published a series of [PSP coding tutorials](https://www.youtube.com/watch?v=35q-7ITBzSk&list=PLwIRcsl57ziPsDYCi6bgO-W9qqAwuW3Mk) on YouTube.

### Python

Python interpreters for PSP have been around since all the way back in 2005, but they were never as popular as Lua. All in all, only [20-odd](https://archive.org/details/psp-homebrew-library?query=subject%3Apython) PSP apps and games have been coded in Python since then.

One of the most impressive PSP homebrews coded in Python is [Portable Bubble](https://archive.org/details/portable-bubble-v-2.1.0.7z), a Puzzle Bubble clone by Germano Fabio.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/snaps/PORT01413_00000.webp)

### Rust

One of the newest additions to this list, the [Rust PSP project](https://github.com/overdrivenpotato/rust-psp) started in May 2020, though earlier experiments with Rust on PSP date all the way back to [2014](https://github.com/luqmana/rust-psp-hello). 

Not very much used so far, beyond a few coding samples. 

### BASIC

The PSP can run BASIC code thanks to [PSP Yabasic](https://archive.org/details/pspyabasic_v10a.7z). BASIC never really gained any traction on this device, but it should play homebrews coded for the official [Yabasic port for PS2](https://archive.org/details/gs_20211117192719).

### Ruby

[Joyau](https://archive.org/details/joyau-release) is the name of the only Ruby interpreter for PSP. It was first published in 2009 - relatively late in the handheld's lifespan, so it never managed to gain any following among developers. Still, the interpreter release does include some working code samples.

### Javascript

The standard PSP web browser is capable of running Javascript natively. Beyond that, a homebrew app named [JS-Otello](https://archive.org/details/js-otello) seems to run on an otherwise unknown Javascript interpreter of sorts. 

### C#

There is now some (basic) support for C# coding on PSP, thanks to Matt Emsom's port of [DotNet Anywhere](https://github.com/memsom/PSPDNA). The developer also coded [a version of Tetris](https://archive.org/details/PSPDNA) to showcase the port's abilities.

### Assembly

Coding a PSP program in MIPS assembly alone is certainly a possibility, though not a popular one. The homebrews fully written in this language are no more than a handful - TyRaNiD's [Minifire](https://archive.org/details/minifire) being the best known.

Some learning resources are available, such as [the MIPS page](https://github.com/uofw/uofw/wiki/MIPS) of the uOFW project.

### Zig

Another recent addition to the PSP coding repertoire, the [Zig port](https://github.com/zPSP-Dev/Zig-PSP) is yet to see any use beyond a few basic coding samples.

### GameMaker

While calling it programming might be a stretch, a PSP port of [GameMaker 8.1](https://github.com/KuromeSan/chovy-gm) and has seen increasing use in recent years. First [showcased in 2010](https://www.youtube.com/watch?v=cmAA6FJkVgQ), GameMaker for PSP has been used for two official PSP Mini releases before resurfacing as a homebrew project on GitHub nearly a decade later.

*Image credit: [kibwen on Reddit](https://www.reddit.com/r/rust/comments/2m10id/hello_world_on_a_psp_via_rust/)*
