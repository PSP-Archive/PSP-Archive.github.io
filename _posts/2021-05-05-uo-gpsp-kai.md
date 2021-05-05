---
layout: post
title: "TempGBA4PSP-mod"
author: "Pierre L"
categories: emulators
tags: [PSP,homebrew]
image: /assets/img/snaps/tempgba.png
---

-- Overview

Emulates Game Boy Advance hardware.
Game Boy Advance dedicated software can be executed.

Uo gpSP Kai was created by [Exophase](https://github.com/phoe-nix/), Takka

Based on this version (TempGBA4PSP-26731020), http://www1.axfc.net/uploader/so/3063963

- Added gpsp kai 's cheats function.

- Added Chinese language.

- Added restore function.

- New menu icon.

- Impoted code from TempGBA-mod-dstwo-26750220

## GBA BIOS


To run it, you need the actual BIOS image. <b>gba_bios.bin</b>

                     ::Thanks::

このソフトウェアは、takka氏のgpSP kai 3.1、Nebuleon氏のTempGBAをベースにしています。

文字表示は、mediumgauge氏の全角文字表示ライブラリをベースに使用しています。

PNGイメージ作成、ボリュームバー表示は、NJ氏のnjemuのコードを使用しています。


Gameboy Advanceのハードウェア仕様は、以下のドキュメントを参考にしています。
 GBATEK by Martin Korth.
 CowBite Virtual Hardware Specifications by Tom Happ

以下のPC用GBAエミュレータのコードを参考にしています。
 VisualBoyAdvance   by Forgotten & VBA development team
 VisualBoyAdvance-M by VBA-M development team

According to the documentation, turning off the graphical elements in the menus saves 1Mb of memory. Given how ugly they were, I would have gladly disabled them regardless. If you want them back, the source code is in the [PSP Archive on GitHub](https://github.com/PSP-Archive/PSP-MAME4ALL), waiting to be compiled.

<video class="center" width="480" height="272" controls>
	<source type="video/mp4" src="https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/video/2021-05-02-PSP-Mame4All.mp4">
</video>

### Download

<p class="download-btn">
    <a href="https://archive.org/compress/gp-sp-kai-v-3.4-test-4-b-230fat.-7z/formats=7Z&file=/gp-sp-kai-v-3.4-test-4-b-230fat.-7z.zip">
	<img border="0" alt="Download the homebrew" src="/assets/img/icon0/tempgba.png" width="130" height="70">
	Download the homebrew
	</a>
</p>