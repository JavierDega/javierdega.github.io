---
layout: page
title: Personal
permalink: /personal/
---

I've done several smaller things throughout the years, some of which are probably hinted at on my [youtube channel](https://www.youtube.com/channel/UCvBTH-OXl4d4M_MIVpegrpQ), but I consider these my highlights, hope you enjoyed!

## [PiP - 2D Physics Solver](https://github.com/JavierDega/PiP)
<img style="float: middle;" src="../assets/PiPScreenGrab.png" alt="PiP" title="PiP">
<br/>
<br/>
[PiP](https://github.com/JavierDega/PiP) is an open source 2D physics solver I built in my spare time during my first couple years doing gamedev.  
It supports circles, capsules and oriented boxes. It has a bunch of settings to customize runtime behavior, display debug
info and edit bodies at runtime. One core idea I've enjoyed thorougly throughout development is the ability to change between
fixed and floating point numerical methods with one compiler flag, 'USE_FIXEDPOINT' in 'PiPMath.h'.  
It uses CMake for build generation and it runs on Windows and Linux, tested with Visual Studio code.
- C++
- Graphics, windowing, input (OpenGL, [glew](http://glew.sourceforge.net/), [glfw](https://www.glfw.org/)).
- UI ([ImGui](https://github.com/ocornut/imgui)).
- Unit testing ([catch2](https://github.com/catchorg/Catch2) single header version).

## Homebrew dev
Throughout uni I became a fan of the [devKitPro](https://devkitpro.org/) toolchain for homebrew game development, so I used it to create a couple artefacts.   
The result is a retro styled [GBA puzzle bobble clone](https://github.com/JavierDega/Gba-Puzzle-Bobble), and a 
[voxel based 3D pool game](https://github.com/JavierDega/VoxelPool_Wii) for the Wii using the Wiimote's motion controls.  
I made everything for these except the main track for the Wii, [Pool Hall Jam](https://soundcloud.com/omnidigital/pool-hall-jam) by Ollie Plaatsman from [omni-digital technologies](https://www.omnidigitaltechnologies.co.uk/).

<iframe width="702" height="395" src="https://www.youtube.com/embed/nBaU7Xpso-Q" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<br/>
<iframe width="702" height="395" src="https://www.youtube.com/embed/_IwZnQj_zqE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<br/>
They taught me various things, such as:
- .obj model parsing.
- Lighting / graphics with OpenGL ES based APIs (GX is the graphics library for Wii / Gamecube).
- Plugging in assembly code to your C code (GBA uses ARM Assembly THUMB2 for some recurring functions).
- Game physics.

I wrote a devlog on the GBA game 'Haunted Bobble' [here](https://javierdega.github.io/junk/2018/09/01/Hexagonal-Grids!-A-Puzzle-Bobble-Tutorial.html).
You can run both games by plugging in the appropriate output file in the repository (.gba, .dol) into your emulator of choice, as running it on hardware would not be legal!

