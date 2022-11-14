# vgmsplit: Program to record channels from chiptune files

Modified to compile on macOS 10.15.7 via CMake (and possibly Linux and Windows. Haven't tested). This is still a WIP. Uses a modified version of mpyne's [Game Music Emu 0.6.3 (latest version as of 2022)](https://bitbucket.org/mpyne/game-music-emu)

## Usage
You will have to build the game-music-emu binary first via CMake before building the main vgmsplit binary:

```
git clone https://github.com/htucker77/vgmsplit.git
cd vgmsplit
cd game-music-emu
make
cd ..
make
```


# Original readme


`vgmsplit` is an improved fork of `towave rel1` by icesoldier (source code of rel2 and rel3 were never uploaded).

## Bugfixes

- No longer erroneously skips silence in track 1. (Also fixed in binary-only `towave rel3`)

## Features

- Automatically rips master audio (all channels together)
- Command-line arguments for duration and track number (both optional)
- Customizable sample rate (`-r, --rate`)
- Fadeout (8 seconds, hard-coded by libgme)
- More accurate YM2612 emulation
    - CMakeLists.txt with static linking to <https://bitbucket.org/mpyne/game-music-emu>

## Planned

- Ability to accurately dump NSF files with nonlinear mixing (by emulating dpcm, dpcm+tri, dpcm+tri+noise)
- More accurate NSF emulation (using nsfplay core?)

## Usage

vgmsplit will be used in <https://github.com/corrscope/corrscope>, a multi-channel oscilloscope program with "intelligent" correlation triggering and real-time playback.
