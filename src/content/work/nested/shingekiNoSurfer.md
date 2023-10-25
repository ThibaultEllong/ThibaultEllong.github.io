---
title: Unity | Attack On Surfers
publishDate: 2023-10-24 11:39:00
img: /labs/lab2_filtering/minia.png
img_alt: SIFT
description: |
 Course: Augmented & Virtual Reality
tags:
  - Unity
  - Blender
  - Game Design
---
<style>
  pre{
    border-radius: 5px;
    margin: 0 2px;
    background-color: #f2f2f2;
  }
</style>

---

As part of my Augmented & Virtual Reality master's diploma, I had to develop a video game using the game engine Unity, from scratch.
Without any prior knowledge and as a mostly autonomous project, I had to learn by myself most of the advanced scripting and game mechanic techniques used by Unity in order to create a compelling game.

In this blog post, I will go over the creation process of my game: Attack On Surfers

All the code of the game can be read and downloaded [here]().

---

#### Inception

For some proper introduction, I'll start by introducing Attack On Titan:

Attack on Titan is a manga and anime created by Hajime Isayama in 2009. It is set in a medieval city surrounded by gigantic walls. Indeed, the outside of the city is flooded with titans: tall, naked, humanoid creatures whose only endeavour is to eat humans.
The story follows a young soldier called Eren Yaeger that mysteriously obtains the power to turn himself into a titan.
It is a very mature and dark story addressing topics such as death, revenge, remembrance and the unending cycle of hate and violence.

As a huge fan of the Attack On Titan series, I knew right from the start that I wanted to set my game in this universe. I think that it's a visually and thematically interesting world that I've spent a lot of time immersing myself in while watching the anime.

However, I had to come up with an idea for the gameplay. 

I first wanted to recreate the Omni-Dimensional Movement sequences that are so emblematic to the show. The characters are equipped with gas tanks, grappling hooks and long swords that they use to move in any direction and kill Titans.

With one month ahead of myself and no knowledge, I quickly understood that I was getting far ahead of myself and that it would surely lead to a half-finished, buggy game; or even to **nothing at all.**

Thus, I pivoted to a more manageable gameplay that would still be related to the anime.

I thought of an iconic scene in Episode 1, in which the newly formed soldiers take to the streets for their first fight against titans. They dash throught the corridors of this German-inspired city, running on the roofs and flying past the windows.

Using this scene as inspiration, it reminded me of a game I used to play as a teen: Subway Surfer.

What if the player, instead of dodging oncoming trains and running on top of wagons, sprinted on the roofing tiles and avoided titans?

After a few research, I found interesting tutorials and clones of the famous game and it appeared to me that this idea could be done in the given time.

Thus I went to work.

#### Creating the game

I wont go over all the technical details and the whole creation process as I didn't document it all.
However, I'll describe the main mechanics, their implementation and the challenges I faced and solved.

The game had to have 4 main components:

- A running player followed by a camera
- A random generated environment
- Obstacles and collectibles
- An appealing gameplay

##### Running Player

To create my character, I went on Adobe's ![Mixamo website](https://www.mixamo.com/#/). This free library provides animations and 3D models as well as an automatic rigging tool.
I selected this archer's model as it fitted the aesthetic I was going for:
[Image archer]()
I didn't think too much about its appearance as I just needed it for the programming phase.

I then wrote a script for the basic motion (jumping, running, sliding, changing lane) and animated it accordingly.

##### Random Environments

Subway Surfer uses randomly generated environments to create its levels ([about the difference between random and procedural environments](https://www.gamedeveloper.com/design/procedural-vs-randomly-generated-content-in-game-design)). This technique allows for infinite replayability as every restart is a new level.





