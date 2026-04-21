# Home Screen Mockup

## Wireframe (Mermaid)
```mermaid
graph TD
    subgraph Header
        H[User Profile Icon] --- T[App Title: InkPreview] --- N[Notification Bell]
    end
    
    subgraph HeroSection
        B1[Gradient Hero Card: 'Visualize Your Next Ink']
        B2[Primary Button: 'Start New Project']
    end
    
    subgraph RecentProjects
        S1[Section Title: Recent Projects]
        C1[Glass Card 1]
        C2[Glass Card 2]
        C3[Glass Card 3]
    end
    
    subgraph BottomNav
        Nav1[Home Icon - Active]
        Nav2[Gallery Icon]
        Nav3[Editor Icon]
        Nav4[Profile Icon]
    end
    
    H --> B1
    B1 --> B2
    B2 --> S1
    S1 --> C1
    S1 --> C2
    S1 --> C3
    C3 --> BottomNav
```

## Visual Description
- **Background**: Deep Charcoal (`#0D0D0D`) consistent across the screen.
- **Header**: Minimalist. Pure White text for the title, Muted Silver for icons.
- **Hero Card**: A large, rounded rectangle (`20px`) with a vivid Electric Purple to Hot Pink gradient. Text is `Outfit` Bold, Pure White. The "Start New Project" button is a high-contrast white button with a subtle glow.
- **Recent Projects**: A horizontal scrolling list of Glassmorphic cards. Each card has a `rgba(26, 26, 26, 0.4)` fill, `15px` blur, and a thin `rgba(255, 255, 255, 0.12)` border.
- **Navigation**: A fixed bottom bar with a Glassmorphic background. Active icon is highlighted with the brand gradient.
