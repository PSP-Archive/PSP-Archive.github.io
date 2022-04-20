---
layout: post
title: "Injecting CD-based PC Engine games into the official PSP emulator"
author: "Pierre L"
categories: emulators
tags: [PSP,homebrew]
image: /assets/img/random/pce_inject.webp
---

Injecting PC Engine CD games into the official emulator on PSP is not hard. Just very time-consuming.

The logic behind the process has been well understood for years now. Reprep wrote [a long guide](https://wololo.net/talk/viewtopic.php?f=24&t=41526) on the topic already in 2015. I found some of his instructions to be hard to follow at times, and some of the tools he was using have become outdated or difficult to find over time - hence the following post.

Reprep began his guide by explaining how to convert the standard cartridge-based PC Engine games, but the new [TGInjector utility](https://www.reddit.com/r/PSP/comments/l0sg1e/tginjector_a_tool_to_take_advantage_of_soldier/) ([backup link](https://archive.org/details/tginjector-v-1)) created by IncendiaryIdea makes the process so simple that no guide is necessary. 

CD games are a different story entirely. In this case, the conversion process involves several steps in which to extract all the files contained in an official PC Engine CD game released for PSP, replace the game data and audio tracks with the target game, and put them all back into a format a PSP will understand.

To carry out the conversion, we will need:
- an official PSP release of a PC Engine CD game - I used Ys I & II (title ID: NPJJ30038) for this test,
- the PC Engine CD game to convert,
- the [PCE_py_tool and PCE_CD_tools](https://archive.org/details/pce-cd-tools) scripts,
- Python 2.7,
- [CDmage](https://www.videohelp.com/software/CDMage) 1.02.1 Beta (it has to be this specific version),
- [SCEI ATRAC3plus Codec Tool](https://archive.org/details/scei-atrac-3plus-codec-tool),
- the [bincuesplit](https://archive.org/details/bincuesplit) app.

### Step 1: decrypting

Grab the PSP version of Ys I & II. The files we need for this step are `CONTENT.DAT` and `PSP-KEY.EDAT`, found inside the `NPJJ30038` folder.

For this step, we will be using PCE_py_tool. Move `CONTENT.DAT` to the `PCE_py_tool\encrypted` folder and `PSP-KEY.EDAT` to `PCE_py_tool\keys`.

Run the `decrypt.py` script. This script requires Python 2.7 - using something like [Portable Python 2.7](https://sourceforge.net/projects/portable-python/) might be the fastest option if you don't have this older version already installed. The command-line executable is found under `Portable Python-2.7.17 x64\App\Python\python.exe`.

From the command line, run: 

`C:\[path to your Python 2.7]\python.exe C:\[path to PCE_py_tool folder]\decrypt.py`

The decryption process will take quite a while, and there is no visible indication of its progress, beyond a blinking cursor.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/random/pce_inj_step_1-1.webp) 

Once it is done, you will find the decrypted files in the `PCE_py_tool\decrypted\files` folder.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/random/pce_inj_step_1-2.webp) 

The .at3 files are sound files, while one or more .bin files contain the game data. The .hcd file is the table of contents, listing all the files that make up the CD. These are the files we will be replacing, everything else should be left as it is.

### Step 2: converting sound files

Now we will be working on the game to convert. The game will most likely come in the bin/cue format. 

If the CD dump came as several .bin files, they will need to be merged back together first. CDmage will handle that. Point it to the .cue file, and, making sure the disc image is highlighted on the left-hand side widow frame, select `Save as...` from the `File` menu. The default save options will work just fine.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/random/pce_inj_step_2-1.webp) 

CDmage can also extract audio tracks and convert them to wav. From the frame on the right-hand side of the CDmage window, click on one of the CD tracks, then press Ctrl+A to select them all. Then from the `File` menu, select `Extract Tracks...`. 

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/random/pce_inj_step_2-3.webp) 

In the next window, make sure to select `Wave file` under the `Audio as` dropdown window. Extract the files to an easily reachable folder, rather than the default AppData\Local\Temp path.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/random/pce_inj_step_2-4.webp) 

The `.tao` files are the data tracks, as extracted by CDmage in a format that is not really useful to us - they can be deleted.

Having done that, we can finally... convert the audio files again, this time into the ATRAC3plus format that the official PC Engine emulator will understand. `psp_at3tool.exe` will handle this stage of the process:

`psp_at3tool.exe -e input_track_01.wav output_track_01.at3`

Unless you feel like converting the files one by one, it is advisable to move `psp_at3tool.exe` and `msvcr71.dll` to the folder containing the extracted .wav files, and use a simple batch script, like:

```
cd /d "%~dp0"
for /r %%i in (*.wav) do psp_at3tool.exe -e "%%~nxi" "%%~ni.at3"
```

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/random/pce_inj_step_2-5.webp) 

We will not be needing the .wav files past this point, so they can be deleted.

### Step 3: creating the new table of contents for the disc

Once every single audio track has been converted, it is time to work on the .hcd table of contents. 

`bincuesplit.exe` is what we will be using here. This app was created for a PC Engine emulator on the Wii, but it will prove useful to us as well. Point it to the *single* bin/cue files put together by CDmage, and make sure to add `hcd` to the command-line options.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/random/pce_inj_step_3-1.webp) 

