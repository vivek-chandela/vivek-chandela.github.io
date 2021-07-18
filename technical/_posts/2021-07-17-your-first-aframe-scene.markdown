---
layout: post
title:  "WebXR #2: Your First Aframe Scene"
date:   2021-07-17 15:29:00 +0530
category: Technical
---
Head over to [Glitch](https://glitch.com/) and create an account. Next, go to `New Project -> hello-webpage`.<br>Congrats on making your very first VR scene on Glitch. 

You can see some files on the left side of your project:

- **index.html** - This is where most of the development takes place. The code you write is what gets rendered on your web page/smartphone.

- **style.css** - A simple CSS file to add styling to your content.
script.js - To add interactivity and make your content dynamic by adding some Javascript.

- **assets** - This is a folder where you can add all your images, audios, videos, 3D objects, and many more which you want to display in your AR/VR scenarios. Glitch creates a CDN for these assets and improves the speed of delivery.

When you click on the project name on the page’s top-left corner, you get a dropdown with the option **Remix Project**. This option allows us to take an existing project and create its clone for our account.

Inside your `index.html` file, add the following lines:

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <!-- import Aframe inside the project -->
    <script src="https://aframe.io/releases/1.0.4/aframe.min.js"></script>
    <title>Hello World!</title>
    <!-- import the webpage's stylesheet -->
    <link rel="stylesheet" href="/style.css">
    <!-- import the webpage's javascript file -->
    <script src="/script.js" defer></script>
  </head> 
  <body>
    <a-scene>
    <a-box color="blue" depth="0.5" height="0.5" width="0.5"></a-box>
    </a-scene>
    <!-- include the Glitch button to show what the webpage is about and
          to make it easier for folks to view source and remix -->
    <div class="glitchButton" style="position:fixed;top:20px;right:20px;"></div>
    <script src="https://button.glitch.me/button.js" defer></script>
  </body>
</html>
```


Add this line to include Aframe inside your project:

`<script src="https://aframe.io/releases/1.0.4/aframe.min.js"></script>`


**Note:** At the time of writing, 1.0.4 is the latest stable version of Aframe. 

You will see a blank screen for now because our box is not in front of the camera. To do that, add a position component to `<a-box>` primitive.

```
<a-scene>
  <a-box color="blue" depth="1" height="1" width="1" position="0 0 -4">
  </a-box>
</a-scene>
```

`<a-scene>` is a placeholder for an Aframe scene that contains all the [entities](https://aframe.io/docs/1.0.0/core/entity.html). You can read more about it [here](https://aframe.io/docs/1.0.0/core/scene.html).

Primitives are `<a-entity>`’s under the hood that:
- Have a semantic name (e.g., <a-box>)
- Have a preset bundle of components with default values
- Map or proxy HTML attributes to component data

Now click on `Show -> In a New Window`. 
You can see a blue box now. Also, there is a VR button on the bottom-right corner. Press that, and kaboom, your first VR scenario is ready !!

**Basics of Position:**

<!-- ![position](/technical/assets/images/position.png) -->
<p align="center">
<img src="/technical/assets/images/position.png" alt="position" width="200" height="200"/>
</p>


To move your asset left/right and top/down, change your x and y coordinates, respectively.

The camera is positioned at (0,0,0) by default, so to view your asset, your z coordinate must be negative (i.e., away from the camera).

**Task #1:** Just play around with the options available in Glitch and try making other primitives like `<a-circle>`, `<a-cone>`, and so on. Also, try setting rotation and scale for your shapes.

Next, we’ll learn about Entity-Component Architecture in Aframe. 
See you in the next one.