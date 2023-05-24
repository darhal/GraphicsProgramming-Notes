# Image Reconstruction

## 1st Generation Image Reconstruction Techniques
These techniques can upscale images as low as half of the native presentation resolution without any major image quality losses.

### AMD's FSR 1 
AMD's FidelyFX Super Resolution is an open-source library that offers a classical algorithms (non AI based) that can upscale images without providing any additional inputs. 
The algorithms also offers sharpening post processing effect to sharpen the reconstructed image. 
This technique is usually fast and is cross GPU vendor (meaning it can run on any GPU even older ones)

### Nvidia's DLSS 1 
Nvidia's Deep Learning Super Sampling is an AI based approach to image reconstriction that can upscale images given low resolution images and motion vectors.
This technique requires special Tensor Cores to run at optimal speed and is limited to Nvidia GPU's

### Temporal Anti-Aliasing Upscaling (TAAU)
A software technique implemented and used by UE4.

## 2nd Generation Image Reconstruction Techniques
These techniques can upscale images as low as quarter of the native presentation resolution without any major image quality losses.

### AMD's FSR 2
Unlike FSR1, [FSR2](https://github.com/GPUOpen-Effects/FidelityFX-FSR2) requires other inputs along with the low resolution image. These inputs include : 
* Depth buffer (at render resolution = low resolution)
* Motion vectors (Velocity buffer at render resolution)
* [Optional] Reactive mask (at render resolution) : Used to complete areas that do not write to depth/motion vectors (e.g: particles, alpha blended objects, etc)
* [Optional] Transparency and cmposition mask (at render resolution) : Denotes area of other special rendering (e.g. : ray traced reflections, animated texture)

This technique is usually fast and is cross GPU vendor (meaning it can run on any GPU even older ones)
### Nvidia's DLSS 2
Similar to DLSS1 but offer the possiblity to upscale from quarter resolution (still limited to Nvidia GPUs)

### Intel's XeSS 1
Quite similar in terms of visual quality to DLSS2. It uses previous frames and a machine learning model to upscale a low resolution image. Apprently, it doens't need motion vectors (TO CONFIRM).

### Temporal Super Resolution
A software technique implemented and used by UE5.
