# Virtual Farm

This project describes my journey, into creating a Virtual Farm simulator.

*What is Virtual Farm*

A 3D version of a farm with a one or more crops. This we should be able to see in computer screen, or navigate it using VR Device (like Oculus), or even put a virtual camera, and train a AI agent to navigate it.

We should be able to generate any crop, in any conditions. they will be like age, weather, yield, sunlight, pests and so on. 

*Why we need it*

In future robots should be able to grow our crops. It might be in land based farms or virtical farms. It takes lot of time for us to shitch to alternatives like cell-factories. So these robots need to know how to navigate our existing farms and they need to know how to take care of stuff.

In order to do that, AI needs a virtual environment to train these things. Doing things only with physical objects, takes lot of effort and cost. And more than that it is time consuming. Future is digital first, our entire world will be reconstructed in 3D very soon.

## Journey

### Day 2 
2nd June 2023

Unreal Engine on my Mac was very slow. I could barely select objects. Thought my Windows laptop with poerfull GPU will help. And wasted 2hrs updating drivers etc. Same issue there. What hardware do other game developers are using? My systems are no way average...they are super powerfull systems. 

Anyway finally managed to understand what is NeRF.. (Could not get what it is even after watching so many Two Minute Paper videos). 
It is basically a nural network overfitted to produce 3D data from different points of view. And it seems super duper slow. There is no way we can use it in our application. Also It needs Images of single object from different points of view. But at max we can get a continues video of plants in a farm. 

Do we need a NN(Nural Network)? Yes

What does it take as input, What does it Train on, What does it produce ? Not sure.

According to GPT4 it might take around 6MB per plant, and based on various techiniques we can render a 1acre of corn on current highend GPUs.
Here are the techniques. 

1. **Level of Detail (LOD)**: You can use a technique known as "level of detail," where you have multiple versions of each mesh, with varying levels of detail. When the mesh is far from the camera, you render a less detailed version, which uses less memory and processing power. As the mesh gets closer to the camera, you switch to more detailed versions. This allows you to have a high overall level of detail while minimizing the impact on performance.

2. **Frustum Culling**: This is a technique in 3D computer graphics which eliminates the rendering of objects or parts of objects that are outside the viewing area (i.e., not visible on the screen). This is very useful for large environments because it allows you to only process the parts of the scene that the player can actually see.

3. **Occlusion Culling**: Similar to frustum culling, occlusion culling is a technique for deciding which objects to render based on whether they are actually visible given the current view point. An object that is behind another object might be within the viewing frustum, but if it's completely occluded by the front object, there's no point in rendering it.

4. **Streaming/Chunk Loading**: Splitting the scene into chunks and then loading/unloading them based on the camera's position can also help. This is commonly done in video games with large open worlds. As the camera moves, you load in the chunks of the world that are about to come into view, and unload the chunks that are far away from the camera.

5. **Impostors/Billboarding**: For very far objects, you can use a technique known as impostors or billboarding. Instead of rendering a full 3D mesh, you render a 2D sprite that gives the illusion of a 3D object. This is often used for things like trees and foliage in the distance.

### Day 1
1st June 2023

We need to understand what are game engines, what are 3d assets, how to render them. 

Omniverse from NVIDIA, they are trying to simulate factories, cities, and planet. They want to build collaboration tools, and stuff. And also sell lot of hardware to do it. So I need the same, but instead of factories, I simulate farms. 

Saw a video on how Omniverse setup is done. It is more like a online collaborative UI. Means anyone can edit in 3D and every one else can see it. And they stream all that video to the viewer using [Nice-DCV](https://docs.aws.amazon.com/dcv/latest/adminguide/what-is-dcv.html). So you have bunch of RTX enabled GPU and some collaborative 3D editor etc. 

We don't need all that software, but we might neede the hardware, because we need Real time Ray-Tracing which seems possible with that hardware. 

From one podcast [Into the Metaverse](https://podcasts.google.com/search/Into%20the%20Metaverse) I larned about USD. A fileformat that they want to support. It is bilt by Pixar. If we generate a Virtual Form, that might be in the form of such a file. 

Learned about USD through couple of Youtube videos. It is a highly flexible system to tell what we want in any scene. 

Now it is time to understand about Mesh, Texures, Materials, Physics, Shaders etc. These are the things that represent how our 3D obejcts look and behave.

**Things to do**

* Using Unreal Engine 5, develop a small native program(C++) that loads one such USD and displays.
* Disgn one plant, and apply physics, and show. 
* Calculate the cost of million such plants. 
