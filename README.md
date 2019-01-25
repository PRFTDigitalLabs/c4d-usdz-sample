<p align='center'>
<a href="/docs/usdz/spinner.usdz?raw=true" rel="ar"><img src="/docs/img/spinner_sq_loop.gif?raw=true" alt="" width="443" height="443"></a></p>

# c4d-usdz-sample
A sample workflow implementation to aide in the conversion of Cinema 4d files to iOS Quicklook USDZ 3D files.

## Contents

#### Source Files:
- [/spinner/spinner.c4d](/spinner/spinner.c4d) is the Cinema 4d 3D source file which is used to bake textures and export to other formats.
- [/spinner/tex](/spinner/tex) contains the source images for texture maps referenced by that file.

- [/spinner/baked](/spinner/baked) contains the 'baked' textures for each of the [various PBR channels](/docs/img/screenshots/PBR.jpg).

#### Exports from Cinema 4d:
- [/spinner/abc](/spinner/abc): Alembic ([export settings](/docs/img/screenshots/alembic-export.png))
- [/spinner/dae](/spinner/dae): Collada (v1.4, everything unchecked)

#### Conversions:
- [/spinner/gltf](/spinner/gltf): glTF (uncompressed)
- [/spinner/glb](/spinner/glb): glTF (binary)
- [/docs/usdz](/docs/usdz): Universal Scene Description (Zipped)

#### 🌟 Utility:
- [/spinner/mkargs](/spinner/mkargs), is a bash script that will automatically generate a [/spinner/usdargs.txt](/spinner/usdzargs.txt) file which can be passed into the apple `usdz_converter` tool via the `-f` argument.

## Prerequisites

In order to open the 3D source file, you will need to install [Cinema 4d](https://www.maxon.net/en/products/cinema-4d/overview/). This file was created with R20.

To create [a USDZ file](https://github.com/PixarAnimationStudios/USD), I converted the exported [Alembic](https://github.com/alembic/alembic) file using `usdz_converter`. `usdz_converter` is a utility that comes with [Xcode](https://developer.apple.com/xcode/). An introduction to that tool (not quite documentation), can be found in this [WWDC 18 video](https://developer.apple.com/videos/play/wwdc2018/603/?time=2297).


## Goals of this exercise:

For a more in-depth exploration of this process, please view my blog post here: (https://blog.truthlabs.com).

### Utilize Cinema 4d as a source for USDZ files.
 - [x] Geometry
 - [x] Scale
 - [x] Animation
 - [x] PBR Textures
 
### Utilize Cinema 4d as a source for Facebook (.glTF binary) 3D posts
 - [x] Geometry
 - [ ] Animation ([not currently supported by Facebook](https://developers.facebook.com/docs/sharing/3d-posts/asset-requirements#requirements))
 - [x] PBR textures

### Streamline the conversion of assets
- [x] Expedite the conversion process from c4d to usdz.
- [x] Expedite the preview process of usdz files.
- [ ] 'One-click' process to generate all assets, including web preview.

### Identify strengths & weaknesses of
- [x] USDZ format
- [x] associated pipeline tools (in context of c4d -> iOS Quicklook)
