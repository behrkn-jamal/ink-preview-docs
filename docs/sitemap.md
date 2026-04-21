# Ink Preview: Mobile App Sitemap & User Flows

This document outlines the information architecture and primary user journeys for the Ink Preview mobile application.

## 1. App Sitemap

The sitemap represents the hierarchical structure of the application, mapping all primary and secondary screens.

### Root Navigation (Bottom Nav)
- **Home**
    - Dashboard
    - Recent Projects (Grid/List)
    - New Project Trigger $\rightarrow$ *Redirects to Editor*
- **Gallery**
    - Discovery Feed
    - Search Interface
    - Category Filters (Realism, Traditional, Minimalist, Neo-Tribal, etc.)
    - Artwork Detail View
        - Save to Favorites
        - Use in Editor $\rightarrow$ *Redirects to Editor*
- **Editor**
    - Project Canvas
    - Toolset Panel
        - Placement/Transform Tools
        - Opacity & Blend Mode Controls
        - Rotation & Scale
    - Asset Library Drawer
        - Recent Uploads
        - Gallery Presets
        - Custom Brush/Upload
    - Export/Save Flow
- **Profile**
    - User Dashboard
    - Saved Artwork Gallery
    - My Projects
    - **Settings**
        - Account Management
        - App Preferences (Units, Theme)
        - Support & Help
        - Legal / Privacy Policy

### Auxiliary Screens
- **Onboarding**
    - Splash Screen
    - Welcome Walkthrough (Value Proposition)
    - Authentication (Login/Sign-up/Guest)
- **Notifications**
    - Alert Feed
    - Notification Settings

---

## 2. Primary User Flows

### Flow A: Creating a New Mockup (The "Quick Start")
**Goal**: Visualize a tattoo design on a body part from scratch.
`Home` $\rightarrow$ `Tap 'Start New Project'` $\rightarrow$ `Editor (Canvas)` $\rightarrow$ `Select Asset/Upload Image` $\rightarrow$ `Adjust Placement/Opacity` $\rightarrow$ `Tap 'Export'` $\rightarrow$ `Save to Device/Share`.

### Flow B: Inspiration to Execution
**Goal**: Find a design in the gallery and immediately see how it looks on skin.
`Gallery` $\rightarrow$ `Browse/Search for Design` $\rightarrow$ `Tap Artwork Detail` $\rightarrow$ `Tap 'Try it on'` $\rightarrow$ `Editor (Canvas)` $\rightarrow$ `Adjust Transform` $\rightarrow$ `Tap 'Export'`.

### Flow C: Managing Saved Projects
**Goal**: Review and refine a previously saved mockup.
`Profile` $\rightarrow$ `My Projects` $\rightarrow$ `Select Project` $\rightarrow$ `Editor (Canvas)` $\rightarrow$ `Modify Design` $\rightarrow$ `Save Changes`.

### Flow D: User Personalization
**Goal**: Update profile and app preferences.
`Profile` $\rightarrow$ `Settings` $\rightarrow$ `Account/Preferences` $\rightarrow$ `Modify Value` $\rightarrow$ `Save/Auto-save`.

---

## 3. Architecture Notes
- **Navigation Pattern**: The app uses a persistent Bottom Navigation Bar for top-level switching.
- **Contextual Overlays**: The Editor utilizes slide-up drawers (Asset Library) and floating panels (Toolset) to maximize canvas real estate.
- **State Management**: The 'Export' action in the Editor triggers a modal for choosing quality and format before final save.
