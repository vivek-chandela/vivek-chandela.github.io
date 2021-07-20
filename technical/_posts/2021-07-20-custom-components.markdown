---
layout: post
title:  "WebXR #4: Registering Custom Components"
date:   2021-07-20 11:52:00 +0530
category: Technical
---
There are two ways to add custom components to your project:

### 1. Create a new file foo.js

```	
AFRAME.registerComponent('foo', {
 schema: {
   bar: {type: 'number'},
   baz: {type: 'string'}
 },

 init: function () {
   // Do something when the component is first attached.
 },

 update: function () {
   // Do something when the component's data is updated.
 },

 remove: function () {
   // Do something when the component or its entity is detached.
 },

 tick: function (time, timeDelta) {
   // Do something on every scene tick or frame.
 }
});
```

The entity-component framework gives us the ability to write a JavaScript module and abstract it through HTML. Once the component is registered, we can declaratively plug this module of code into an entity via an HTML attribute.

To use this component, add a `<script>` tag inside the `<head>` tag:

`<script src="foo-component.js"></script>`


### 2. Register the component inside index.html 

Using this, you can avoid importing a JavaScript file, but this approach reduces code readability.

```
<html>
 <head>
   <script src="https://aframe.io/releases/1.0.4/aframe.min.js"></script>
 </head>
 <body>
   <script>
     // inline before the <a-scene>.
     AFRAME.registerComponent('foo', {
       // ...
     });
   </script>

   <a-scene>
     <a-entity foo="bar: 5; baz: bazValue"></a-entity>
   </a-scene>
 </body>
</html>
```

So, **foo** is the name of the component we just registered, and the data contains **bar** and **baz** properties. Now, we can add this component inside `<a-scene>` to use it in our code.

```
<a-scene>
<a-entity foo="bar: 5; baz: bazValue"></a-entity>
</a-scene>
```

This post is just a preview of how to write a basic component. We’ll see it in more detail later. Meanwhile, you can read more about it [here](https://aframe.io/docs/1.0.0/introduction/writing-a-component.html).

In the next blog, we’ll learn how to add 3D models to our project. 
See you in the next one.

<script src="https://utteranc.es/client.js"
        repo="vivek-chandela/vivek-chandela.github.io"
        issue-term="pathname"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>