# Virtual Farm

This project describes my journey, into creating a Virtual Farm simulator.

*What is Virtual Farm*

A 3D version of a farm with a one or more crops. This we should be able to see in computer screen, or navigate it using VR Device (like Oculus), or even put a virtual camera, and train a AI agent to navigate it.

We should be able to generate any crop, in any conditions. they will be like age, weather, yield, sunlight, pests and so on. 

*Why we need it*

In future robots should be able to grow our crops. It might be in land based farms or virtical farms. It takes lot of time for us to shitch to alternatives like cell-factories. So these robots need to know how to navigate our existing farms and they need to know how to take care of stuff.

In order to do that, AI needs a virtual environment to train these things. Doing things only with physical objects, takes lot of effort and cost. And more than that it is time consuming. Future is digital first, our entire world will be reconstructed in 3D very soon.

## Journey

### Day 1

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
