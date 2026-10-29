# Orvante — Monochrome Editorial Branding Agency Landing Page

An art-directed, three-section monochrome editorial landing page for the fictional branding agency **Orvante**, built with precision proportional scaling (`u` units on a 1440px artboard), scroll-driven typography, Web Animations load choreography, and an interactive call-booking modal.

## User Review & Critical Decisions

> [!IMPORTANT]
> The following interactive behaviors have been confirmed and integrated alongside the exact artboard coordinates, media assets, and animation timings from your specification:

- **Confirmed Decision 1 — Navigation Pill Interaction**: Clicking **Home**, **Studio**, **Works**, or **Blog** smoothly scrolls to the corresponding section of the page and updates the active black sliding pill indicator, while hovering slides the black pill dynamically to preview the hovered link.
- **Confirmed Decision 2 — Call-Booking & Inquiry Modal**: Clicking **Contact Us ↗** or **Book A Call ↗** (including the stats card bar and brand plate menu) opens a strict monochrome editorial inquiry and call-booking modal with form validation and instant confirmation state.
- **Single-File Architecture Option**: While hosted inside the Vite environment so the preview server runs seamlessly on port 3000, the entire application can be delivered directly as a self-contained plain HTML, CSS, and vanilla JS implementation in the root entry file with zero external framework overhead.

---

## 1. Overview & Core Concept

- **What It Does**: Presents Orvante's agency positioning through three tightly choreographed sections:
  1. **Light Grey Editorial Hero (`938u` tall)**: Features a centered black-and-white studio portrait masked into a `#dadada` paper canvas, overlaid with the frosted dark glass `ORVANTE` brand plate, `PURE / DESIGN ('25)` display typography, segmented sliding navigation pill, live partner/project counters (`400+` and `230+`), and the `Q Industrial [2025]` release showcase.
  2. **Divider Bar & Scroll-Fill Manifesto (`111u` bar + statement section)**: A pure black `#000000` canvas headed by a wide Archivo metadata bar (`EST 2019`, `SCROLL DOWN`, `LIVE IN DETAILS`), followed by a 5-line strategic manifesto where every individual word transitions smoothly from `#6f6f6f` to `#f4f4f4` in reading order with a 3-word soft gradient edge as the user scrolls.
  3. **Bordered Trust Panel (`1302 × 429u`)**: A `1px` white-bordered (`28%` opacity) showcase panel featuring overlapping frosted glass icon tiles (`*` asterisk and 4-dot grid) over the `"Trusted by Hundreds of Growing Businesses"` heading, paired with three horizontal stat/media cards (`56M+ Global Collaborations` with an 8-avatar grid, `10+ Industry Awards` with an SVG laurel badge, and an edge-cropped portrait card).
- **Target Audience / Persona**: Design-forward brand founders, marketing directors, and creative leads evaluating Orvante for brand strategy, digital identity, and high-converting web execution.
- **Key Value**: Combines Swiss-inspired editorial precision (`u`-unit artboard geometry) with tactile motion choreography (load reveals, parallax drift, scroll-linked word illumination, and time-based `?rec=1` recorder playback).

---

## 2. User Experience & Visual Design

### Key User Flows
1. **Initial Arrival & Load Choreography**:
   - The `PURE / DESIGN` headline lines rise out of overflow masks over `1000ms` (staggered by `110ms`).
   - The central studio portrait rises `40px`, un-blurs, and fades in over `1300ms`.
   - The segmented navigation pill drops into place while surrounding hero modules rise `14px` and fade in at `55ms` stagger intervals.
   - The `400+` and `230+` partner/project counters count up over `1400ms`, and the `Q Industrial` progress bar draws across.
2. **Navigation & Exploration**:
   - Hovering over **Home**, **Studio**, **Works**, or **Blog** glides the black pill background smoothly behind the hovered item; moving the cursor away returns it to the active item.
   - Clicking a link locks the active state and smoothly scrolls to the mapped section (**Home** → Hero, **Studio** → Manifesto & Bar, **Works** → Q Industrial / Stats showcase, **Blog** → Trust Panel & Awards).
3. **Scroll Progression**:
   - As the user scrolls, the hero portrait drifts vertically at `0.12×` scroll speed.
   - Entering the black statement section illuminates each word span from `#6f6f6f` to `#f4f4f4` with a 3-word soft interpolation window.
   - When the Trust Panel enters the viewport, `56M+` and `10+` count up from zero while the 8 monochrome circular avatars pop in (`scale(0.4)` → `scale(1)`, staggered).
4. **Booking a Call / Inquiry Modal**:
   - Clicking **Contact Us ↗** or **Book A Call ↗** opens a monochrome glass/obsidian modal dialog allowing the visitor to select a project scope (Brand Strategy, Web Architecture, Campaign Growth), pick a preferred date/time window, enter their name and work email, and submit with instant visual confirmation.

