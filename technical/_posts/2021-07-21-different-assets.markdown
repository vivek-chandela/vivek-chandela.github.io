---
layout: post
title:  "WebXR #7: Say Hi to Different Assets"
date:   2021-07-21 21:22:00 +0530
category: Technical
---
In this blog, we’ll see how to add different assets such as:
- Image
- Text
- Photosphere (360° image)
- Audio
- Video
- Videosphere (360° video)

This list is not exhaustive, but it will provide you with a nice headstart for adding other assets as well.

### 1. Image

Drag an image file (.jpg or .png) into the assets folder of your Glitch project and copy its URL.

This URL can be used in different primitives based on your use case like `<a-image>`, `<a-sky>`, `<a-plane>` and so on.

```
<a-scene>
 <a-assets>
   <img id="i1" src=”URL1">
   <img id="i2" src=”URL2">
 </a-assets>
 <a-image src="#i1"></a-image>
 <a-sky src="#i2"></a-sky>
</a-scene>
```

`<a-image>`: The image primitive shows an image on a flat plane.

`<a-sky>`: The sky primitive adds a background color or 360° image to a scene. A sky is a giant sphere with a color or texture mapped to the inside.

`<a-plane>`: The plane primitive creates flat surfaces using the geometry component with the type set to plane.

You can read more in the primitives section of Aframe Documentation.

### 2. Text

You can add text with the `<a-text>` element.

```
<a-text value="Aframe Blogs" position="-2 2 -4" rotation="0 10 0" width="5" color="red" ></a-text>
```

### 3. Photosphere

A photosphere is simply an image captured in all possible viewing directions. They usually act as a background for AR/VR scenes. 

We’ll add an equirectangular photosphere to our project using [flickr](http://flickr.com/groups/equirectangular/).

Like an image, drag the photosphere file (.jpg or .png) into the assets folder of your Glitch project and copy its URL.

To make the photosphere the background of our scene, we can add an `<a-sky>` element to our scene, and we give it a **src** attribute. For the value of the src attribute, we use the URL of our photosphere:

`<a-sky src="URL"></a-sky>`

**Note:** You can preload the photosphere using Asset Management System for better performance. To read more about Asset Management System check my previous post [here](https://vivek-chandela.github.io/technical/2021/07/21/first-3D-model.html).

### 4. Audio, Video, and Videospheres

I prefer to use the following formats while dragging audios/videos to my assets folder:

- **audio:** use .mp3 or .wav files
- **video:** use .mp4 video
- **360 video:** use equirectangular .mp4

```
<a-scene>
 <a-assets>
   <audio id="a1" src="URL1" preload="auto" crossorigin="anonymous">
   </audio>
   <video id="v1" autoplay loop="true" src="URL2" crossorigin="anonymous">
   </video>
   <video id="vs1" autoplay loop="true" src="URL3" crossorigin="anonymous">
   </video>
 </a-assets>
 <a-entity geometry="primitive: plane" material="color: blue"
         position="-10 0 0" sound="src: #a1; autoplay: true">
 </a-entity>
 <a-video src="#v1" width="16" height="9" position="0 0 -20"></a-video>
 <a-videosphere position="0 1.8 0" radius="0.7" src="#vs1" videosphereexpand>
 </a-videosphere>
</a-scene>
```

You use an `<audio>` element for loading an audio asset and a `<video>` element for loading a video asset inside the asset management system.

We can play audio by using the sound component inside an `<a-entity>`. It is a core component of Aframe that defines the entity as a source of sound or audio. Set the src property of the sound component to be the hash sign followed by the id of the preloaded audio asset in `<a-assets>`.

To put a video in your scene, you can use the `<a-video>` entity. Set the src attribute to be the hash sign followed by the id of the preloaded audio asset in `<a-assets>`.

To put a videosphere in your scene, you can use the `<a-videosphere>` entity. Set the src attribute to be the hash sign followed by the id of the preloaded audio asset in `<a-assets>`.

In the next blog, we’ll see how to add animations to your project using custom components. 

See you in the next one.


<script src="https://utteranc.es/client.js"
        repo="vivek-chandela/vivek-chandela.github.io"
        issue-term="pathname"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>