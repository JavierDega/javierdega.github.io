---
layout: page
title: Personal
permalink: /personal/
---
## [PiP - 2D Physics Solver](https://github.com/JavierDega/PiP)
<img style="float: middle;" src="../assets/PiPScreenGrab.png" alt="PiP" title="PiP">
<br/>
<br/>
[PiP](https://github.com/JavierDega/PiP) is an open source 2D solver I build in my free time. I wanted to further my knowledge in physics engines after my dissertation's 
[3D Solver](https://github.com/JavierDega/DX_3DPhysics), with a proper library that I hope people can use and learn from.
It supports circles, capsules and oriented bounding boxes and has a bunch of settings to customize runtime behavior, display debug
information, and edit rigidbodies at runtime. One core idea I've enjoyed thorougly throughout development is the ability to change between
fixed and floating point numerical methods with one compiler flag, 'USE_FIXEDPOINT' in 'PiPMath.h'. It supports CMake to build Visual Studio
solution files.
- Graphics and windowing with OpenGL, glew.
- UI in ImGui.
- Unit testing with catch2. 

## Homebrew dev
Throughout uni I became a fan of the [devKitPro](https://devkitpro.org/) toolchain for homebrew game development, so I used it to fulfill a couple artefacts. 
the result is a retro style [GBA puzzle bobble clone](https://github.com/JavierDega/Gba-Puzzle-Bobble), and a 
[voxelized 3D pool game](https://github.com/JavierDega/VoxelPool_Wii) for the Wii using the Wiimote. I made everything in these except the main 
track for the Wii, [Pool Hall Jam](https://soundcloud.com/omnidigital/pool-hall-jam) by Ollie Plaatsman

<iframe width="702" height="395" src="https://www.youtube.com/embed/nBaU7Xpso-Q" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<iframe width="702" height="395" src="https://www.youtube.com/embed/_IwZnQj_zqE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

With these I leanred various things, such as:
- .obj model parsing
- Lighting / graphics with OpenGL ES based APIs (GX is the graphics framework for Wii / Gamecube)
- Plugging in assembly code to your C code ( GBA uses ARM Assembly THUMB2 for some recurring functions)
- Game physics

I wrote a devlog on the gba game 'Haunted Bobble' [here](https://javierdega.github.io/junk/2018/09/01/Hexagonal-Grids!-A-Puzzle-Bobble-Tutorial.html).
You can run both games by plugging in the appropriate output file in the repo (.gba, .dol) into your emulator of choice, as running it on hardware would not
be legal!

I've done other smaller things throughout the years, which are probably hinted at on my [youtube channel](https://www.youtube.com/channel/UCvBTH-OXl4d4M_MIVpegrpQ),
but I consider these my highlights, hope you enjoyed!

