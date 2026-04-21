# Tatship Competitive Analysis - InkPreview Research

## Overview
Tatship is a comprehensive tattoo planning platform that combines AI generation, AR try-on technology, and artist discovery to help users visualize tattoos before committing to permanent ink.

## 1. Core Feature Set

### Visualization & Try-On
- **AR Camera Overlay**: Real-time preview of tattoo designs on the user's body using the device camera.
- **3D Try-On Technology**: Advanced mapping that adapts the tattoo design to the contours and curves of the body for higher realism.
- **Photo-Based Mockups ("Tattoo My Photo")**: Ability to upload a static photo and overlay designs to test placement and size.
- **Realistic Effects**: Blend modes and filters to simulate how ink looks on skin (opacity, shading).

### Design & Creation
- **AI Tattoo Generator**: Text-to-image generation allowing users to create unique designs via keywords.
- **Custom Uploads**: Import personal images or screenshots and convert them into "ink-ready" designs.
- **Tattoo Photo Editor**: Tools to refine uploaded images into tattoo stencils.
- **Tattoo Font Generator**: Specialized tool for converting text into various tattoo-style typography.
- **Sketching Tools**: In-app designer tools for creating original artwork from scratch.

### Discovery & Planning
- **Tattoo Library/Gallery**: A massive repository of designs filterable by style, meaning, and body part.
- **Favorites/Saved References**: Ability to save designs and "try-on" results for later review.
- **Artist Marketplace**: Integrated search to find local tattoo artists, view portfolios, and book appointments.

---

## 2. User Flow Analysis

**Typical User Journey:**
1. **Inspiration Phase**: 
   - User browses the `Tattoo Ideas Gallery` $\rightarrow$ filters by "Minimalist" $\rightarrow$ saves a favorite.
   - *OR* User uses the `AI Generator` $\rightarrow$ enters "Cyberpunk Dragon" $\rightarrow$ selects a generated image.
2. **Visualization Phase**:
   - User selects `Try-On` $\rightarrow$ opens camera $\rightarrow$ positions the design on their forearm.
   - User applies `3D Adaptation` to ensure the design wraps correctly around the arm.
   - User adjusts size and rotation via on-screen controls.
3. **Validation Phase**:
   - User takes a screenshot or saves the mockup.
   - User compares different placements (e.g., wrist vs. forearm) by saving multiple trials.
4. **Execution Phase**:
   - User uses the `Artist Finder` $\rightarrow$ searches for "Realism artists" in their city $\rightarrow$ shares the mockup with the artist to communicate the exact vision.

---

## 3. Value Proposition
- **Risk Mitigation**: Solves the "tattoo regret" pain point by providing a safe, virtual environment to experiment with size and placement.
- **Communication Bridge**: Reduces friction between client and artist by providing a precise visual reference instead of vague descriptions.
- **Creative Empowerment**: Lowers the barrier to design by providing AI tools for those who aren't artists but have a vision.

---

## 4. UX/UI Patterns
- **Manipulation Controls**:
    - **Pinch-to-Zoom/Rotate**: Standard gestures for adjusting tattoo scale and angle.
    - **Sliders**: Likely used for adjusting opacity and blend levels to match skin tone.
    - **Automated Wrapping**: 3D technology that handles the perspective distortion of the body surface.
- **Discovery UI**:
    - **Category-based Filtering**: Efficient navigation through large libraries.
    - **Visual Grid**: High-density image gallery for rapid inspiration.
- **Conversion Path**:
    - Seamless transition from "Design" $\rightarrow$ "Try-On" $\rightarrow$ "Book Artist".

---

## 5. Gap Analysis & Opportunities for InkPreview

| Tatship Limitation / Gap | InkPreview Opportunity (Competitive Advantage) |
| :--- | :--- |
| **Design Management**: Users report difficulty deleting old designs or organizing saved trials. | **Advanced Library Management**: Implement robust folders, tagging, and a "Trash/Archive" system for designs. |
| **Artist Integration**: Primary focus is on finding artists, not collaborating with them. | **Collaborative Canvas**: Allow artists to open a user's "InkPreview Project" and make professional tweaks in real-time. |
| **Platform Reach**: Focused heavily on mobile/iPad; lack of professional desktop tools. | **Cross-Platform Sync**: A powerful desktop app for artists to refine mockups, synced with a mobile app for users to "try on". |
| **Feedback Loop**: No built-in way to get community or professional feedback on a mockup. | **Social Validation**: Integration for users to share mockups to a community "Vote" board to decide between two designs. |
| **Stencil Accuracy**: Basic photo-to-stencil conversion. | **Pro-Grade Stencil Export**: Generate precise, printable PDF stencils with scale markers for the artist. |
