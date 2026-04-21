# Editor Screen Mockup

## Wireframe (Mermaid)
```mermaid
graph TD
    subgraph TopBar
        B[Back Button] --- T[Editor Title] --- S[Save/Export Button]
    end
    
    subgraph CanvasArea
        C[Main Preview Area: Skin Surface / Body Part]
        P[Overlay: Tattoo Image with Transform Handles]
    end
    
    subgraph Toolset
        T1[Placement Tool] --- T2[Opacity Slider] --- T3[Blend Mode] --- T4[Rotation/Scale]
    end
    
    subgraph AssetLibrary
        L1[Recent Uploads] --- L2[Gallery Presets] --- L3[Custom Brush]
    end
    
    subgraph BottomNav
        Nav1[Home Icon]
        Nav2[Gallery Icon]
        Nav3[Editor Icon - Active]
        Nav4[Profile Icon]
    end
    
    TopBar --> CanvasArea
    CanvasArea --> Toolset
    Toolset --> AssetLibrary
    AssetLibrary --> BottomNav
```

## Visual Description
- **Background**: Deep Charcoal (`#0D0D0D`).
- **Canvas Area**: The focal point. A high-resolution photo of a body part (e.g., forearm) with the tattoo image overlaid. The tattoo has transform handles (circles) at the corners, colored with the Electric Purple to Hot Pink gradient.
- **Toolset**: A Glassmorphic panel at the bottom of the canvas.
    - **Sliders**: Custom sliders with a gradient track and a white thumb.
    - **Buttons**: Glassmorphic buttons for blend modes (e.g., Multiply, Overlay).
- **Asset Library**: A slide-up drawer (Glassmorphic) containing a grid of available tattoo designs.
- **Export Button**: A Primary Button (Gradient) in the top right, making it the most prominent action.
