---
title: HCI Research, the Ultimate Display & Interaction Paradigms
publishDate: 2023-09-26 11:40:00
img: /blog3/minia.png
img_alt: Good design
description: |
  Homework 2: HCI Research, the Ultimate Display & Paradigms
tags:
  - Design
  - HCI
  - Research
---

This blog post is part of a series of assignment for the Human-Computer Interaction course at Institut Polytechnique de Paris.

I will first present a **research paper exploring the future of HCI and its combination with AI**.

I will then present the concept of **the Ultimate Display by Ivan Sutherland** and its impact on HCI.

Finally, I will discuss about the different **input devices and the interaction paradigms** they induce.

##### Paper: Development of an Eye Tracking-Based Human-Computer Interface for Real-Time Applications
**by Radu Gabriel Bozomitu, Alexandru Păsărică, Daniela Tărniceriu and Cristian Rotariu**

Physically-disabled people, especially those that can't use their upper limbs or hand, have a hard time interacting with computers. Our modern interfaces are focused on hand and finger movements.

In this paper, the researchers investigate the use of pupil detection and eye tracking to create a new interface for disabled people.

The authors evaluated 6 methods for pupil detection by measuring the detection rate. 

**Introduction:**

The introduction of the paper highlights the importance of eye-tracking technology in human-computer interaction and its potential for real-time applications. The authors discuss the challenges associated with developing an accurate and reliable eye-tracking system, including the need for robust pupil detection algorithms and the impact of various factors such as lighting conditions and user ability.

**Methods and Materials:**

The paper goes on to describe the video oculography technique used in the study, which is based on video analysis of eyeball movement using a video camera in the visible or infrared spectrum. The authors explain the advantages and disadvantages of infrared eye image capturing and describe the dark-pupil technique used in their study. The section also provides details on the hardware system for VOG signal acquisition, including the head-mounted eye tracking interface used in the study and the infrared video camera used for eye pupil image acquisition and processing. 

**Conclusion:**

The conclusion adresses the results for the eye detection tasks as well as the eye-controlled interface.

Firstly, the authors evaluated six pupil center detection techniques for accuracy and determined the detection rate within a circular target area. They found that the algorithm based on circular Hough transform was the best for real-time applications. Secondly, the authors presented experimental results for cursor controllability and stability on the user screen. They found that the proposed eye tracking interface provided stable cursor control with an average error of less than 10 pixels. Finally, the authors presented an application of the system, a low-cost eye typing application using a virtual keyboard. The results showed that the proposed system achieved a typing speed of 20.74 words per minute with an accuracy of 96.7%.

You can read the paper [here](https://www.mdpi.com/1424-8220/19/16/3630).

---

##### The Ultimate Display

Let's take interest into a paper written by a HCI rockstar, Ivan Sutherland. Ivan Sutherland is considered as a founding father of HCI and an Internet pioneer. He was awarded a Turing prize for inventing SketchPad, the ancestor of CAD softwares.

His paper, The Ultimate Display, is an essay about what the end-goal of display technologies is while reviewing the (then) current state of the art.

Sutherland approaches three main topics:

- Computer displays as a window: The author describes how computer displays can show mathematical and physical worlds that are not accessible to human senses, such as negative masses, non-projective transformations, or constraints.

- Types and functions of displays: The author discusses various types of displays, such as visual, audio, kinesthetic, and force feedback, and how they can create and manipulate virtual objects that defy the ordinary rules of reality. He also explains how different input devices, such as keyboards, light pens, joysticks, or eye trackers, can be used to interact with the computer and the displayed objects.

- Ultimate display as a wonderland: The author envisions the ultimate display as a room where the computer can control the existence of matter, creating a wonderland for human exploration and learning. He argues that such a display would enable us to gain familiarity with concepts that have no visual representation in the physical world.

---

##### The Power Glove: A Failed Look into the Future

In 1989, a team at Abrams/Gentile Technologies research lab and led by Grant Goddard & Sam Davis delivered a then to be thought revolutionnary device. 

The Power Glove is a glove controller, equipped with a keyboard, remote and hand controls. The user could use his fingers as independant inputs to trigger actions in the game, such as shooting by lifting his index.
The device came at a cost of 100$ a piece.
To be used, the player had to set 3 markers on his TV screen.

Unfortunately, the Power Glove was a commercial flop due to the few compatible games and cost of the device. 

However, Goddard & Davis might have only been a few decades too early, as many draw a parallel between their invention and a later controller technology that faced a much more fruitful destiny: the Wii.

Indeed, many similarities can be found between the two controllers:

- Motion Sensors: The remote can be used by spatial movements of the controller.
- Ability to Point the Screen: One of the most prominent feature of the Wii is the ability to control the cursor by simply pointing to where we want to click.
- One Handed controls: Both controllers can be used using a single hand.
- Two Hand Controls: However, when held horizontally, both controllers can be used as a single remote.

So beside the now obvious similarities, what could explain the difference in success that both technologies faced ?

My analysis, even though I never used the Power Glove, is that **form factor** is a prominent cause for its failure.
Handing a TV Remote-sized controller is much more intuitive and practical than slipping on a futuristic looking glove.

Moreover, the **technical maturity** of the public might not have been developped enough for them to use such a device. We saw this more recently with the Google Glasses. Far from a bad product, people couldn't picture themslves wearing such a odd looking pair of glasses on their head.

The takeaway is that one must always think about the user when creating a device:
- Will people **want** to buy and use it ?
- How far ahead is it from existing technologies ?
- Can't I make something less innovative but more wanted ?

It is important to look at the failures from the past to not reproduce them.

---

#### Bibliography

- [The Ultimate Display](https://www.semanticscholar.org/paper/The-Ultimate-Display-Sutherland/dce55f83dd425c68e5d1c1714dd0c8bbb43e54d9)
- [Wikipedia's Power Glove page](https://fr.wikipedia.org/wiki/Power_Glove)
- [Development of an Eye Tracking-Based Human-Computer Interface for Real-Time Applications](https://www.mdpi.com/1424-8220/19/16/3630).

---

Thanks for reading !