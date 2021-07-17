---
layout: post
title:  "Introduction to WebXR"
date:   2021-07-17 15:28:00 +0530
categories: jekyll update
---
What is WebXR?
In simple terms, WebXR allows us to deliver AR or VR experiences using plain HTML, CSS and JS.

AR/VR must require a lot of prerequisites right?
No worries. You only need the knowledge of HTML, CSS and some plain Javascript to build AR/VR scenarios. Sounds Interesting ?

Developing AR/VR scenarios must surely require a lot of tools and hardware. How can I arrange those?
You just need an online editor and your smartphone !!!

Let us begin the journey.

We will be using Aframe, a javascript framework to build XR scenarios. Let’s go over some of its features:
Easy to use: Nothing to install, no build steps.
Entity-Component Architecture: This is the core of Aframe borrowed from three.js as Aframe itself is a javascript framework built on top of three.js. Now what are entities and components?
To briefly answer this question, entities are container objects into which components can be attached. All logic like appearance, behaviour and functionality is implemented using components. Aframe not only has its own set of core components but also has large publicly available third-party components or allows us to write our own custom components.
Cross-Platform: It works on standard desktop and smartphones even if you don’t have access to controllers like Vive, Rift, GearVR etc.
Performance and Scalability:  The most interactive and large scale WebVR applications have been done in A-Frame running smoothly at 90fps.
Visual Inspector: A-Frame provides a handy built-in visual 3D inspector. Open up any A-Frame scene, hit <ctrl> + <alt> + i, and fly around to peek under the hood!

We’ll get to know more about each individual part of Aframe when we play around a bit more with it in the future blogs.

Well Vivek, this is fine but what about the development part?
For development we’ll use Glitch. Glitch is an online editor which not only gives you a way to write code but also hosts the changes in real time online, so that you can open and view your changes in the desktop browser or your smartphone immediately !!

There are no additional specifications for VR but for AR you will need ARCore compatible devices and Chrome 79 or newer. At the time of writing, you need to enable the WebXR Incubations module in chrome://flags and make sure your page is served over https.

So let’s rock and roll.
