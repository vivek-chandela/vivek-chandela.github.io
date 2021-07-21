---
layout: post
title:  "WebXR #6: Relatives and Inspector"
date:   2021-07-21 20:22:00 +0530
category: Technical
---
Take a look at the following code:

```
<a-scene>
       <a-box position="-2 1 -3" color="green">
           <a-box position="0 1 -3" color="red"></a-box>
           <a-box position="2 1 -3" color="red"></a-box>
       </a-box>       
</a-scene>
```

We know that `<a-scene>` is the parent element of all entities.
Similarly, we can argue that the green box is the parent of the two red boxes. The red boxes are siblings of each other and are children of the green box.

### Relative Position

>The coordinates of a parent entity act as the origin point for all of its children entities

So, instead of using the scene’s origin, which is (0,0,0) by default, the child entity will use coordinates of its parent entity as the origin.

Let’s take an example: 

In the code above, the position of the 1st red box is “0 1 -3”. This position is known as the **local position** as it is the relative position of an entity w.r.t the coordinates of its parent entity. 

The parent green box has position “-2 1 -3”.
So, the actual position of the 1st red box is “-2+0 1+1 -3-3” = “-2 2 -6”. This exact position is known as the **global position**. It is the actual position of an entity w.r.t to the scene.

**Note:** local position and global position of the green box are the same because it is a child of the `<a-scene>` element. By default, coordinates of `<a-scene>` and camera are (0,0,0) which is the global origin. We can always change the coordinates of `<a-scene>` and camera as per requirements, but we’ll skip that for now.

**Task #1:** Find the local and global coordinates of the 2nd red box. I’ll be providing the answers at the end of this section. 

Suppose we have many nested entities; making changes to a single entity can be pretty cumbersome. To make this process smoother, we can use the [Aframe Inspector](https://aframe.io/docs/1.0.0/introduction/visual-inspector-and-dev-tools.html).

To use it, open your immersive website using `Show -> In a New Window` and press  `<ctrl> + <alt> + i`

<p align="center">
<img src="/technical/assets/images/aframe-inspector.png" alt="position" width="700" height="400"/>
</p>

Aframe Inspector has an entity list on the left. Any parent entity has a little arrow next to it that you can click to expand out and see all of its children. If you move/rotate/scale the parent entity, the children entities also move/rotate/scale.

**Task #2:** Play around with the Aframe Inspector. It is a convenient tool to have. Create your own custom nested entities and try moving/rotating/scaling the parent entity.

**Solution for Task #1:** local position = “2 1 -3 “, global position = “0 2 -6“ 

Next, we’ll learn how to add different assets to our project. 

See you in the next one.

<script src="https://utteranc.es/client.js"
        repo="vivek-chandela/vivek-chandela.github.io"
        issue-term="pathname"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>