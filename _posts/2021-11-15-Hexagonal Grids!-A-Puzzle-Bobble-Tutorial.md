---
layout: post
title: " Puzzle Bobble: Scoring points (Ball Chains) "
categories:
author:
- Javier Dieguez
meta: "Springfield"
---
## Preface
This is a rewrite of some dev stuff I wrote in blogspot around 2018 for my homebrew GBA game.

## Intro/Preamble
So I have finally gotten through my gba game. Its a Puzzle Bobble clone with a spooky/haunted style I made on Notepad++, using C as well as ARM assembly. It follows a standard C structured code architecture with things such as manual interface classes (Given C doesn't actually support interfaces)
[Check it out!](https://github.com/JavierDega/Gba-Puzzle-Bobble)
This project started as a university hand-in; I really wanted to get an entire game finished for my deadline but unfortunately I missed a lot of major Puzzle Bobble features before I had to wrap it up (Even then I handed it in a month later , getting a capped mark; But hey, I passed) One major feature is the Hex Grid, which I will try and simplify on this entry!

## What is a Hex Grid?
Well...something like what this crappy drawing is trying to illustrate.
<img style="float: middle;" src="_assets/HexGrid.png" alt="hexgrid" title="hexgrid">
