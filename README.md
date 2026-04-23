<div align="center">

# ToonWater Shader

*A lightweight and highly customizable stylized water shader built for Unity Universal Render Pipeline.*

[![ToonWater Showcase](https://img.youtube.com/vi/Fp_cOwRofbs/maxresdefault.jpg)](https://youtu.be/Fp_cOwRofbs)

</div>

The shader is entirely **Artist Friendly**, exposing all necessary properties in the Unity Inspector so game designers can easily tweak colors, wave speeds, and foam thickness without touching the code.

***

### Technical Architecture
To ensure maximum control over the rendering pipeline and maintain solid frame rates, I wrote this shader directly in HLSL.

* **Dynamic Depth Coloring:** I utilized Linear Eye Depth and Scene Depth to calculate the exact distance between the water surface and the ground below. This mathematical approach allows the water to automatically blend between shallow and deep colors, giving players a visual sense of depth without needing extra 3D models.

* **Intersection Foam Generation:** Instead of manually placing foam textures around objects, I engineered a system that dynamically generates a crisp white outline wherever the water intersects with solid geometry like rocks or shorelines.

* **Stylized Surface Patterns:** I implemented a scrolling Voronoi noise setup to simulate water ripples and caustics. By running the texture data through a smoothstep function, I ensured the foam edges remain sharp and clean, preventing any blurry pixels that could break the cartoon aesthetic.

* **Vertex Wave Displacement:** To make the ocean feel alive, I wrote a custom vertex function using Sine waves driven by the engine time and world position. This physically moves the geometry up and down, turning a simple flat plane into a rolling ocean surface without relying on expensive physics calculations.

***
