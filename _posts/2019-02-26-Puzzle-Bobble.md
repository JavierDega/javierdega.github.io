---
layout: post
title: "Puzzle Bobble: Scoring points (Ball Chains) "
categories:
author:
- Javier Dieguez
meta: "Springfield"
---

## Intro  

I know it's been a while but I've been busy getting on with my final year, I need to make sure I can get a job after this, or there will be no point to all this devlogs!
Here's the second tutorial related to my GBA Puzzle Bobble clone, and I will discuss arguably the hardest feature to develop; Coming up with a solution to detect ball groups of three or more, that share the same colour value. Not only that, but its sister algorithm; One to detect the balls that are left hanging, ran only if we have just deleted three(Or more) balls and scored some points.

I will discuss the dangers of recursion and the benefits of storing your data in an intuitive manner, as well as coming up with your own structs to match your logic.

Lets get to it!

## Ball Cluster Detection:  

So the easy part of this routine, is to identify whether we have scored a chain of 3 or more balls of the same colour. Just for your information, we're working from a hex grid, which I have [covered before](https://javierdega.blogspot.com/2018/09/hexagonal-grids-puzzle-bobble-tutorial.html).
This basically means that, depending on whether we're on an even or uneven row, we will have two extra neighbours, which would correspond to the left or right diagonals in a quadratic grid. Making up a total of 6.

Regardless of whether we analyse the array or use recursion to find ball clusters, we will need each ball to hold some extra information. An unsigned integer representing how many neighbours of the same colour they currently have (m_chain in my struct), and a [Graph Edge](https://mathworld.wolfram.com/GraphEdge.html)-like structure, which really is just a set of booleans defining which neighbours we have already checked against.  

<img style="float: middle;" src="../../../assets/devlogStaticBallCodeStr.png" alt="staticball" title="staticball">
<br/>

Now for this, the 'array analysis' approach would be looping through the entire grid every time we shoot a ball and it collides with a static ball, or the 'ceiling' of the play area. This might be redundant given that a newly added ball can only pop balls in its neighbour area.  

So in order to loop through arbitrary array members, following a set of rules, [recursion](https://en.wikipedia.org/wiki/Recursion_(computer_science)) is our best friend. In this context its simply about having a function that can recall itself, given certain conditions.When defining those conditions make sure they never allow the function to go into an infinite loop, since we could easily get stack overflow errors; If you check [GameScene.h](https://github.com/JavierDega/Gba-Puzzle-Bobble/blob/master/Final/source/scene/GameScene.h) on my repo you will see every recursive function has the suffix 'Recursive' on its definition, to make sure I avoid using them when its not necessary.  
In our case we will have a function that operates on one specific ball, and is able to recall itself with different arguments (col, row) specifying the next ball to analyse. This ball will use a set of booleans to identify which orientation has already been checked against, so we can finalize the recursive call ; once we have checked against all colliding, potentially same colour balls.  

This is where our ClusterBoundsStr comes in.  

<img style="float: middle;" src="../../../assets/devlogClusterBounds.png" alt="clusterBounds" title="clusterBounds">
<br/>

tr,br,tl, blcheck (top right, bottom right,..) represent the extra diagonal neighbours in the grid. And here's our function:  

<img style="float: middle;" src="../../../assets/devlogFindClusters.png" alt="clusterBounds" title="clusterBounds">
<br/>

Pseudocode goes something like this: 


```
for ball at [row][col]
{
    for (Relevant neighbours on the grid, depending on whether row is odd or even)

    {

         if this position in the grid (2d array) is occupied by a ball of same colour

         {

          increase chain counter for both balls.

          negate positional booleans, so we don't recheck against this relative position

          CallItSelf([newRow][newCol])

         }

    }
}
```

Now how you go about deleting them is up to you. But after this I run a pass on the entire grid looking for a ball with a chain value of two or more (= three or more ball chain). If i do find one that's when I use recursion again, in a simple function that loops through the target ball, using its positional booleans to delete its neighbours. This leaves me with a clean grid and no leftover boolean checks.
There's other implications when working with GBA like reorganizing the Object Attribute Memory
after instance deletion but they're not the topic of this devlog.  

<img style="float: middle;" src="../../../assets/devlogClusterAnalysis2.png" alt="clusterBounds" title="clusterBounds">
<br/>

Do not take my pictures very seriously, I've made them through development and they're more of a mental guidance of the ideas I had at the time. Onto the last part!  

## Detecting unsupported balls:  

One of the things that makes this game slightly more frenetic, is the fact that all bubbles must be consequently attached to the game's ceiling.
This one took way longer than the first. It's not that there's one specific solution, but it's hard to land onto one that aligns neatly with the way the grid is stored.

One of my initial approaches was a recursive function called on all ceiling top balls, which spreads an isHanging boolean throughout all the balls that are neighbours, and occupied  (Note we don't care about colours here). You could land on a solution there. But I feel like in practice, due to ceiling rows usually being full, and there not being many separate branches in a grid, you would probably cover most of it after running the first ceiling ball (You would obviously finish the loop at this point, since further balls already have the isHanging value), it just doesn't seem very clean.  

<img style="float: middle;" src="../../../assets/devlogHangingBallAlgorithmAnalysis.png" alt="
A deep analysis into the array looping approach.
" title="
A deep analysis into the array looping approach.
">
<br/>  

 My preferred solution is quite simple, and a blend of a for loop and recursion. If you read the picture (Congrats) you will have guessed that simply looping through the array is not a smart solution, given we'd have to loop in all four possible direction combinations (up to down, left to right,....), to find balls attached to others , in different orders. Also, in a big enough grid, spiral patterns formed by balls would mean not even this is enough.
A simple solution is to first set the ceiling bubbles as supported. Then run a loop once, in your preferred order. Now, in this loop, whenever you find a ball which is supported to a previous one, you start a recursive call that spreads this boolean value to all neighbours (In every direction, avoiding the problem with ordering). By the time you finished this loop all neighboring balls to a supported one, should have been identifying. You can now delete the rest of the balls.

These have basically been the two hardest problems I have tackled throughout development, related to gameplay behaviour. It sits on my mind the idea of writing a blog about GBA rotations, with the rotated, aiming arrow in the game as an example, however this will be the last devlog on my Puzzle Bobble clone, which I finished now half a year ago.

I will probably be reiterating on certain bits of this log over the next few days, as it seems to get a bit hard to follow near the end. I am also thinking of adding a quick, survival mode, where instead of the ceiling dropping you get a new row of random balls, which would make the game playable for longer term.

I hope you took something out of this!  
Kind Regards  
Javier