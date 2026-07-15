---
version: alpha
name: Nexus AI Cinematic Agents Template
description: A cinematic, high-density cinematic experience for AI agent systems, featuring complex scroll-driven narratives, WebGL-enhanced layers, and a high-contrast dark aesthetic.
colors:
  primary: "#f5b8d0"
  secondary: "#1a1a1a"
  accent: "#c26a97"
  background: "#0a0a0c"
  surface: "#1a1a1a"
  text-primary: "#f4f2ef"
  text-muted: "#b8b4ae"
  border: "rgba(255,255,255,0.06)"
typography:
  fontFamily: "sans-serif, Inter"
  headings:
    weight: 500
    lineHeight: 0.95
    letterSpacing: "-0.025em"
  body:
    size: "14px"
    weight: 400
    lineHeight: 1.5
  mono-caps:
    size: "12px"
    letterSpacing: "0.35rem"
spacing:
  container: "77.5rem"
  section-py: "6rem"
rounded:
  card: "1rem"
  button: "9999px"
components:
  button-primary:
    bg: "#ededed"
    text: "#1a1a1a"
    shadow: "inset 0 1px 0 rgba(255,255,255,0.8)"
  card-glass:
    bg: "rgba(255,255,255,0.04)"
    border: "1px solid rgba(255,255,255,0.06)"
    blur: "12px"
---

## Overview
Nexus AI presents a "Cinematic AI Agents Experience" defined by atmospheric density, high-contrast monochrome palettes with soft pink accents, and a vertical narrative driven by precision scrolling. The visual language is technical yet ethereal, utilizing cinematic letterboxing, grain-like grid patterns, and delicate line-work brackets. The interface feels like a sophisticated terminal mixed with a filmic presentation, emphasizing "Quiet Nodes" and "Connected Swarms."

## Colors
The palette is rooted in an ultra-dark grey (`#0a0a0c`), avoiding pure black to maintain depth. Highlights use a soft, desaturated pink (`#f5b8d0`) for technical data and status indicators. Surface materials are semi-transparent with heavy backdrop blurring. A secondary section utilizes a high-contrast warm cream/off-white (`#f4efe7`) with deep indigo and rose radial gradients to shift the tone during the manifesto portion.

## Typography
Typography is dominated by sans-serif faces (Inter/system-sans) with varying weights. Headings use tight line-heights (0.95 to 1.1) and clamp-based fluid sizing. A distinctive "technical subhead" style exists using small caps with extreme letter-spacing (up to 0.35rem) in primary pink. Numbers are tabular where displayed in the HUD to ensure alignment during animation.

## Layout
The site uses a strictly centered container constraint of 77.5rem (1240px). The core of the experience is a pinned, full-viewport stage that occupies 820vh of scroll progress. Subsequent sections use traditional CSS grids (1-column to 3-column) and flex-based headers/footers. Layout density is airy, with significant negative space between technical blocks.

## Elevation & Depth
Depth is achieved through layering rather than traditional shadows. The hierarchy includes:
1.  **Background Layer:** Fixed canvas with Three.js particles and desaturated image backgrounds.
2.  **Mid-Layer:** Floating subject assets (bouquet/tech objects) with CSS parallax transforms.
3.  **UI Overlay:** Fixed navigation and HUD-style timeline trackers.
4.  **Foreground:** Animated text "beats" and WebGL petal particles.
Cards use a subtle 1px border and low-opacity white backgrounds to suggest glass surfaces.

## Shapes
Rounded corners are used deliberately: 1rem (16px) for cards and full pill-shapes (9999px) for buttons. However, these are contrasted by sharp, 90-degree technical corner brackets (1.375rem size) that frame the main viewport, providing a "camera lens" or "targeting system" feel.

## Components
### Navigation Bar
A fixed-position header with `backdrop-filter: blur(12px)`. It features a minimal logo, links with 300ms hover transitions, and a pill-shaped primary action button with an inner white highlight.

### Agent Cards
Vertical 4:5 aspect ratio image containers with rounded corners. They include a glass-morphism hover state where the background brightness shifts. Content is bottom-aligned with a primary-colored price tag.