### Visual Identity & Theme
- **Aesthetic Direction**: Strict monochrome Swiss/editorial minimalism—high contrast between warm-neutral stone paper (`#dadada`) in the upper canvas and deep obsidian (`#000000`) below the fold, punctuated by frosted glass plates and hairline rules.
- **Color Palette & Mood**:
  - Hero Paper Canvas: `#dadada` with `#111111` primary ink and `#cdcdcd` stats container surface.
  - Lower Sections Canvas: Pure black `#000000` with `#f4f4f4` primary text and `#6f6f6f` muted/unfilled statement text.
  - Card Surfaces: `#d6d6d6` (light grey avatar card), `#262626` (dark charcoal awards card), and frosted glass (`backdrop-filter: blur(...)` with translucent dark/light fills).
  - Hairlines & Borders: `rgba(255, 255, 255, 0.14)` to `rgba(255, 255, 255, 0.28)`.
- **Typography & Hierarchy**:
  - **Display & Brand (`Archivo` variable width `wdth 62..125`, `wght 100..900`)**:
    - `"PURE DESIGN"`: `font-variation-settings: 'wdth' 104, 'wght' 640`, size `90u`, line-height `0.86`, letter-spacing `-0.06em`.
    - `"ORVANTE"` brand plate & divider bar labels (`EST 2019`, `SCROLL DOWN`, `LIVE IN DETAILS`): Wide `Archivo` (`25u` on plate, `14u` on bar).
  - **UI & Editorial Body (`Inter Tight` variable `wght 100..900`)**:
    - UI labels, navigation, and cards: `13u–15u`, weight `500`.
    - Manifesto statement: `52u` (`28u` on mobile), line-height `1.33`, tracking `-0.028em`.
    - Trust heading: `55u`, weight `500`, paired with `14.5u` body copy.
- **Component Styling & Spatial Math**:
  - **Desktop Artboard (`> 760px`)**: `u = min(100vw / 1440, 1.333px)`. Every coordinate (`left`, `top`, `width`, `height`, `font-size`, `border-radius`) scales proportionally in `calc(N * var(--u))`.
  - **Phone Artboard (`≤ 760px`)**: `u = 100vw / 390`. Reflows into a clean single-column vertical sequence with zero horizontal overflow (`overflow-x: hidden`), converting the top-right Contact button into a `40u` square arrow button and stacking the hero copy, `470u` full-width portrait with overlaid brand plate/logos, True Growth pill, 2-column stats frame, Out Now card, `28u` statement, and stacked Trust Panel cards (hiding the second glass tile).

---

## 3. Key Product Decisions & Trade-Offs

- **Decision 1 — Pure Vanilla HTML/CSS/JS Execution Inside the App Entry**:
  - *Chosen Approach*: Implement the entire page using plain HTML markup, CSS custom properties (`--u`), and vanilla JavaScript (Web Animations API, `IntersectionObserver`, `requestAnimationFrame` scroll loop) directly in the page entry without React component overhead.
  - *Why*: Directly fulfills the prompt requirement for plain HTML, CSS, and vanilla JS with no framework abstractions, ensuring exact DOM structure, deterministic Web Animations timing, and instant `?rec=1` recorder mode playback.
  - *Alternatives Considered*: Wrapping sections in React components was passed over because direct DOM manipulation and native Web Animations match the specification's exact single-file vanilla architecture.
- **Decision 2 — Deterministic Recorder Mode (`?rec=1`) & Reduced Motion**:
  - *Chosen Approach*: Inspect `new URLSearchParams(location.search).get('rec') === '1'` and `window.matchMedia('(prefers-reduced-motion: reduce)')` on startup.
  - *Why*: When `?rec=1` is active, scroll listeners are replaced by a deterministic timeline (`1.3s–4.2s` statement word fill, `3.5s–5.2s` trust counters and avatar pop-ins, `5.3s` awards card lift, plus continuous slow photo drift). When `prefers-reduced-motion` is enabled, all words start fully white (`#f4f4f4`) and all counters display their final numbers immediately.

---

## 4. Technical Architecture & Data Strategy *(Technical Reference)*

### Architecture & Component Diagram

