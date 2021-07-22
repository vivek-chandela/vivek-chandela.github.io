---
layout: post
title:  "WebXR #8: Adding Animations"
date:   2021-07-22 09:12:00 +0530
category: Technical
---
In my blog titled [Your First 3D Model](https://vivek-chandela.github.io/technical/2021/07/21/first-3D-model.html), we saw how to include the [animation-mixer](https://github.com/donmccurdy/aframe-extras/tree/master/src/loaders#animation) component into our project. The animation-mixer component allows us to play an animation within any 3D model.

Aframe also provides us with the option of building custom animations using the [animation](https://aframe.io/docs/1.0.0/components/animation.html) component. We can bring this component using a script inside our head element:

`<script src="https://unpkg.com/aframe-animation-component@^5.1.2/dist/aframe-animation-component.min.js"></script>`

Unlike animation-mixer, the animation component requires configuration.
E.g.,

```
<a-box position="-1 1 -4.5" rotation="0 45 0" color="#4CC3D9" depth=".2" width="2" animation="property: position; to: -1 1.5 -4.5 dur: 2000 loop: 3"></a-box>
```

We have used four properties in our animation component:

- **property:** It tells the component that we want to animate the position of our box.

- **to:** Set where the animation will animate.

- **dur:** How long the animation should last.

- **loop:** How many times the animation should repeat.

**Task #1:** Play around with other properties and apply animation to the rotation and color of our box.

Next, we’ll see how to animate the camera of our project. The camera depicts the viewer’s perspective. When we create any scene with Aframe, a camera gets automatically created. 

The camera has two components:

- wasd-controls
- look-controls

These components come included with Aframe, so we don’t need to import them into our project. They help us to move around and look around.

To animate the camera, we need to see it in our HTML. For this, we can use an `<a-entity>` element.

Let’s see how we can give a flyover effect to our camera:

`<a-entity position="0 4 40" camera wasd-controls look-controls animation="property:position; to: 0 4 0; dur: 10000"></a-entity>`

To see more examples of Aframe and Three.js, check out the fantastic work of [Lee Stemkoski](https://github.com/stemkoski/A-Frame-Examples) on Github.

To give you a little taste of the possibilities of the animation component, I have included a GIF below.

<p align="center">
<img src="/technical/assets/images/animation.gif" alt="position" width="700" height="400"/>
</p>

We can notice four types of animations above: 

- The flyover effect of the camera.
- The blue and red balls are moving towards the camera.
- The two rotating rectangles.
- The square with fade-out animation.

In the next blog, we’ll learn about Hit Testing and DOM Overlay. We’ll also get to know how to incorporate them into our projects to make them more interactive. 

See you in the next one.


<script src="https://utteranc.es/client.js"
        repo="vivek-chandela/vivek-chandela.github.io"
        issue-term="pathname"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>