---
layout: post
title: 3D Ray Tracing Engine
subtitle: 3D rendering engine using path tracing algorithms
gh-repo: pblood66/RayTracer
gh-badge: [star, fork, follow]
tags: [simulation, Java]
comments: true
mathjax: true
author: Patrick Blood
---

![Final Rendering](../assets/img/final-render.jpg)

{: .box-success}
Over the summer, I took on a personal project that really pushed the boundaries of what I’d done in software development: I built a simple 3D ray tracing engine in Java. You can check out the code on [GitHub](https://github.com/pblood66/RayTracer). It’s a proof-of-concept renderer that produces basic 3D images by simulating how rays of light interact with spheres and materials.

At first glance, ray tracing sounds intimidating. It’s a core graphics technique used in everything from Pixar movies to real-time rendering engines, and it involves a fair amount of math and computer science concepts like vectors, recursion, and material shading. But tackling it as a project gave me a chance to level up in so many areas, not just graphics, but software structure and development habits too. 

## What the Engine Does

The renderer works by casting rays from a virtual camera through each pixel of the image plane. Each ray is tested for intersections with scene objects (currently spheres), and the closest hit determines how the pixel color is computed. I implemented ray–object intersection logic using vector equations and used this as the foundation for shading and material behavior.

The output is written to the PPM image format, which kept the focus on rendering logic rather than file-handling complexity. This also made it easier to inspect intermediate results and debug visual artifacts during development.

### Materials and Light Interaction

To simulate different surface properties, I implemented multiple material models:

- Lambertian (diffuse) materials scatter incoming rays randomly to approximate matte surfaces.

- Metal materials reflect rays with controllable fuzziness to simulate imperfect reflection.

- Dielectric materials handle refraction and reflection using Snell’s Law and Schlick’s approximation.

Each material encapsulates its own scatter behavior, which helped keep the rendering logic modular and extendable. This design choice made it easier to experiment with different material behaviors without rewriting the core ray traversal code.

## What I Learned

### Software Structure and Organization

Building a renderer from scratch forced me to think carefully about how to organize code. I broke the project into logical components like rays, vectors, materials, and scene objects, which made the codebase easier to understand and extend. This was a big step up from smaller, single-file programs.

### Math in Practice

Ray tracing relies heavily on vector math and geometric reasoning. Implementing these concepts in code helped solidify ideas like dot products, normalization, and reflection in a way that felt practical instead of abstract.

### Debugging Through Visualization

One of the biggest challenges was debugging. When something went wrong, the program didn’t crash — it just produced strange images. Learning how to isolate issues by testing individual parts of the rendering pipeline taught me to be more patient and methodical when debugging complex systems.

### Iteration and Refinement

This project evolved over time. I started with basic ray-object intersections and gradually added materials, shading, and scene complexity. That incremental approach helped me learn how to build systems that grow without becoming unmanageable.