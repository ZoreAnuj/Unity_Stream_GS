# Unity Stream GS

Unity plugin for streaming and playing back animated 3D Gaussian Splatting sequences in real time. Supports AR and VR pipelines with both HDRP and Built-in render pipeline integration.

## Architecture

- **Gaussian Splatting Renderer** (`package/Runtime/GaussianSplatRenderer.cs`) - Core rendering component that sorts and rasterizes gaussian splats per-frame using compute shaders
- **Streaming Player** (`package/Runtime/GaussianSplatPlayer.cs`) - Sequence playback controller for animated gaussian splat captures with frame interpolation
- **Asset Pipeline** (`package/Editor/GaussianSplatAssetCreator.cs`) - Import pipeline supporting PLY and SPZ file formats with batch conversion and K-means clustering for LOD
- **Splat Editing** (`package/Editor/GaussianMoveTool.cs`, etc.) - In-editor manipulation tools for translating, rotating, and scaling gaussian splat volumes
- **Cutout System** (`package/Runtime/GaussianCutout.cs`) - Region-based cropping for isolating objects within gaussian splat scenes
- **HDRP Integration** (`package/Runtime/GaussianSplatHDRPPass.cs`) - Custom render pass for High Definition Render Pipeline compatibility

## Stack

C# / Unity 2022.3+ / Burst / Unity.Mathematics / Compute Shaders / HLSL

## Installation

Add via Unity Package Manager using the `package/` directory. Requires Burst 1.8.8 and Unity Collections 2.1.4.

## Supported Formats

PLY (standard gaussian splat), SPZ (compressed), with batch import and automatic asset optimization.
