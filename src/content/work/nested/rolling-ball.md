---
title: Rolling Ball | HCI Mini Project
publishDate: 2023-08-10 10:00:00
img: /blog1/miniature.png
img_alt: Roll A Ball
description: |
  Summary of the development process of a simple roll-a-ball game
tags:
  - Development
  - Unity
  - HCI

---

#### Roll a Ball | Developping and Building my first Unity game

In today's blog post, I'll be presenting the development process of an arcade game.

The goal of the game is to gather all the collectibles without touching the walls.

It consist of a top-down view of a ball rolling across an arena. Small yellow floating squares can be collected. Once all 10 cubes have been collected, the player wins.
However, if the player hits any obstacle, he loses.

Check out a short gameplay:

![Demo of the game](/roll-a-ball/Demo_1.gif)

#### Starting the project

I created this project in Unity's 2022.3.9f1 version as it's stable.

![Creation of the project](/roll-a-ball/creation_project.png)

I used the 3D game template.

#### Setup

Before implementing any mechanics to the game, we must create all the assets.

First, I made a basic square arena with walls. It is better to start simple and build more complex levels once every mechanics works properly.

I then created the player object, a ball.

Before starting scripting the movement, it is necessary to add the proper colliders to assets:
- the ball must be assigned a rigidbody collider and a ball collider. The rigidbody is necessary to detect collision and trigger actions.

- the walls and ground need a box collider to prevent the ball from going throught them as well as defining collisions and triggers.

#### Movement Mechanics

Let's implement our first game mechanics: the movement of the ball.

As our 3D game is played in a 2D plane, we only need a Vector2 movement vector for our input.

However, the ball is 3D and thus needs a Vector3 for controls. 

We finally apply our movement inputs to the rigidbody of the ball to make it move.




