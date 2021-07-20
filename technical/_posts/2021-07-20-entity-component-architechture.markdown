---
layout: post
title:  "WebXR #3: Entity-Component Architecture"
date:   2021-07-20 11:06:00 +0530
category: Technical
---
Imagine you want to build a car entity by assembling components. We’ll need three components:

- **engine component** with properties like horsepower, torque.
- **material component** with properties like color, design.  
- **tire component** with properties like steering angle.

In Aframe, an entity is defined as:

```
<a-entity geometry="primitive: sphere; radius: 1.5"
         light="type: point; color: white; intensity: 2"
         material="color: white; shader: flat; src: glow.jpg"
         position="0 0 -5"></a-entity>
```

Entities are represented by the `<a-entity>` element.

Components are represented by HTML attributes on `<a-entity>`. We have four components in the code snippet above: geometry, light, material, position.

Each component has its own set of properties and property values. E.g., primitive and radius are the properties for geometry components with values sphere and 1.5, respectively.

There are three ways to bring components into your project:

1. Directly use core components of Aframe in your code. You can find the list of core components in the [documentation](https://aframe.io/docs/1.0.0/introduction/) of Aframe.

2. You can use the publicly available 3rd party components. There are a host of available options:
  - [Aframe Registry](https://aframe.io/aframe-registry/)
  - [npm’s search](https://www.npmjs.com/search?q=aframe-component)
  - There are multiple Github projects you can find online.

3. You can also register your custom components. We’ll learn how to do this in the next blog.

See you in the next one.

<script src="https://utteranc.es/client.js"
        repo="vivek-chandela/vivek-chandela.github.io"
        issue-term="pathname"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>