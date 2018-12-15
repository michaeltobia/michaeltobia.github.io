---
layout: project
title: Mechatronics - Path Follower
date: December 15, 2018
image: https://michaeltobia.github.io/public/images/path_follower_project.jpg
permalink: "/path_follow.html"
---

This project was completed for my Advanced Mechatronic course at Northwestern.
In a way, the entire course centered around designing this path following vehicle,
but the ultimate goal was for the vehicle to follow a rainbow colored path well
enough to complete an entire circuit.

This course was incredibly engaging. The focus on mechatronics meant the path
following vehicle was designed from scratch right down to the circuit board,
below:

![My pic32 microcontroller board](https://michaeltobia.github.io/public/images/pic32.jpg)

This microcontroller, a PIC32 programmed in C, was used to control the motors on the path
following vehicle. An android phone calculated the desired control messages by using
a computer vision algorithm to detect the line. These messages were sent via USB
OTG connection to the PIC32. The following gif shows the path following vehicle
in its later stages of testing.

![Path following robot behaving badly](https://michaeltobia.github.io/public/images/path_follow_demo.gif)