```
┌──────────────────────────────────────────────────────────────────────────────┐
│                     ORVANTE LANDING PAGE (1440u Artboard)                    │
├──────────────────────────────────────────────────────────────────────────────┤
│  CSS Scale Engine:  --u = min(100vw / 1440, 1.333px) | Mobile: 100vw / 390   │
└───────────────┬──────────────────────────────────────────────┬───────────────┘
                │                                              │
                ▼                                              ▼
┌───────────────────────────────────────────┐  ┌───────────────────────────────┐
│        VISUAL SECTIONS & DOM TREE         │  │   MOTION & INTERACTION ENGINE │
├───────────────────────────────────────────┤  ├───────────────────────────────┤
│ 1. HERO SECTION (1440 × 938u, #dadada)    │  │ • Load Choreography (WAAPI)   │
│    ├─ Segmented Nav Pill (57, 61)         │◄─┤   - Title line mask rise (1s) │
│    ├─ Date & Contact Us ↗ (1038 / 1237)   │  │   - Photo unblur + rise (1.3s)│
│    ├─ Center Hero Photo (338, -86)        │  │   - Staggered UI fade (55ms)  │
│    │   ├─ 6% L/R edge alpha mask          │  │   - 400+ & 230+ count-up      │
│    │   ├─ ORVANTE Glass Plate (532, 444)  │  │                               │
│    │   └─ Wordmarks Row (y: 864)          │  │ • Scroll & Parallax Loop      │
│    ├─ PURE / DESIGN ('25) (57, 246)       │◄─┤   - Hero photo 0.12× drift    │
│    ├─ (ABOUT) + Book A Call ↗ (y: 458)    │  │   - Statement 3-word soft     │
│    ├─ Stats Frame (57, 693 | 341 × 208u)  │  │     grey → white interpolation│
│    │   ├─ 400+ Dark Card + 6 Glyphs       │  │   - IntersectionObserver for  │
│    │   └─ 230+ Cap Photo Card             │  │     56M+, 10+ & 8 avatars     │
│    └─ Right Column                        │  │                               │
│        ├─ True Growth Pill (1216, 258)    │  │ • Recorder Mode (?rec=1)      │
│        ├─ Available Copy (y: 442)         │◄─┤   - 1.3–4.2s Statement fill   │
│        └─ Q Industrial Card [2025]        │  │   - 3.5–5.2s Trust & Avatars  │
│                                           │  │   - 5.3s Awards Card 6u lift  │
│ 2. BAR & STATEMENT (#000000)              │  │                               │
│    ├─ 111u Bar (EST 2019 / SCROLL / LIVE) │  │ • Interactive Controllers     │
│    ├─ 830u Word-Span Statement (52u)      │◄─┤   - Sliding Nav Pill + Scroll │
│    └─ 23u Performance Sub-line            │  │   - Inquiry & Booking Modal   │
│                                           │  │     (Form + Validation)       │
│ 3. TRUST PANEL (1302 × 429u, #000000)     │  └───────────────────────────────┘
│    ├─ Heading + 2 Frosted Glass Tiles     │
│    ├─ 56M+ Avatar Grid Card (#d6d6d6)     │
│    ├─ 10+ Awards Laurel Card (#262626)    │
│    └─ Cropped Portrait Card (200u)        │
└───────────────────────────────────────────┘
```

### Interactive Component & State Mapping
- **Segmented Navigation Controller**:
  - Tracks `activeNavIndex` (default `0` for `Home`) and `hoverNavIndex`.
  - Positions the black background pill (`.nav-indicator`) using `transform: translateX(...)` and `width` matching the target link button.
  - Clicking a nav item updates `activeNavIndex`, smoothly scrolls to the target section anchor (`#hero`, `#manifesto`, `#works-showcase`, `#trust-panel`), and keeps focus accessible.
- **Word-by-Word Statement Illumination**:
  - Splits the 5 manifesto lines into individual `<span class="word">` elements while preserving exact line breaks.
  - Computes scroll progress $p \in [0, 1]$ across the statement viewport window (or elapsed time $t \in [1.3\text{s}, 4.2\text{s}]$ in `?rec=1` mode).
  - Maps each word index $i \in [0, N-1]$ through a 3-word soft ramp: $\alpha_i = \text{clamp}\left(\frac{p \cdot (N + 3) - i}{3}, 0, 1\right)$, interpolating RGB channels between `#6f6f6f` `(111, 111, 111)` and `#f4f4f4` `(244, 244, 244)`.
- **Counter & Avatar Trigger System**:
  - Uses `requestAnimationFrame` with cubic-out easing (`1 - Math.pow(1 - t, 3)`) to animate numeric counters (`400+`, `230+` on load; `56M+`, `10+` on Trust Panel entry).
  - Triggers staggered Web Animations on the 8 CloudFront avatar images (`scale(0.4)` to `scale(1)`, `opacity: 0` to `1`, `60ms` stagger).
- **Monochrome Inquiry & Call-Booking Modal**:
  - Triggered by **Contact Us ↗**, **Book A Call ↗**, the dark card's **Book a call ↗** bar, or the brand plate menu icon.
  - Supports keyboard `Escape` dismissal, backdrop click close, interactive service pill selection, email/name validation, and an immediate confirmation state displaying the scheduled discovery details.
