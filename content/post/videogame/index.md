+++
author = "Olivier Boisvert"
title = "Video game"
date = "2022-01-07"
description = "Video game prototype programation"
tags = [
    "video game",
 
]
categories = [
    "system",
    
]
series = ["Themes Guide"]
aliases = ["migrate-from-jekyl"]
image = "/img/back_game_1.png"
+++


## Project Description

This project is a 2D video game developed entirely in Python using the Pygame library. The game engine was designed from scratch, without the use of any existing game engine. The project's objective was to develop and structure all the fundamental systems of a 2D game directly within the code, in order to master the basic principles of video game programming.

The game features a player-controlled character who explores different maps, fights enemies and bosses, and interacts with various elements of the environment such as chests and items. The game world is constructed from overlapping matrices representing the state of each pixel or cell on the map. These matrices are used to manage several aspects of the game, including:

-the terrain and obstacle structure
-collision zones
-the position of interactive objects
-the presence of enemies or dynamic elements

Each layer of the map corresponds to a specific matrix, allowing for the overlaying of multiple levels of information (scenery, objects, collisions, entities) while maintaining a logical and flexible structure.

The game engine also manages a dynamic camera system that follows the character and displays only the relevant portion of the map on the screen. This approach allows for the creation of levels larger than the visible area while maintaining good performance.

The player can use various weapons, such as a sword for melee attacks or a bow for firing arrows. Projectiles have their own movement logic and use a collision detection system with enemies and bosses.
Enemies have autonomous behaviors, and some can also attack the player with their own projectiles. The game also includes bosses with multiple vulnerable areas, such as the eyes or mouth, which must be targeted at specific moments during animations to inflict damage. This mechanic adds a strategic dimension to combat.

The environment contains several types of elements:

-static objects that make up the scenery
-dynamic objects with animations or movements
-interactive chests that can contain rewards
-visual effects and elements placed in the foreground or background to enrich the scene

From a technical standpoint, this project represents the design of a complete 2D mini-game engine, including sprite management, animations, data matrices, collision detection, projectile handling, camera control, and gameplay logic. The project highlights the ability to design a complex software architecture and develop a complete interactive system from scratch.



# The intro, open a chest, push bloc, animation, kill an enemy:
{{< video label="this is a label" mp4="/img/vg8.mov" >}}
# Menu, select a different sword
{{< video label="this is a label" mp4="/img/vg1.mov" >}}
# The bow

{{< video label="this is a label" mp4="/img/vg2.mov" >}}
# The parasailing
{{< video label="this is a label" mp4="/img/vg3.mov" >}}
# Climbing
{{< video label="this is a label" mp4="/img/vg4.mov" >}}
# Menu
{{< video label="this is a label" mp4="/img/vg5.mov" >}}
# The boss, you need to kill the 3 eyes with the bow to kill the mouth with a sword
{{< video label="this is a label" mp4="/img/vg6.mov" >}}
# Getting exhausted and drinking potions, life, breathing. 
{{< video label="this is a label" mp4="/img/vg7.mov" >}}