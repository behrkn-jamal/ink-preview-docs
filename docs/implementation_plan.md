# InkPreview — Flutter Tattoo Mockup App

A Flutter app that lets users visualize tattoo designs on their body by overlaying tattoo images onto body photos with interactive manipulation.

## User Review Required

> [!IMPORTANT]
> **Platform targets**: Planning for **iOS and Android**. Let me know if you also need web or desktop support.

> [!IMPORTANT]
> **Tattoo design source**: The initial version will include a built-in gallery of sample tattoo designs (bundled as assets) plus the ability to import custom designs from the device gallery. Do you also want AI-generated tattoo designs (would require an API key)?

> [!IMPORTANT]
> **Complexity level**: I'm proposing a **custom-built editor** (using Flutter's `Stack`, `GestureDetector`, and `InteractiveViewer`) rather than relying on `pro_image_editor`. This gives us full control over the UX tailored specifically for tattoo mockups — a simpler, more focused experience. If you'd prefer the full-featured image editor approach, let me know.

## App Overview

**InkPreview** — "See it before you ink it"

### Core User Flow
1. **Home Screen** → Browse recent mockups or start new one
2. **Select Body Photo** → Camera or gallery
3. **Tattoo Editor** → Place tattoo on body with full manipulation
4. **Preview & Export** → Save to gallery or share

---

## Proposed Architecture

```
lib/
├── main.dart
├── app.dart                          # MaterialApp + theme + routing
├── theme/
│   ├── app_theme.dart                # Dark theme with premium styling
│   └── app_colors.dart               # Color palette
├── models/
│   ├── tattoo_design.dart            # Tattoo design data model
│   ├── mockup_project.dart           # Saved project model
│   └── tattoo_layer.dart             # Layer state (position, scale, rotation, opacity)
├── screens/
│   ├── home/
│   │   └── home_screen.dart          # Main landing screen
│   ├── gallery/
│   │   └── tattoo_gallery_screen.dart # Browse tattoo designs
│   ├── editor/
│   │   ├── editor_screen.dart        # Main tattoo placement editor
│   │   ├── widgets/
│   │   │   ├── tattoo_canvas.dart    # Stack-based canvas with body + tattoos
│   │   │   ├── tattoo_layer_widget.dart # Individual draggable/scalable tattoo
│   │   │   ├── editor_toolbar.dart   # Bottom toolbar (opacity, flip, delete, etc.)
│   │   │   └── blend_mode_picker.dart # Blend mode selection for realism
│   │   └── controllers/
│   │       └── editor_controller.dart # State management for the editor
│   └── preview/
│       └── preview_screen.dart       # Full-screen preview + export
├── services/
│   ├── image_service.dart            # Pick, crop, and process images
│   └── export_service.dart           # Render composite image & save to gallery
├── widgets/
│   ├── glassmorphic_card.dart        # Reusable glass-style card
│   └── gradient_button.dart          # Styled CTA button
└── utils/
    └── constants.dart                # Asset paths, strings
```

---

## Proposed Changes

### 1. Project Setup

#### [NEW] Flutter project initialization
- Create Flutter project with `flutter create` in the workspace
- Target: iOS + Android
- Minimum SDK: Flutter 3.x stable

#### [NEW] `pubspec.yaml`
Key dependencies:
| Package | Purpose |
|---|---|
| `image_picker` (^1.2.1) | Select body photos from camera/gallery |
| `image_gallery_saver_plus` (latest) | Save final mockup to device gallery |
| `path_provider` | Local file storage paths |
| `share_plus` | Share mockup images |
| `google_fonts` | Premium typography (Inter, Outfit) |
| `flutter_animate` | Smooth micro-animations |
| `uuid` | Unique IDs for layers/projects |
| `permission_handler` | Camera/storage permissions |

---

### 2. Theme & Design System

