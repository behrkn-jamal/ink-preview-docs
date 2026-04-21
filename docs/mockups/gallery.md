# Gallery Screen Mockup

## Wireframe (Mermaid)
```mermaid
graph TD
    subgraph Header
        T[Gallery Title] --- S[Search Bar: 'Find inspiration...']
    end
    
    subgraph FilterBar
        F1[All] --- F2[Realism] --- F3[Traditional] --- F4[Minimalist] --- F5[Neo-Tribal]
    end
    
    subgraph GalleryGrid
        G1[Glass Card: Image + Artist]
        G2[Glass Card: Image + Artist]
        G3[Glass Card: Image + Artist]
        G4[Glass Card: Image + Artist]
        G5[Glass Card: Image + Artist]
        G6[Glass Card: Image + Artist]
    end
    
    subgraph BottomNav
        Nav1[Home Icon]
        Nav2[Gallery Icon - Active]
        Nav3[Editor Icon]
        Nav4[Profile Icon]
    end
    
    T --> S
    S --> FilterBar
    FilterBar --> GalleryGrid
    GalleryGrid --> BottomNav
```

## Visual Description
- **Background**: Deep Charcoal (`#0D0D0D`).
- **Search Bar**: Glassmorphic input field with a Muted Silver (`#B0B0B0`) placeholder and a search icon.
- **Filter Bar**: A horizontal list of capsules. The active filter has a gradient border and Pure White text; inactive filters have a thin grey border and Muted Silver text.
- **Gallery Grid**: A staggered masonry grid of high-fidelity tattoo images. Each image is wrapped in a Glassmorphic card (`20px` radius) that reveals the artist's name and a "Save" heart icon on hover/tap.
- **Visual Effect**: Images have a subtle outer glow to blend the edges with the dark background.
