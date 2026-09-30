# 🌲 Sagada Travel & Itinerary Web App — Design & Architecture Blueprint

## 1. Vision & Executive Summary
This document presents the complete architectural and UI design specification for upgrading the **Sagada Oct 15–18 Trip App**. The upgraded web application preserves the beloved aesthetic identity of the original itinerary—a dark pine forest theme with rich typography (`Fraunces` serif + `Inter` sans-serif), warm gold, terracotta, and soft moss accents—while elevating the user experience into a full-featured, interactive travel portal.

The application features a modern, responsive **Sidebar Navigation** allowing seamless tabbed browsing across **Home & Itinerary**, **Tours & Activities**, **Accommodation**, and **Transportation**, paired with interactive features like dynamic budget estimators, interactive packing checklists, filtering systems, and stunning visual photography of Sagada.

---

## 2. Color System & Typography

### 🎨 Color Palette (Preserving Existing Tokens)
| Token | Hex Value | Visual Concept | Usage |
| :--- | :--- | :--- | :--- |
| `--bg` | `#101c16` | Deep Forest Night | Primary background |
| `--bg-2` | `#16241c` | Dark Alpine Shade | Cards, secondary layers, hover states |
| `--card` | `#1a2a21` | Elevated Pine Surface | Main container cards & modal background |
| `--ink` | `#ece6d6` | Warm Cream | Primary text & headlines |
| `--ink-dim` | `#a9b3a4` | Muted Sage / Fog | Subtitles, metadata, secondary body copy |
| `--rule` | `#2c3d31` | Pine Branch Border | Dividers, borders, subtle outlines |
| `--rust` | `#b5552e` | Terracotta / Sunset | Primary accents, status indicators, badges |
| `--moss` | `#8ba06a` | Fresh Mountain Moss | Secondary accents, success states, route nodes |
| `--mist` | `#8fa6ac` | Cloud Mist Blue | Section labels, tag borders, subtle badges |
| `--gold` | `#d1a95c` | Warm Sunlight Gold | Italic title highlights, prices, featured items |

### ✒️ Typography
- **Headings & Accents**: `Fraunces` (Google Fonts variable serif, opsz 9..144, weights 500/600/700). Used for page titles, section titles, numbers, price tags, and hero text.
- **Body & Controls**: `Inter` (Google Fonts sans-serif, weights 400/500/600/700). Used for metadata, timeline notes, button labels, and body text.

---

## 3. Sidebar & Information Architecture

The app adopts a split-view layout on desktop with a sleek fixed sidebar, and a bottom/drawer navigation bar on mobile viewports (`< 768px`).

```
┌──────────────────────────────┬────────────────────────────────────────────────────────┐
│ 🌲 SAGADA TRIP               │ 🌄 HERO & FEATURE BANNER WITH SAGADA PHOTOGRAPHY       │
│ Oct 15–18 · 5 Travelers      │                                                        │
│                              ├────────────────────────────────────────────────────────┤
│ 📌 MAIN NAVIGATION           │ ⚡ MAIN CONTENT VIEW (SWITCHES DYNAMICALLY)            │
│ ├─ 🏠 Home / Itinerary       │                                                        │
│ ├─ ⛰️ Tours & Activities     │  • Home: Hero stats, 3-Day timeline, budget breakdown  │
│ ├─ 🏡 Accommodation          │  • Tours: Filterable adventure cards + difficulty tags │
│ └─ 🚌 Transportation        │  • Accommodation: Carpenter's Homestay spotlight + map │
│                              │  • Transport: Coda bus route diagram, fare calculator  │
│ 🧮 INTERACTIVE UTILITIES     │                                                        │
│ ├─ 🎒 Packing Checklist      │                                                        │
│ └─ 💰 Group Split Calc       │                                                        │
└──────────────────────────────┴────────────────────────────────────────────────────────┘
```

---

## 4. Page Breakdown & Detailed Feature Specifications

### 🏠 1. Home / Itinerary Page
* **Hero Header**: 
  * Displays existing key facts (`5 travelers`, `3D2N Fri–Sun`, `1,500m elevation`).
  * Features a high-resolution hero photo banner of Sagada’s sea of clouds at sunrise over Kiltepan / Marlboro Hills with gradient overlay.
  * Quick-jump navigation pills for Day 1, Day 2, Day 3, Budget, and Packing list.
* **3-Day Day-by-Day Timeline**:
  * **Day 1 (Fri Oct 16)**: Arrival, St. Mary's, Echo Valley, Hanging Coffins, Ganduyan Museum.
  * **Day 2 (Sat Oct 17)**: Kiltepan Sunrise, Lumiang to Sumaguing Cave Connection, Bomod-ok Falls.
  * **Day 3 (Sun Oct 18)**: Marlboro Hills / Blue Soil sunrise, souvenir shopping, departure.
