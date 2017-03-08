---
layout: post
title: Practical Research
categories: [university]
tags: [honours]
description: Updates on the allocated supervisor and research done.
---

Having been allocated our supervisors this week, in my case Matthew Bett, I decided to look more into Unity VR development capabilities, since discovering Unreal 4 already has a VR editor in their engine already - it might be more beneficial for me to create something for Unity and help make me stand out more (even though they have announced their own VR editor is in development). Also using Unity I will be able to make development progress a whole lot quicker since I am more experience in Unity, than I am in Unreal 4. 

With this VR engine/interface in mind, the first thing that is needed is saving/loading of objects, so I started looking into the file I/O for Unity, and found some online help to understand how to read/write to a file using the Unity engine. Using this, I plan to create a base class called Persistent Object, which will be the very base class for all of the objects I will allow the player to create. This will also allow me to later on, build a data structure for storing all of the level objects easily - which will allow me to save to, and allow me to save the values to the file that I will write to.

Over tonight and tomorrow, I will go about creating a set of class diagrams to help structure my classes and help with the subtyping polymorphism that I have in mind.

In order to create shapes in the level, Unity has a handy Game Object function called CreatePrimitive, where you can pass in a primitive type and then transform that primitive as normal. In my mind I have the initial thoughts of a similar UI layout to Tilt Brush, and similar to the Unreal VR editor, where the menus will dock to your hand controllers - these should be able to be dismissed and brought back up with a button on the HUD. Also, if time permits, these should have the option to dock/stick to the user's screen, to save the user from looking down at their hands constantly.

A menu on the left would have buttons on it, where you have different sections, so a section could be for primitives, this section would then be expanded upon in the menu to the left, and to the right, allow the user to edit values of the primitive more precisely. The user should be able to click on a primitive button, and have it spawn at the origin (for example), then it is in the scene for the user to edit and manipulate.