# Research: Photo-based AR Mesh Wrapping (Tier 3)

## Objective
To implement realistic tattoo visualization by wrapping 2D tattoo designs onto body photos. This requires understanding the 3D geometry of the body part shown in the 2D image.

## Technical Approach
We are adopting a **Depth-Based Displacement Mapping** pipeline.

### Pipeline
1.  **Monocular Depth Estimation (MDE)**: Use a pre-trained neural network to estimate depth from the input image.
2.  **Surface Normal Generation**: Derive surface normals from the depth map to understand skin curvature.
3.  **Fragment Shader Displacement**: Apply the tattoo texture to the body image using a custom GLSL shader that distorts the UV coordinates based on the depth/normal map.

### Recommended Model: DepthAnything-Small
*   **Why**: State-of-the-art performance for mobile devices.
*   **Format**: Convert to `.mlpackage` (iOS/CoreML) and `.tflite` (Android).
*   **Hardware Acceleration**: Use Apple Neural Engine (ANE) on iOS and GPU delegate on Android.

### Implementation Stack
- **Bridge**: Native MethodChannels (Swift/Kotlin) for handling high-bandwidth tensor buffers.
- **Rendering**: Custom Flutter `FragmentProgram` (Impeller).
- **Blending**: Multiply blend modes implemented in GLSL to simulate ink-skin integration.

---

## Action Plan (Milestone 1)
1.  **Infrastructure**: Establish Swift (iOS) and Kotlin (Android) MethodChannel handlers.
2.  **Model Integration**: Configure on-device inference for DepthAnything-Small.
3.  **Depth Map Visualization**: Implement a debug UI to verify the model is accurately capturing body surface contours.