* **Interactive Timeline**: Click on any stop to view detailed tips, gear requirements, map location notes, and cost badges.

### ⛰️ 2. Tours & Activities Page
* **Interactive Category Filters**: All, Spelunking/Caves, Treks & Waterfalls, Cultural & Heritage, Sunrise Views.
* **Rich Activity Cards**:
  1. **Lumiang to Sumaguing Cave Connection** (Extreme Spelunking · 3.5 hrs · ₱680/pax · 2 Guides for 5 pax).
  2. **Echo Valley & Hanging Coffins Trek** (Cultural Walk · 1.5 hrs · ₱210/pax · Local Kankanaey Guide).
  3. **Bomod-ok (Big) Falls Trek** (Rice Terraces Trek · 3 hrs · ₱230/pax · Swimming allowed).
  4. **Marlboro Country & Blue Soil Hills** (Scenic Sunrise Trek · 4 hrs · ₱290/pax · Unique flora & blue terra).
  5. **Kiltepan Sunrise Viewpoint** (Sea of Clouds · 2 hrs · ₱120/pax · Cold mountain weather).
  6. **Sagada Weaving & Pottery Studio** (Crafting & Souvenirs · 1 hr · Free entry).
* **Card Features**: Difficulty indicators (Easy / Moderate / Challenging), photo previews, mandatory gear checklist, fee breakdown, and tour booking tips.

### 🏡 3. Accommodation Page
* **Featured Spotlight — Carpenter's Homestay**:
  * Tagline: *"Your cozy home in the heart of Sagada"*
  * Location: Datil, Ato, Poblacion, Sagada (Central location near town square & dining).
  * Check-in / Check-out details (Oct 16–18).
  * Direct Contact Hotline: `0948 779 2864` with one-touch tap-to-call action.
* **Amenity Badges**: Full Kitchen, Fireplace & Living Area, Dining Area, Mountain View Balcony, Onsite Parking, Hot Shower, High-speed Wi-Fi.
* **Homestay Photo Gallery**: Multi-image preview of pine interiors, cozy fireplace, kitchen, and mountain vista view.
* **Interactive House Rules & Tips**: Information on water conservation, quiet hours, cooking guidelines, and local store hours.

### 🚌 4. Transportation Page
* **Route 1: Manila/QC (Coda Lines Bus Terminal) ↔ Sagada**:
  * Outbound: Thu Oct 15 (20:00) → Fri Oct 16 (07:00) | 11h Overnight bus.
  * Inbound: Sun Oct 18 (14:00) → Mon Oct 19 (01:00) | 11h Overnight bus.
  * Visual route map node diagram showing stopovers (Banaue / Solano / Baguio options).
* **Local Travel & Internal Transport**:
  * SAGADA SEGA Guide & Transport Association details.
  * Shared tourist vans (Kiltepan, Sumaguing drop-off, Bomod-ok shuttle rates).
* **Interactive Fare & Duration Calculator**: Compute bus + local van costs dynamically based on group size.
* **Traveler Survival Guide**: Bus cold AC tips, motion sickness precautions, stopover schedules, terminal coordinates.

---

## 5. Interactive Features & Functional Enhancements

1. **Dynamic Group Budget Calculator**:
   * Users can adjust the number of travelers (default: 5 pax).
   * Toggle optional add-on activities (e.g., Marlboro Country +₱290, Extra souvenir allowance).
   * Live recalculation of per-person cost vs. group total cost.
2. **Interactive Packing Checklist**:
   * Pre-populated items categorized by Gear, Clothing, Cash/Docs, and Personal Care.
   * Interactive checkboxes with progress indicator bar (e.g., `6/10 items packed`).
   * LocalStorage persistence so packing status stays saved across page refreshes.
3. **Interactive Visual Photo Gallery / Lightbox**:
   * Gallery featuring rich imagery of Sagada's pine ridges, rice terraces, hanging coffins, and cave formations.
4. **Quick Search & Filter**:
   * Global search bar in sidebar/header to quickly locate specific activities, places, or tips.

---

## 6. Implementation Strategy & Next Steps

1. **Design System & Styles**: Build CSS using custom properties matching the color palette, typography (`Fraunces` + `Inter`), and dark pine aesthetic.
2. **Component Architecture**: Single Page Application (SPA) structure using vanilla JS for zero-dependency speed and native DOM smoothness.
3. **Responsive Sidebar Layout**: Collapsible/fixed navigation on desktop with hamburger/drawer menu on mobile screens.
4. **Media & Assets**: Use generated high-resolution Sagada scenery images for the hero background, tour cards, accommodation gallery, and transportation visuals.
