# Cemu Metal game compatibility list

This repository contains a list of games compatible with the Cemu Metal backend. You can see the list by going to `Issues`. If you don't find the game you were looking for, it means it wasn't tested yet.

## How to test games

You can get the latest release of Cemu Metal [here](https://github.com/SamoZ256/Cemu/tags) (pick the top-most one). From there just run any game you'd like (also make sure you have Metal selected as a graphics API in settings).

## How to report game status

If you have tested a game that isn't in `Issues`, please report it [here](TODO). If the game you tested doesn't work as intended, please provide a detailed description of what exactly the issue is. Attaching a log is really helpful as well.

## How to make a frame capture

If there are graphical issues in the game, it might be useful if you made a frame capture. See [this guide](TODO) on how to make one.

## How to fix performance issues

There are some tricks to improve performance for some games. Turning `Accurate Barriers` off in the `Debug` section of the menu bar can greatly improve the performance in *The Legend of Zelda: Breath of the Wild* (make sure to also use the FPS++ mod). Setting the `buffer cache mode` (in game profile) to either `device shared` or `host` will slightly improve the performance in most games, and will also completely fix performance issues present in *The Legend of Zelda: Wind Waker HD* in areas with lots of particles. Just note that changing this option might cause graphical issues in certain games (for example in New Super Mario Bros U, all blocks will appear yellow when going into the same level twice).

## Got any other questions?

In case you'd like to ask anything regarding the Metal backend for Cemu, feel free to reach out in the official Cemu discord server in the macOS channel.
