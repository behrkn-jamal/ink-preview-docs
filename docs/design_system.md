# InkPreview Design System Specification v1.0

## 1. Visual Philosophy: "Ink & Obsidian"

### Core Aesthetic
The "Ink & Obsidian" philosophy is designed to position InkPreview as a premium, luxury tool for tattoo enthusiasts and professionals. Moving away from generic Material or Cupertino looks, this system emphasizes high contrast, depth, and a "dark-room" studio atmosphere.

**Key Principles:**
- **Art-Centric**: The UI recedes to let the tattoo artwork be the primary focus.
- **Depth & Dimension**: Extensive use of glassmorphism and subtle shadows to create a tactile, layered experience.
- **Luxury Minimalism**: Clean lines, generous whitespace (breathing room), and high-end typography.
- **Obsidian Foundations**: A palette rooted in deep blacks and charcoal greys to evoke sophistication and permanence.

---

## 2. Color Palette

### Foundation Colors
| Role | Hex Code | Usage | WCAG Contrast |
| :--- | :--- | :--- | :--- |
| **Obsidian Black** | `#0A0A0A` | Main Background, Deepest Shadows | Pass (AAA) |
| **Steel Grey** | `#1C1C1E` | Secondary Surfaces, Cards, Modals | Pass (AA) |
| **Charcoal** | `#2C2C2E` | Disabled States, Subtle Dividers | Pass (AA) |

### Accent Colors
| Role | Hex Code | Usage | Note |
| :--- | :--- | :--- | :--- |
| **Liquid Gold** | `#D4AF37` | Primary CTA, High-Value Highlights | High contrast against black |
| **Silver Mist** | `#C0C0C0` | Secondary Icons, Accents | Neutral luxury feel |
| **Pure White** | `#FFFFFF` | Primary Text, Key Icons | Maximum readability |
| **Soft Grey** | `#A0A0A0` | Secondary Text, Captions | Reduced visual weight |

### Semantic Colors
- **Error**: `#FF453A` (Vibrant Red)
- **Success**: `#32D74B` (Emerald Green)
- **Warning**: `#FFD60A` (Caution Yellow)

---

## 3. Typography

### Font Pairings
- **Display/Headings**: `Playfair Display` (Serif) - Evokes elegance, craftsmanship, and tradition.
- **UI/Body**: `Inter` (Sans-Serif) - Ensures maximum readability, modern feel, and precision.

### Type Scale
| Level | Font | Weight | Size | Line Height | Letter Spacing |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **H1** | Playfair Display | Bold | 32px | 40px | -0.5px |
| **H2** | Playfair Display | Semi-Bold | 24px | 32px | -0.2px |
| **H3** | Inter | Bold | 20px | 28px | 0px |
| **Body L** | Inter | Regular | 16px | 24px | 0px |
| **Body M** | Inter | Regular | 14px | 20px | 0px |
| **Caption** | Inter | Medium | 12px | 16px | 0.5px |
| **Overline** | Inter | Bold | 10px | 12px | 1.2px (All Caps) |

---

## 4. Glassmorphism & Effects

To achieve the "Premium" feel, the app avoids flat surfaces in favor of translucent, blurred layers.

### The "Obsidian Glass" Spec
- **Fill**: `rgba(255, 255, 255, 0.05)`
- **Backdrop Blur**: `20px`
- **Border**: `1px solid rgba(255, 255, 255, 0.12)`
- **Inner Glow**: Top-left `1px` highlight `rgba(255, 255, 255, 0.2)`

### Shadows & Elevation
- **Low Elevation**: `0px 4px 12px rgba(0, 0, 0, 0.5)`
- **High Elevation**: `0px 12px 32px rgba(0, 0, 0, 0.8)`
- **Glow Effect (Accents)**: `0px 0px 15px rgba(212, 175, 55, 0.3)` for Liquid Gold elements.

---

## 5. Component Library

### Buttons
- **Primary Button**: 
    - Background: Linear Gradient (`#D4AF37` $\rightarrow$ `#B8860B`)
    - Text: Obsidian Black, Semi-Bold, 16px
    - Corner Radius: `12px`
    - Shadow: Liquid Gold Glow.
- **Secondary Button**:
    - Background: Transparent
    - Border: `1px solid #C0C0C0`
    - Text: Silver Mist, Medium, 16px
    - Corner Radius: `12px`

### Cards
- **Artwork Card**: 
    - Style: Obsidian Glass
    - Padding: `16px`
    - Corner Radius: `24px`
    - Interaction: Scale up (1.02x) on tap.

### Input Fields
- **Style**: Minimalist
- **State (Idle)**: Bottom border only (`1px solid #2C2C2E`), Text `#A0A0A0`.
- **State (Active)**: Bottom border (`2px solid #D4AF37`), Text `#FFFFFF`.
- **Placeholder**: `Inter Regular, 14px, #666666`.

### Navigation
- **Nav Bar**: 
    - Style: Obsidian Glass (Fixed Bottom)
    - Height: `84px` (including safe area)
    - Icons: Silver Mist (Inactive) $\rightarrow$ Liquid Gold (Active).

---

## 6. Layout & Grid

### Spacing System
Based on an **8px baseline grid** to ensure mathematical harmony.
- **xs**: 4px
- **sm**: 8px
- **md**: 16px
- **lg**: 24px
- **xl**: 32px
- **xxl**: 48px
- **huge**: 64px

### Grid & Margins
- **Side Margins**: `24px` (Standard for mobile)
- **Vertical Spacing**: `24px` between major sections.
- **Component Gap**: `16px` between related elements.

### Responsive Behavior
- **Compact (Small Phones)**: Reduce margins to `16px`, H1 to `28px`.
- **Expanded (Large Phones/Tablets)**: Maximum content width `600px` (centered), increase margins to `32px`.
