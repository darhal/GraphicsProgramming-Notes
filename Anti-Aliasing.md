# Anti-Aliasing
Anti-Aliasing is the process of removing jagged, or stair-stepped, lines on edges and objects that should otherwise be smooth. 
There are different methods of anti-aliasing used to reduce these types of visual artifacts. 
Some are developed for use with specific renderers and platforms, while others are ideal for improving performance and fidelity.

## Anti-Aliasing Techniques :
### MSAA
Multiple Sample Anti-Aliasing only smooths parts of the frame. 
MSAA primarily looks at areas that are issue-prone, like the edges of geometry. 
Where aliasing problems can occur on edges, MSAA manipulates their color to be between the color of the two pixels that make up the edge. 
The dithering effect gives the illusion of smoother edges.
MSAA is supported by most GPU hardware but doesn't work with deferred renderers.
### FXAA
Fast Approximate Anti-Aliasing is a spatial-only anti-aliasing technique (that is a post-processing) effect that uses a high contrast filter to find edges and smooth them by blending (dithering) between the pixel edges. 
It is fast to render and well-suited for low-end devices and desktops, but the final image can lose fidelity when compared to other anti-aliasing techniques.
### TAA
Temporal Anti-Aliasing is a software implementation that used previous frames (with some jitter) to remove the aliasing in the current frame.
This method is effective and considered an industry standard. 
However it suffers from ghosting/trailing effects where you can see ghosting effect behind moving objects in a scene (this is a result of using previous frames).
### TSR
Temporal Super Resolution

## Anti-Aliasing for Upscaling
Anti-Aliasing techniques can also be used to upscale images. These techniques are well described in [Image Reconstruction](Image_Reconstruction.md)