#### [NEW] `lib/theme/app_theme.dart`
- **Dark mode primary** with vibrant accent colors
- Glassmorphism-inspired cards and surfaces
- Color palette: Deep charcoal background (#0D0D0D), accent gradient (electric purple → hot pink)
- Typography: Google Fonts "Outfit" for headings, "Inter" for body
- Rounded corners, subtle shadows, frosted-glass effects

#### [NEW] `lib/theme/app_colors.dart`
- Curated tattoo-studio-inspired palette
- Surface colors with varying opacity for glass effects

---

### 3. Home Screen

#### [NEW] `lib/screens/home/home_screen.dart`
- Hero section with app branding and tagline
- "New Mockup" CTA button (gradient, animated)
- Recent mockups grid (if any saved)
- Bottom navigation or simple flow-based navigation

---

### 4. Tattoo Design Gallery

#### [NEW] `lib/screens/gallery/tattoo_gallery_screen.dart`
- Grid of built-in tattoo designs organized by category (tribal, floral, geometric, minimal, lettering)
- Import custom design button (from device gallery)
- Tattoo thumbnail preview cards with glassmorphic styling
- Category filter chips at top

#### [NEW] `assets/tattoos/` directory
- Bundle 10-15 sample tattoo PNG designs (transparent background)
- Generated using the image generation tool

---

### 5. Tattoo Editor (Core Feature)

#### [NEW] `lib/screens/editor/editor_screen.dart`
Main editor screen layout:
- Full-screen body image as background
- Tattoo overlays rendered on top via `Stack`
- Bottom toolbar for controls
- Top bar with undo/done actions

#### [NEW] `lib/screens/editor/widgets/tattoo_canvas.dart`
- Uses `Stack` + `InteractiveViewer` for zoom/pan of the body image
- Renders `TattooLayerWidget` for each placed tattoo
- Handles coordinate system for accurate placement

#### [NEW] `lib/screens/editor/widgets/tattoo_layer_widget.dart`
Core interaction widget:
- **Drag**: `GestureDetector.onPanUpdate` for repositioning
- **Scale**: Pinch-to-zoom via `ScaleGestureRecognizer`
- **Rotate**: Two-finger rotation
- **Selection handles**: Show resize/rotate handles when selected
- **Opacity**: Adjustable via slider
- **BlendMode**: Apply `multiply`, `softLight`, or `overlay` for realistic skin blending
- **Flip**: Horizontal mirror for symmetry

#### [NEW] `lib/screens/editor/widgets/editor_toolbar.dart`
Bottom controls:
- Opacity slider
- Blend mode toggle
- Flip horizontal/vertical
- Duplicate layer
- Delete layer
- Add another tattoo button

#### [NEW] `lib/screens/editor/controllers/editor_controller.dart`
- `ChangeNotifier`-based state management
- Manages list of `TattooLayer` objects
- Handles selection, undo stack
- Coordinates between canvas and toolbar

---

### 6. Models

#### [NEW] `lib/models/tattoo_design.dart`
```dart
class TattooDesign {
  final String id;
  final String name;
  final String category;
  final String assetPath; // or file path for custom
  final bool isCustom;
}
```

#### [NEW] `lib/models/tattoo_layer.dart`
```dart
class TattooLayer {
  String id;
  TattooDesign design;
  Offset position;
  double scale;
  double rotation;
  double opacity;
  BlendMode blendMode;
  bool isFlippedX;
  bool isFlippedY;
}
```

---

### 7. Preview & Export

#### [NEW] `lib/screens/preview/preview_screen.dart`
- Full-screen final render (no handles/UI overlay)
- Before/After toggle (show original body photo vs with tattoo)
- Save to gallery button
- Share button

#### [NEW] `lib/services/export_service.dart`
- Uses `RenderRepaintBoundary` + `toImage()` to capture the composite
- Saves via `image_gallery_saver_plus`
- Supports high-res export

---

### 8. Sample Tattoo Assets

I will generate ~8-10 tattoo design PNGs using the image generation tool:
- Tribal arm band
- Rose/floral design
- Geometric mandala
- Compass/nautical
- Dragon
- Minimalist line art
- Script/lettering style
- Skull design

---

## Open Questions

> [!IMPORTANT]
> 1. **Platform**: iOS + Android only, or do you also need web support?
> 2. **State management**: I'm proposing simple `ChangeNotifier` + `Provider`. Would you prefer Riverpod, BLoC, or another approach?
> 3. **Persistence**: Should mockups be saveable as projects (to re-edit later), or just export-and-forget?
> 4. **AI generation**: Do you want an AI tattoo design generator feature (text-to-tattoo)? This would require an API integration.
> 5. **Body part templates**: Should we include stock body-part images (arm, back, leg, etc.) in addition to camera/gallery photos?

---

## Verification Plan

### Automated Tests
- Run `flutter analyze` to ensure no lint errors
- Run `flutter build ios --no-codesign` and `flutter build apk` to verify builds

### Manual Verification
- Launch on iOS Simulator / Android Emulator
- Test the full flow: open app → select body image → add tattoo → manipulate → export
- Verify gesture controls (drag, scale, rotate) are smooth
- Verify export saves correctly to device gallery
- Test with various image sizes and orientations
