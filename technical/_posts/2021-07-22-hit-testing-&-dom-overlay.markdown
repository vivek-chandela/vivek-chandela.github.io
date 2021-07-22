---
layout: post
title:  "WebXR #9: Hit Testing and DOM Overlay"
date:   2021-07-22 10:17:00 +0530
category: Technical
---
We’ll first go over some basics of Hit Testing and DOM Overlay. Finally, we’ll see an example that encompasses both of them.

### Hit Testing

>Hit Testing is a WebXR Device API that gives us a means of placing virtual objects in a real-world camera view. 

You can check out a demo of hit testing [here](https://github.com/stspanho/aframe-hit-test). It is well-documented with proper comments. You can test this with an Android phone and a Chrome (Beta) v81+ browser.

<p align="center">
<img src="/technical/assets/images/hit-testing.gif" alt="position" width="700" height="400"/>
</p>

In the demo, you can see a blue circle that moves along with the device. This circle is the intersection between an imaginary line from your device to the point in the environment. As it finds intersection points, it appears to snap to surfaces such as floors, tabletops, and walls because hit testing provides the position and orientation of the intersection point. This circle is known as the **reticle**.

If we tap the screen, the dinosaur appears on the surface at the reticle location, oriented vertically to the surface at the reticle point, regardless of where you tapped the screen.

We can use the ar-hit-test component alongside the demo with the `<a-entity>` representing our reticle to bring hit-testing into our project.

`<a-entity gltf-model="#reticle" scale="0.8 0.8 0.8" position="0 0 -2" ar-hit-test></a-entity>`

### DOM Overlay

Suppose we need an exit button to come out of our AR session. Now, a button is a 2D element that we need to render on our scene. So, the button here is an example of interactive 2D web content.

>DOM Overlay allows us to show interactive 2D web content during an immersive WebXR session.

You can find the source code for an exit button using DOM Overlay [here](https://github.com/aframevr/aframe/blob/master/examples/boilerplate/webxr-dom-overlay/index.html).

Coming to the example, I recently created a Glitch project for a [heart model](https://glitch.com/edit/#!/heart-model?path=index.html%3A373%3A20). 

Open the link in your smartphone and press `Show → In a New Window`.You will see something like this:

<p align="center">
<img src="/technical/assets/images/heart-model.png" alt="position" width="250" height="400"/>
</p>

Now press the `AR` on the bottom-right corner:

<p align="center">
<img src="/technical/assets/images/heart-AR.png" alt="position" width="250" height="400"/>
</p>

You can see my room in the background and the model with the reticle just below it. Also, you can see the buttons for our music player and a button for exiting the AR session.

It encompasses all the learnings of this entire blog series. It has multiple features like:

- Hit Testing for moving the heart model. You can see the reticle at the bottom of our heart model in the image to the right.

- DOM Overlay for displaying various buttons. You can see the five buttons at the bottom of our heart model in the image to the right.

- Custom components for creating a music player, hiding environment in AR mode, adding shadows in AR mode, etc.

- The music player has the options of play, pause, and switch to next or previous songs. As you switch the songs, the rotation of the heart model also changes by 90 degrees each time.

<script src="https://utteranc.es/client.js"
        repo="vivek-chandela/vivek-chandela.github.io"
        issue-term="pathname"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>