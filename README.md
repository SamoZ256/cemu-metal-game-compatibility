# Cemu Metal game compatibility list

This repository contains a list of games compatible with the Cemu Metal backend. You can see the list by going to `Issues` (games that match other platforms in terms of playability and performance will be under the `Closed` tab). If you don't find the game you were looking for, it means it wasn't tested yet.

## How to test games

You can get the latest release of Cemu Metal [here](https://github.com/SamoZ256/Cemu/tags) (pick the top-most one). From there just run any game you'd like (also make sure you have Metal selected as a graphics API in settings).

## How to report game status

If you have tested a game that isn't in `Issues`, please report it [here](https://github.com/SamoZ256/cemu-metal-game-compatibility/issues/new?assignees=&labels=&projects=&template=game-compatibility-template.md&title=). Use the game name as a title. If the game you tested doesn't work as intended, please provide a detailed description of what exactly the issue is. Attaching a log is really helpful as well.

## Graphics packs

Many graphics packs use custom shaders written in GLSL, but that is currently not supported by the Metal backend. So please, disable all your graphics packs before testing a game. The only exception is the `FPS++` mod for botw (FPS unlocking packs for other games might work as well, but they haven't been tested yet).

## How to make a frame capture

If there are graphical issues in a game, it might be useful to make a frame capture.

### For Metal

First, execute `launchctl setenv METAL_CAPTURE_ENABLED 1` in the terminal to enable Metal frame capture for all apps. This has slight (almost non-measurable) impact on the performance. You can disable it by either running `launchctl setenv METAL_CAPTURE_ENABLED 0` or restarting macOS. Next, go to `General Settings -> Debug` and set `GPU capture save directory` to the directory that you want the capture to save to. Now when you have launched a game and want to do a frame capture, simply choose `Debug -> Capture frame (Metal)` in the menu bar. Note that the frame capture might freeze the game for as long as a few minutes depending on the complexity of the game and how powerful your computer is. The frame capture is complete once the game unfreezes.

### For Vulkan

The option for Metal isn't available for Vulkan. See [this guide](https://github.com/SamoZ256/cemu-frame-capture) on how to make a frame capture with the Vulkan backend.

## How to fix performance issues

There are some tricks to improve performance for some games. Make sure to use the FPS++ mod in *The Legend of Zelda: Breath of the Wild*. Setting the `buffer cache mode` (in game profile) to either `device shared` or `host` will slightly improve the performance in most games, and will also completely fix performance issues present in *The Legend of Zelda: Wind Waker HD* in areas with lots of particles. Games that get substantial performance improvement from using these alternative buffer cache modes will be labeled with `buffer cache change`. Just note that changing this option might cause graphical issues in certain games (for example in *New Super Mario Bros U*, all blocks will appear yellow when going into the same level for the second time).

## Intel Mac issues

Games utilizing geometry shaders (for example *Super Mario Maker*) may crash your whole computer on certain Macs with Intel GPUs (AMD and Apple Silicons are fine). While the cause of this issue remains unknown, it's most likely a bug in the Intel Metal drivers, so there is not much we can do about it. Users with Intel GPUs are therefore advised to run games with caution. A good way to find out if a game uses geometry shaders is to see if GUI or the whole screen is cut diagonally when Vulkan is used (like the mini map in *The Legend of Zelda: Twilight Princess* or the whole screen *Mario Tennis: Ultra Smash*).

## Got any other questions?

In case you'd like to ask anything regarding the Metal backend for Cemu, feel free to reach out in the official Cemu discord server in the `macos` channel.
