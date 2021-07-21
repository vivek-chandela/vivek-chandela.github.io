---
layout: post
title:  "WebXR #5: Your First 3D Model"
date:   2021-07-21 19:55:00 +0530
category: Technical
---
3D models are simply a representation of any surface of an object in three dimensions. There are a host of sites offering 3D models:

- [Sketchfab](http://sketchfab.com/)
- [Turbosquid](http://turbosquid.com/)
- [Clara](https://clara.io/library)

Apart from this, you can also create your 3D models:

- [Blender](http://blender.org/)
- [Tinkercad](https://www.tinkercad.com/)
- [Sketchup](https://www.sketchup.com/)
- [Oculus Medium](https://www.oculus.com/medium/)

Next, we'll see how to find, download and use free models from Sketchfab.
 
Let's go with a [skull](https://sketchfab.com/3d-models/the-anatomy-of-the-human-skull-baf6ac7b781a46218dca2b59dee58817) model. 

You can see a **Download 3D Model** option. After clicking there, it asks for a 3D file format, so download with the **glTF** format.

After extracting the zip folder, you may have two or three files depending on the model:

- **scene.gltf:** It defines the mesh of your 3D model. Mesh gives the model its shape and geometry.

- **textures:** This folder provides the appearance of your model. 

- **scene.bin:** This file contains information to integrate the mesh and textures to give a final look to your 3D model.

<p align="center">
<img src="/technical/assets/images/mesh.png" alt="position" width="400" height="250"/>
</p>

In the above image, (a) is a mesh without textures and (b) is a mesh with textures mapped.

To use this 3D model in your Glitch project, we need to wrap all these files in a single file. The easiest way to do this is by using [GLB Packer](https://glb-packer.glitch.me/). Just drop your files, and you’ll receive a single file **out.glb** as output.

GLB files are a binary version of the GL Transmission Format (glTF) file, which uses JSON (JavaScript Object Notation) encoding. So, supporting data (like textures, shaders, and geometry/animation) is contained in a single file.

We can either upload or drag out.glb into the assets folder of our Glitch project. After it gets uploaded, Glitch will generate a URL for it. You can click on the asset and press the **Copy URL** button.

**Note:** You have used the Glitch assets folder as a CDN to generate a link for your 3D model so that it is ready to be used in the HTML without directly bringing the 3D model into your project.

There are a couple of options to load the 3D model inside your scene:

### 1. Using `<a-gltf-model>` element

```
<a-scene>
<a-gltf-model id="skull" position="0 0 -3" rotation="0 50 0" src="URL for our model"></a-gltf-model>
<a-scene>
```

Here, **id** is a unique identifier for our model.
 
This approach works if the number of 3D models in your project is low. Otherwise, loading many models may result in a lag, especially if the models are significant. Some things will show up while others are still loading, and overall it just makes for a crummy experience for the user. So, this is where method 2 helps.

### 2. Using Asset Management System

You can preload assets so that they will load and cache in the browser as soon as your WebXR site loads, improving your site’s performance and preventing lag as the user loads your site.

```
<a-scene>
 <a-assets>
   <a-asset-item id="skull" position="0 0 -3" src="URL" response-type="arraybuffer"></a-asset-item>
 </a-assets>
 <a-entity gltf-model="#skull"></a-entity>
</a-scene>
```

`<a-assets>` holds all the assets you want to preload.

Each `<a-asset-item>` is pre-loaded when a scene starts, so this approach is better in preventing lag when loading our scenarios.

The `response-type="arraybuffer"` just helps the browser understand the specific kind of model you're throwing at it - a unified glTF file.

**Note:** Array Management System comes in handy for storing multiple types of preloaded assets like images, audio, video, 3D models, and many more.
Preloading assets inside of `<a-assets>` doesn't make the assets play or show up in your scene. It simply preloads them so that they are readily available and stored in the browser. Notice that we are referencing the asset with `id=”skull”` using the # sign before the id name.

You can also download 3D models with pre-built animation into your project. To use the animations, you can use the [animation-mixer component](https://github.com/donmccurdy/aframe-extras/tree/master/src/loaders#animation) from [aframe-extras](https://github.com/donmccurdy/aframe-extras/tree/master/src/loaders#animation).

For this, include a `<script>` tag inside the `<head>` tag of your index.html

```
<head>
// ...
<script src="https://cdn.jsdelivr.net/gh/donmccurdy/aframe-extras@v6.1.0/dist/aframe-extras.min.js"></script>
<head>
```

Now you can use animation-mixer as a component.

`<a-entity gltf-model="#skull" animation-mixer></a-entity>`

Next, we’ll see how relative positioning works and check out a fantastic tool to make our lives easier.

See you in the next one.

<script src="https://utteranc.es/client.js"
        repo="vivek-chandela/vivek-chandela.github.io"
        issue-term="pathname"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>