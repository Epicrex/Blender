---
title: "📑 Glossary"
enableToc: true
---
## ─────────
## Visual
## ─────────

---

### Ambient Occlusion
_[[Wikipedia](https://en.wikipedia.org/wiki/Ambient_occlusion)] - [[Polycount](http://wiki.polycount.com/wiki/Ambient_occlusion_map)] - [[Unreal Engine Doc](https://docs.unrealengine.com/4.27/en-US/RenderingAndGraphics/PostProcessEffects/AmbientOcclusion/)] - [[Unity Doc](https://docs.unity3d.com/2021.3/Documentation/Manual/LightingBakedAmbientOcclusion.html)]_

Ambient Occlusion (AO) is a shading and rendering technique used to calculate how exposed each point in a scene is to ambient lighting. It shows subtle variations in lighting and helps your eyes detect surface details that would otherwise be washed out or unnoticeable.

> [!info] Ambient Occlusion Info
> 
> - Softens the overall lighting in your scene
> - Adds depth
> - Can be used as a budget [[glossary#Ray Tracing|ray traced]] occlusion
> - Requires high resolution light maps to look good

|Ambient Occlusion Off|Ambient Occlusion On
|:-:|:-:
|![[AO_off_1.png]]|![[AO_on_1.png]]
|![[AO_off_2.png]]|![[AO_on_2.png]]
|![[tdmMtT4_off.png]]|![[tdmMtT4_on.png]]

---

### Ray Tracing
_[[Wikipedia](https://en.wikipedia.org/wiki/Ray_tracing_(graphics))] - Unreal Engine Doc [[1](https://www.unrealengine.com/en-US/explainers/ray-tracing/what-is-real-time-ray-tracing)] [[2](https://docs.unrealengine.com/4.26/en-US/RenderingAndGraphics/RayTracing/)] (real-time) - [[Unreal Engine Doc](https://docs.unrealengine.com/5.0/en-US/hardware-ray-tracing-in-unreal-engine/)] (hardware) - [[Unity Doc](https://docs.unity3d.com/Packages/com.unity.render-pipelines.high-definition@14.0/manual/Ray-Tracing-Getting-Started.html)]_

Ray tracing can either be real-time ray tracing (games industry) or hardware ray tracing (film industry).

Ray tracing is a rendering method that simulates the physical behavior of light rays. It allows accurate rendering of things like shadows, reflections, highlights, and bounced light. However, ray tracing doesn't make everything better, and sometimes it's good to turn off ray traced shadows, lights and only keep ray traced reflections on.

Ray tracing is a broad term and consists of many smaller things like:
- Ray Traced Shadows
- Ray Traced Reflections
- Ray Traced Lighting
- Ray Traced [[glossary#Ambient Occlusion|Ambient Occlusion]]
- Ray Traced Global Illumination [[1]](https://developer.nvidia.com/rtx/ray-tracing/rtxgi)[[2]](https://docs.unity3d.com/Packages/com.unity.render-pipelines.high-definition@15.0/manual/Ray-Traced-Global-Illumination.html)
- Ray Traced Translucency

> [!info] Ray Tracing Info
> 
> - Only works on [Nvidia RTX](https://en.wikipedia.org/wiki/Nvidia_RTX) and some Nvidia GTX series graphics cards (all their graphic cards with DirectX ray tracing support)

Ray tracing off vs on:

![[20230603110116.png|600]]
![[20230603123401.png|600]]

On the flipped side, here's an example of ray tracing making the lighting and shadows look way worse. 

![[20230603111140.png|600]]

This doesn't mean that ray tracing in its nature makes lighting and shadows worse, but rather adding ray tracing into a scene that wasn't designed with ray tracing in mind won't yield good results. It's important for the environment artists to have direct previews of how the scene will look like with ray tracing on. And potentially there needs to be 2 different presets for ray tracing on and off. 

---

### Subsurface Scattering
Subsurface scattering (SSS) is a rendering feature, which allows for objects to appear more alive by scattering light more realistically inside themselves. Though subsurface scattering mostly has a reddish glow, the color totally depends on what is on the `SSS Color Map` as well as the light source color. For the render engine to properly scatter the light it also needs to know how thick each area on the model is, for that the `Thickness Map` is used (A map which is also useful for other things than sub surface scattering). The `SSS Color Map` is sometimes also complemented with a `SSS Control Map`.

Real objects can either absorb, scatter or ??? (To-Do) light rays. To recreate this in 3D, subsurface scattering (SSS) maps are used in combination with thickness maps.

>[!info] Theory behind real life SSS (Transparency and Translucency)
>
>When traveling in an inhomogeneous medium like air or translucent materials, light can be absorbed or scattered.
> 
>When absorption occurs, the light intensity decreases and the direction of the ray doesn’t change.
>>[!example] Objects that absorb light
>
>When scattering occur, the ray direction changes randomly and doesn’t change its intensity.
>
>>[!example] Objects that scatter light
>>
>>- Dirty water
>
>If there is no scattering and the absorption is low, rays can pass directly through.
>
>>[!example] Objects that don’t scatter light with low absorption
>>
>> - Clear water
>
>The further light travels in such a medium/ material, the more it's absorbed and/ or scattered. Therefore, object thickness plays a large role in how much the light is absorbed or scattered
>>[!example] Examples of SSS in action
>>
>> Ears are thin >>> Low light ray absorption = Light is very visible through ears

![[20230603111548.png|50]]

> [!example] Objects where SSS is vital
> 
> - Fleshy characters (any character or creature)
> - Wacs
> - Marble
> - Milk

---

### Anisotropic Filtering
To-Do: Explain better

Anisotropic Filtering (AF), is a method of enhancing the image quality of textures on surfaces that are at oblique viewing angles with respect to the camera. Like bilinear and trilinear filtering, anisotropic filtering eliminates aliasing effects.

![[20230603111310.png|600]]

---

### Screen Space Refraction
- Adds local reflections to the objects
- Helps Glass, plastic, water, and other transparent/translucent materials.
- Similar to screen space reflection. Screen Space Reflections and Ambient Occlusion aren't compatible with Screen Space Refraction. And are disabled on surfaces that use it.

---

### Screen Space Reflection
A technique for reusing screen-space data to calculate reflections. Used for more subtle reflections like wet surfaces or puddles.

---

### Caustics
https://youtu.be/7l6QOcgWXfI

---

### Bloom
- Bloom/ light bloom (not to be confused with glow/emission) is a rendering technique to reproduce artifacts of real-world cameras. It produces fringes or feathers of light extending from the borders of bright areas in an image, contributing to the illusion of an extremely bright light overwhelming the camera or eye capturing the scene. 

- Even tough bloom is most apparent around emissive objects, it can just as well happen with normal light sources

---

### Motion Blur
- Portrays the illusion of speed or movement blurring the objects
- Tends to remove temporal aliasing effects
- Used as a real time filter, for animation renders and even still renders
- Not having Motion Blur on can lead to more eye strain, but can give you motion sickness
- It can also increase the visual fidelity

---

### Lens Flare
To-Do

![[20230603111506.png|400]]

---

### Volumetric Effects

#### Volumetric Lighting

Volumetric lighting or God Rays lets beams of light shine across the environment.

![[Pasted image 20230603124930.png|500]]

#### Volumetric Fog
> [!example] Volumetric Fog is used for 
>
> - Fog
> - clouds
> - dust
> - smoke
> - Or any airborne material capable of partial occlusion

Volumetric fog has a great synergy with volumetric lighting.

To-Do: Add image

---

### Chromatic Aberration
To-Do: Restructure

- In real life chromatic aberration occurs when a lens fails to focus all the colors into a single point, causing an ever so slight color shift on the edges of some objects
- A color fringing or distortion
- Basically the R, G and B channels are shifted to the left/ right. The shift amount and what channels are shifted can be tweaked

![[Pasted image 20230603125616.png|700]]

---

### Depth of Field
Blurs out things that are farther away from the focus point. The distance at which the effects starts and ends at, as well as the fall off, can all be adjusted in the render/ game engines settings. Sometimes it is even possible to set multiple focal points.

![[Pasted image 20230603125653.png|700]]

---

### DLSS and FSR
- DLSS stands for Deep learning super sampling (Nvidia GPUs)
- FSR stand for FidelityFX Super Resolution (AMD GPUs)

Both DLSS and FSR are basically the same thing, just developed by different companies. It's an image upscaling technology which uses deep learning to upscale lower-resolution images

---

### Anti-Aliasing
Anti-aliasing (AA) removes aliasing effect. Aliasing is the appearance of jagged edges in a rasterized image (image rendered using pixels). Samples the pixels around the edges and uses them to blend away the appearance of jagged edges.

---

### Blend Modes in 3D Software
To-Do: Restructure

Blend methods apply to every software (some have more or less modes). Every texture has to have a blend mode, the most common one being opaque. Blend Modes describe how the output of the current material will blend over what is already being drawn (rendered) in the background.

- Black = invisible/ not rendered
- White = visible/ rendered

#### Opaque Blend
Surface through which light neither passes nor penetrates. The previous color will be overwritten and alpha is ignored. 
- Cheapest blend method

> [!example] Opaque Blend Examples
> 
> - Plastics
> - Metals
> - Stone
> - Wood

#### Masked Blend/ Alpha Clip
Used to make some parts invisible and others visible. The invisible parts are not rendered at all. Only needs black and white, however if gray values are in the control texture a clip threshold value (which is per default set but can be changed) decides what counts as black and what as white. 

> [!example] Masked Blend/ Alpha Clip Examples
> 
> - Fence
> - Chains
> - Net

#### Translucent Blend/ Alpha Hashed
Used for objects that require some form of transparency. By taking advantage of the full range of an opacity control map, it can make objects be and opacity level.
- Can produce noise
- Most expensive blend mode

> [!example] Translucent Blend/ Alpha Hashed Examples
> 
> - Thin cloth/ Nylon
> - Jellyfish
> - A lot of female clothing

#### Additive
Takes the pixels of the Material and adds them to the pixels of the background (Like PS Linear Dodge (Add))
No darkening, since all pixel values are added together.

#### Multiply/ Modulate
Multiplies the values of the Material against the pixels of the background.


---

### Object Properties

#### Transparent
- With transparent objects, almost all light passes directly through them. 
- One can clearly see what's behind transparent objects

> [!example] Transparent Examples
> 
> - Air
> - Water
> - Clear glass
> - Plastic wrap

#### Translucent
- Translucent objects allow some light to travel through them. 
- Often one can't see what's behind a translucent object but 

> [!example] Translucent Examples
> 
> - Frosted glass
> - Sunglasses
> - Notebook paper
> - Lampshade

#### Transparency/ Opacity/ Alpha

---

### Light Ray
- In air light rays travel as straight lines
- A light ray that hits a surface is called the `incident ray` and the light that bounces off a surface is called the `reflected ray`
- When the light ray hits an `opaque surface` the `reflected angle` is the `same` as the `incidence angle`
- When a light ray hits opaque surface one of two events occur:
    1. Incident light ray hit surface and `bounces off` in the same angle `(reflected light)`
    2. The light ray `passes through` the surface in a straight line `(refracted light)`
- Absorption of the light ray doesn’t occur on the material surface

> [!example] Objects that reflect light
> 
> - Polished metal
> - Glass
> - Water

> [!example] Objects that reflect light
> 
> - Lenses
> - Prism

![[Pasted image 20230603130631.png|400]]

---

### Specular Reflection
- The more planar the surface is, the more the incidence angle equals the reflected angle (law of reflection)
- Most surfaces are irregular
- Rougher surfaces have `larger highlights` and are `dimmer` and `less reflective`
- Smoother surfaces are `brighter` and `more reflective`


Examples:

> [!example] Smoother Objects
> 
> - Polished metal
> - Glass
> - Water

> [!example] Rougher Objects
> 
> - Concrete
> - Wood
> - Leather

![[Pasted image 20230603130821.png|500]]

---

### Diffuse Reflection
- Diffuse reflection is light that has been refracted
- Light ray hits a surface, enters the object, is scattered multiple times and finally is refracted out of the object at the same point it entered the object
- Most diffuse materials have high absorption so for the light to leave the object it can only travel (scatter) short distances within the object
- Materials with both high scattering and low absorption are called translucent or participating materials
- The outgoing direction of the ray is fairly independent of surface roughness and the incident direction
- Surface irregularities are referred to as roughness, smoothness, glossiness or 
micro-surface

Examples for diffuse objects:

> [!example] Objects with high scattering and high absorption

> [!example] Objects with high scattering and low absorption
> 
> - Smoke
> - Milk
> - Skin
> - Jade
> - Marble
> - Fog

![[Pasted image 20230603131037.png|400]]

---

## ─────────
## Topology
## ─────────

---

### Poles
There are two types of poles, N-Poles (3 edges) and E-Poles (5+ edges). More about poles on the topology page.

A pole is a set of edges that merge into a single vertex. Avoiding poles with six or more edges on curved surfaces is something that you should incorporate into your modeling workflow. It is best practice to try to avoid poles when modeling.

---

### Faces

- Triangle, Tris, Polygon: 3 vert face
- Quad: 4 vert face
- Ngon: 5+ vert face

---

### Backface Culling
To-Do

---

### Convex/ Convex Hull
Convex is means (ToDo). A convex hull is a mesh that wraps around another mesh in the most optimal way.

> [!example] Convex Hulls are used for
> 
> - Collisions
> - Physics calculation boundaries, for hair for example
> - Baking cages

---

### Chamfer
A corner with one edge is a hard edge, with 2 edges a chamfer and anything more than 2 is a bevel. Chamfers mostly have a ~45° angle.

---

### LOD
To-Do

LOD's (Level of Detail) ...

---

### Tessellation
Tessellation (Triangulation) is the process of the converting faces to random even triangles.

---

## ─────────
##  Textures
## ─────────

---

### Bit Depth
_[[Wikipedia](https://en.wikipedia.org/wiki/Color_depth)] - [[Polycount](http://wiki.polycount.com/wiki/BitDepth)] - [[Photoshop Doc](https://helpx.adobe.com/photoshop/using/bit-depth.html)]_

>[!example]- Bit depth explanation (videos)
><div style="text-align: center;">
>
>**Bit depth explanation**
><iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/Y-wSHpNJs-8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
></div>

Bit depth (Color depth) determines how much color information an image can store, which directly influences the dynamic range the image can have.

It's often good to render/ bake images with higher bit depth than needed, and later in the process convert them to a lower bit depth. The trade-offs with higher bit depths are increased render times and bigger file sizes.

Whether the texture is only intended for one object or a texture atlas, should not influence which bit depth to choose.

#### Bit Depth Math
The most common bit depths are 8 bit, 16 bit, 24 bit and 32 bit. Let's take 32 bit for example, 8 of the 32 channels represent red, 8 channels green, 8 channels blue and lastly 8 channels for alpha. This means that just by looking at the bit depth, one can deduce if the image has alpha or not. If the image didn't have alpha, those 8 channels for alpha would fall away and one would have a 24 bit image.

- 6 bit RGB (2,2,2)
- 8 bit RGBA (2,2,2,2)
- 12 bit RGB (4,4,4)
- 16 bit RGBA (4,4,4,4)
- 24 bit RGB (8,8,8)
- 32 bit RGBA (8,8,8,8)

>[!info] Max amount of unique values per channel
>
>1 bit image (Integer):
>```
> 2 Tone Values >>> Black/ 0 and White/ 1
>```
>8 bit image (Integer):
>```
> 256 Tone Values >>> 256 Reds x 256 Greens x 256 Blues = 16.7 Million RGB Values
>```
>16 bit image (Integer/ Float):
>```
> 65,536 Tone Values >>> 65,536 Reds x 65,536 Greens x 65,536 Blues = 281 Trillion RGB Values
>```
>32 bit image (Integer/ Float):
>```
>4,294,967,295 Tone Value
>```
>
>So 16 bit is 250 times bigger than 8 bit and 32 bit is 15 million times bigger than 16 bit (exponential growth). Though the file size gets progressively bigger, it doesn't increase by that margin.  

#### Human Perception of Bit Depth
Humans can only distinguish between 2 ~ 10 million colors, so we can't even see all colors of 8 bit. This means that an image exported in 8 bit or 16 bit will always look identical. The only advantage in using anything above 8 bit is for editing photos and only for the process of editing and not the export. For 2D artists 8 bit will always be enough and most drawing software doesn't even support more than 8 bit.

---

### Banding
Banding artifacts are caused by a lack of precision with 8 bit normal maps. There aren’t enough color values to accurately represent subtle differences between the high poly and low poly surfaces, which results in stair stepping artifacts.

[In depth PDF about banding](https://loopit.dk/banding_in_games.pdf)

---

### Atlas/ Trim Sheet
To-Do

---

### Dithering
Adds noise to combat banding. So Dithering is mostly only used with low bit images. Dithering can be done by adding a noise filter in Photoshop.

---

### Tangent Space
Normal maps can be tangent-space or object-space. World-space is basically the same as object-space, except it requires the model to remain in its original orientation, neither rotating nor deforming, so it's almost never used. Always use tangent space for the normal map, however object space normal maps can be useful as a utility mask for texturing. The object space Normals maps are easily spotted, they look like orange normal maps.

---

### Handedness (Normal Map)
Handedness has influence over: Object transforms, Normal maps, rigs/ animations, ... . 


#### Handedness with Normal maps
Normal maps can either be Direct X or Open GL. To go from one to the other, the green channel from the normal maps needs to be flipped.

#### Handedness with Objects
For objects it's as follows:

|Handedness|Cords|Software
|:-:|:-:|:-:
|Right Handed (Open GL)|Y-Up|Marmoset, Substance Painter, Maya, Houdini, Modo
|Right Handed (Open GL)|Z-Up|Blender, 3ds Max, CryENGINE
|-|-|-
|Left Handed (Direct X)|Y-Up|ZBrush, Unity, Cinema 4D, Light Wave
|Left Handed (Direct X)|Z-Up|Unreal Engine

Software that supports both Left and Right handedness: Blender, Substance, IClone

The X is in all software the Right vector (Left/Right). The Y and X can either be the Forward vector (Forward/Back or Back/Forward) or the Up vector (Up/Down or Down/Up).

It's important to use the same space for an assets and its textures. When working with software that has different spaces, this can be done by switching channels at export.

---

### Mipmaps
To-Do

---

### Tangent Space
To-Do
https://marmoset.co/posts/toolbag-baking-tutorial/

---

## ─────────
## Animation
## ─────────
To-Do

---

### Apex and Peak
To-Do

---

### Bone Head, Tail and Body
To-Do

---

## ─────────
## Baking
## ─────────

---

### Floaters
Floaters are loose detail pieces that float above the surface of a mesh and are baked down into the normal map. This creates the illusion that they are connected with the mesh they hover above. A boolean cut floater for example can save a lot of time because one doesn't actually have to do a boolean cut and can quickly duplicate the piece along the mesh surface without having to integrate it into the topology.

---

### Low and High Poly
ToDo

(in the context of baking high to low)

---

### Skews 
ToDo

## 🚧Work in Progress🚧

### Rigid Body
An object that is affected by forces of gravity.