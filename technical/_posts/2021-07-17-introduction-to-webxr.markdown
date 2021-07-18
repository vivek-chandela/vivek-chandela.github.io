---
layout: post
title:  "WebXR #1: Introduction to WebXR"
date:   2021-07-17 15:28:00 +0530
category: Technical
---
**What is WebXR?**

In simple terms, WebXR allows us to deliver AR or VR experiences using plain HTML, CSS, and JS.

**AR/VR must require a lot of prerequisites, right?**

No worries. You only need the knowledge of HTML, CSS, and some plain Javascript to build AR/VR scenarios. You just need an online editor and your smartphone. Sounds Interesting?

Let us begin the journey.

We will be using Aframe, a javascript framework, to build XR scenarios. Let’s go over some of its features:

- **Easy to use:** Nothing to install, no build steps.

- **Entity-Component Architecture:** This is the core of Aframe borrowed from three.js as Aframe is a javascript framework built on top of three.js. Now, what are entities and components?

>Aframe uses components to implement all the logic like appearance, behavior, and functionality. Components are attached to container objects called entities. Aframe not only has its own set of core components and publicly available third-party components, but it also allows us to write custom components.

- **Cross-Platform:** It works on standard desktops and smartphones even if you don’t have access to controllers like Vive, Rift, GearVR, etc.

- **Performance and Scalability:** The most interactive and large-scale WebVR applications have been made in A-Frame, running smoothly at 90fps.

- **Visual Inspector:** A-Frame provides a handy built-in [visual 3D inspector](https://aframe.io/docs/1.0.0/introduction/visual-inspector-and-dev-tools.html). Open up any A-Frame scene, hit `<ctrl> + <alt> + i`, and fly around to peek under the hood!

We’ll get to know more about each part of Aframe when we play around a bit more with it in future blogs.

For development, we’ll use [Glitch](https://glitch.com/) -- an online editor that gives you a way to write code and hosts the changes in real-time online.

There are no additional specifications for VR, but for AR, you will need [ARCore compatible devices](https://developers.google.com/ar/devices) and Chrome 79 or newer. At the time of writing this post, you need to enable the WebXR Incubations module in `chrome://flags`. Also, make sure to serve your page over HTTPS.

Next, we’ll learn about creating a VR scene on Glitch. 
See you in the next one.

<script src="https://utteranc.es/client.js"
        repo="vivek-chandela/vivek-chandela.github.io"
        issue-term="pathname"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>