---
layout: page
title: Personal
permalink: /personal/
---

I've done several smallish things through the years, some of which are probably hinted at on my [youtube](https://www.youtube.com/channel/UCvBTH-OXl4d4M_MIVpegrpQ) channel or [itch.io](https://javierdega.itch.io/); consider these my highlights, hope you enjoyed!  

## [PiP - 2D Physics Solver](https://github.com/JavierDega/PiP)  

<iframe width="100%" height="395" src="https://www.youtube.com/embed/kfobE3O5B7Y" title="pip youtube" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<br/>   

[PiP](https://github.com/JavierDega/PiP) is an open source 2D physics solver I built in my spare time during a couple of years, which I now try to maintain.  
It supports circles, capsules and oriented boxes. It has a bunch of settings to customize runtime behavior, display debug info and edit bodies at runtime. One core idea 
I've enjoyed thoroughly is the ability to change between fixed and floating point numerical methods with one compiler flag, 'USE_FIXEDPOINT' in 'PiPMath.h'. This is done
by compiling a [fixed point library](https://gitlab.com/DixieDev/fixed-point-lib) made by a friend, Anthony Arian.  

It uses CMake for build generation and runs on Windows and Linux, tested with Visual Studio code.
- C++
- Graphics, windowing, input (OpenGL, [glew](http://glew.sourceforge.net/), [glfw](https://www.glfw.org/)).
- UI ([ImGui](https://github.com/ocornut/imgui)).
- Unit testing ([catch2](https://github.com/catchorg/Catch2) single header version).  

## [Omni Digital technologies](https://www.omnidigitaltechnologies.co.uk/) - [Awaken Alone](https://www.omnidigitaltechnologies.co.uk/awakenalone)  

Retro styled point & click adventure game like Thimbleweed Park, Maniac Mansion,.. Made in UE4.
Wake up as the sole survivor of "Artemis Agroterra III" and piece together what happened by solving puzzles, interacting and wrangling together various items.  

<img style="float: middle;" src="../assets/awakenalone.png" alt="aa" title="aa" width="49%" >
<img style="float: middle;" src="../assets/awakenalone2.png" alt="aa" title="aa" width="50%" >
<br/>  
  
I initially helped implement common item interactions in UE4 Blueprints, and filled in the text popups for the hundreds of items in the spec. More recently I came in to fix
cutscene and advertising issues, as well as UI scaling for different devices, so the game could remain up on the [Play Store](https://play.google.com/store/apps/details?id=com.OmniDigitalTechnology.AwakenAlone_2022&gl=ES).

<iframe width="100%" height=395 src="https://www.youtube.com/embed/aiiAYbPAASs" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>  
<br/>  

<iframe width="100%" height=395 src="https://www.youtube.com/embed/5Zbs8JyTVhM" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>  
<br/>  

Awaken Alone is out as a prototype on [itch.io](https://omni-digital.itch.io/awakenalone), and [Google Play Store](https://play.google.com/store/apps/details?id=com.OmniDigitalTechnology.AwakenAlone_2022&gl=ES)

## Homebrew dev

Throughout uni I became a fan of the [devKitPro](https://devkitpro.org/) toolchain for homebrew game development, so I used it to create a couple artefacts.   
The result was a retro styled [GBA puzzle bobble clone](https://github.com/JavierDega/Gba-Puzzle-Bobble), and a 
[voxel based 3D pool game](https://github.com/JavierDega/VoxelPool_Wii) for the Wii using the Wiimote's motion controls.  
I made everything for these except the main track for the Wii, [Pool Hall Jam](https://soundcloud.com/omnidigital/pool-hall-jam) by Ollie Plaatsman from [omni-digital technologies](https://www.omnidigitaltechnologies.co.uk/).  

<iframe width="100%" height="395" src="https://www.youtube.com/embed/nBaU7Xpso-Q" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<br/>  

<iframe width="100%" height="395" src="https://www.youtube.com/embed/_IwZnQj_zqE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<br/>  

They taught me various things, such as:
- .obj model parsing.
- Lighting / graphics with OpenGL ES based APIs (GX is the graphics library for Wii / Gamecube).
- Plugging in assembly code to your C code (GBA uses ARM Assembly THUMB2 for some recurring functions).
- Game physics.  

I wrote some [stuff](https://javierdega.github.io/2019/02/26/Puzzle-Bobble.html) on the GBA game 'Haunted Bobble'.
You can run both games by plugging in the appropriate output file in the repository (.gba, .dol) into your emulator of choice, as running it on hardware would not be legal!

## Gamejams

### [LD48: Deeper and Deeper](https://javierdega.itch.io/ld48-journey-to-the-center-of-the-mind)

'Journey to the center of the mind' is a surreal endless faller we built in a weekend as a team of 3 for ld48. I ended up quite pleased with the visual style of it!  
Made with Victor Prudhomme and Ollie Plaatsman.  

<img style="float: middle;" src="../assets/ld48.png" title="ld48">
<br/>  
