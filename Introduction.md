# Introduction

## Graphics API
To access GPU graphics capbilities and be able to do things on the GPU one need to use a graphcis API to communicate with the vendors driver which will finally issue commands to the actual hardware. A bunch of Graphics API's exist but they can be split in 2 categories High Level APIs and Low Level APIs.

### High Level APIs
These are the older APIs that existed for a longtime. The vendors driver do most of the work for us while the programmer have little to no-control over low level concepts such as memory managment, synchronization, etc... This makes these APIs easy to use (suitable for prototyping, etc).
The vast majority of these APIs operates as a huge state machine (e.g. operations are performed on bound resources). They also usually have no or limited support for multi-threading.
|API|Platform|Shading Language|Description|
|---|--------|----------------|-----------|
|OpenGL|Cross-Platform|GLSL|Not an actual API but a specification maintained by Khronos Group. Vendors provide the actual implementation.|
|DirectX 11| Windows + Xbox|HLSL|Unlike OpenGL this is an actual specification and API maintained and implemented by Microsoft on top of vendor firmware. (State machine model like OGL)|

### Low Level APIs
These came out recently and offer programmer greater flexibility and control over the GPU. The driver in this case is just a thin layer translating programmer commands to the actual hardware. These modern APIs usually offer also advanced features such as Ray-Tracing, Variable Rate Shading, Mesh Shaders (via extensions if the hardware supports them). 
State machine in these APIs are hidden/limited to command buffers and structures such as PSO bundle most of the existing states togther (including shaders) which provide room for optimisation. However PSO need to be compiled before the actual rendering occurs otherwise stutters will occur during the frame. 
Also it's worth noting that these APIs support multi-threading as command recording, PSO compilation, ressources allocation and more can happen conccurently on multiple threads.

|API|Platform|Shading Language|Description|
|---|--------|----------------|-----------|
|Vulkan|Cross-Platform|SPIRV (GLSL or HLSL)|Not an actual API but a specification maintained by Khronos Group. Vendors provide the actual implementation. |
|DirectX 12| Windows + Xbox|HLSL|This is an actual specification and API maintained and implemented by Microsoft on top of vendor firmware.|
|Metal| Apple|MSL|This is an actual specification and API maintained and implemented by Apple for their hardware|