### Timeline HUD
A left-aligned UI element consisting of a 11.25rem track with a gradient fill (`#f5b8d0` to `#c26a97`) and a tabular-numeric label. On the right, a row of dots acts as both a progress indicator and interactive navigation.

### Metric Blocks
High-contrast articles with either black backgrounds/white text or vibrant rose backgrounds. They feature large, bold headings and 0.75rem technical labels.

## Page Sections
### Cinematic Hero (Pinned Stage)
A massive scroll-controlled area. It transitions through 7 distinct "beats" of content. Visually, it features cinematic letterbox bars that grow/shrink based on scroll depth. A central asset (bouquet) scales and rotates using GSAP/ScrollTrigger. A WebGL canvas renders pink particles that drift based on a simulated wind amount linked to scroll velocity.

### Collection Section
A 3-column grid of AI agents. The section is overlaid with a repeating linear gradient grid (45-degree angle) at 1.5% opacity. Headers use a masked reveal animation where text rises from an invisible container.

### Craft Parallax Strip
A 70vh tall section with a background image set to `inset: -15%`. It uses a scrubbed parallax effect to move the background independently of the text overlay, creating a sense of scale and immersion.

### Manifesto & Board
A high-contrast break from the dark theme. Uses a cream background (`#f4efe7`) and large, uppercase typography. This transitions into a "Models" board where a massive "MODELS" watermark sits behind a grid of active status cards.

## Motion & Interaction
-   **Scroll-Driven Orchestration:** Most animations are tied to `renderP` (render progress) calculated from scroll position.
-   **Velocity-Aware Interpolation:** Changes in scroll speed affect the intensity of WebGL particle drift and CSS transitions.
-   **Masked Reveals:** Text elements use `overflow-hidden` containers and `yPercent` shifts to reveal on enter.
-   **Parallax Layers:** Backgrounds use a -15% offset with `will-change: transform` to facilitate smooth vertical movement.
-   **Micro-interactions:** Navigation links and buttons use 300ms cubic-bezier transitions for color and background shifts.

## Do's and Don'ts
-   **Do:** Use high letter-spacing for all uppercase sub-labels.
-   **Do:** Maintain the cinematic letterboxing (lbTop/lbBot) for focal hero moments.
-   **Do:** Keep the pink accent limited to technical data and interactive triggers.
-   **Don't:** Use solid black backgrounds; stick to desaturated dark grey (`#0a0a0c`).
-   **Don't:** Introduce heavy box shadows; rely on borders and blurs for separation.

## Accessibility
-   **Prefers-Reduced-Motion:** The codebase contains a `reduce` check that disables WebGL petal rendering and GSAP reveals if the user has motion restrictions enabled.
-   **Semantic Contrast:** While the aesthetic is dark, high-contrast text (`#f4f2ef`) is maintained against dark backgrounds.
-   **Aria Roles:** The background particle canvas is explicitly marked `aria-hidden="true"`.

## Assets
1.  **Tailwind CSS:** https://cdn.tailwindcss.com
2.  **Iconify Library:** https://code.iconify.design/iconify-icon/1.0.7/iconify-icon.min.js
3.  **GSAP Core:** https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js
4.  **GSAP ScrollTrigger:** https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/ScrollTrigger.min.js
5.  **Google Tag Manager:** https://www.googletagmanager.com/gtag/js?id=G-2M6V79H761
6.  **Central Asset (Bouquet):** https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/d0f628cf-26bf-473d-81b9-50e422c51521_3840w.png
7.  **Data Harvester Image:** https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/4dd5a8b0-2d0d-44eb-ae24-75a4345db5ac_3840w.png
8.  **Neural Orchestrator Image:** https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/d898f02c-0397-49fe-9aca-cab19a5582c5_3840w.png
9.  **Logic Synthesizer Image:** https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/25d0ce5e-7521-4346-900f-d2ff2902bd46_3840w.png
10. **Architecture Background:** https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/cf973fee-26dd-4029-b42e-26dfa75c7417_3840w.png

### Exported Codebase Asset Inventory
1. other: &quot;https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/d0f628cf-26bf-473d-81b9-50e422c51521_3840w.png&quot;
   Context: index.html: css url()