The utility will convert audio files to .ogg (useless to PSP owners, delete them) and most importantly, create a new .hcd table of contents.

So keep the .iso files, trash the .ogg, and rename the .hcd to the file name used by the official release (`HCD9009.hcd` for Ys I & II).

In the newly renamed .hcd file, change the extension for the audio tracks from .ogg to .at3, and .iso to .bin for data (a simple search and replace will suffice). 

Change the track titles too, to match the naming scheme used by the original release. `track01` becomes `HCD9009_01`, and so forth. Search and replace is, once again, your friend.

Rename the at3 files converted in step 2 to match the new titles in the .hcd. There are no doubt fancier ways to do this, but [PowerRename](https://docs.microsoft.com/en-us/windows/powertoys/powerrename) works well enough.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/random/pce_inj_step_3-2.webp) 

### Step 4: ISO to BIN

Audio files are not alone in requiring conversion - data files need some work as well. It is time to go back to the .iso files created by bincuesplit in the previous step.

`PCE CD tools` exists for this purpose: `comp.py` takes an .iso file as input, and spits out a `compressed.bin` file that is suitable for our needs. Again, this script will need Python 2.7 to run.

If the game to convert has many data tracks, adding this to line 6 of `comp.py` can make the process a bit less tedious:

```
compressed = os.path.splitext(os.path.basename(fd.name))[0]
```

and replace every instance of `'compressed.bin'` with `compressed + '.bin'`.

As the game I am converting does indeed have lots of data tracks, I will be using a batch script in this step as well:

```
cd /d "%~dp0"
for /r %%i in (*.iso) do "C:\[path to your Python 2.7]\python.exe" comp.py "%%i"
```

This will work, provided that `comp.py` has been previously copied into the folder where the `.iso` files are found.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/random/pce_inj_step_4-1.webp) 

The .iso files can now be deleted, while the newly created .bin files must be renamed according to the names found in the .hcd table of contents: `track02.bin` to `HCD9009_02.bin`, and so on.

### Step 5: repacking

Let's return to the `PCE_py_tool\decrypted\files` folder. Delete all of the original `.hcd`, `.at3` and `.bin` files. Replace them with the corresponding files we just created for the new game: the `.bin` from step 4, `.hcd` from step 3 and `.at3` from step 2.

Run the `encrypt.py` script (again, with Python 2.7). Just like unpacking, the packing process is going to take a while.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/random/pce_inj_step_5-1.webp) 

Once the script has completed its job, the new `CONTENT.DAT` will appear under `PCE_py_tool\final`. Move the file, along with `PSP-KEY.EDAT` and `PARAM.PBP`, back into the folder of Ys I & II. 

PPSSPP may not support PlayStation 1 EBOOTs, but it is able to play emulated PC Engine releases. It can act as a test bench to see if the conversion process was successful, before finally moving the files to an actual PSP.

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/random/valis_ppsspp.webp)

### Arcade Card?

Sometimes the conversion will be seemingly successful, but after starting the game this message will appear:

![Screenshot](https://github.com/PSP-Archive/PSP-Archive.github.io/raw/gh-pages/assets/img/random/pce_inj_step_6-1.webp) 

Reprep suggests appending `arcade,1` at the bottom of the .hcd file, but that does not do anything in my experience. Updates will follow if a solution is found.

### Credits

- Reprep: for the original guide
- qwikrazor87: PCE_py_tool and PCE CD tools
- Francisco Muñoz (Hermes): bincuesplit
