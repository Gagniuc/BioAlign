# BioAlign


# BioAlign Heatmap

Interactive Sequence Alignment Visualization Tool  

**Platform:** Browser-based (pure HTML/CSS/JavaScript)  
**Algorithm:** Smith–Waterman (local alignment)  
**License:** MIT  

---

## Overview

BioAlign Heatmap is a self-contained, browser-based bioinformatics tool for pairwise sequence alignment and interactive heatmap visualization.

It requires:

- No installation  
- No server  
- No external dependencies  

Simply open the HTML file in any modern browser.

The tool implements the **Smith–Waterman local alignment algorithm** and renders the resulting scoring matrix as a color-coded heatmap on an HTML5 canvas.

Supported sequence types (auto-detected):

- DNA  
- RNA  
- Protein  
- Numeric  
- ASCII  

Alignments and experiments can be saved locally in the browser and exported as PNG images or copied in FASTA or plain-text format.

---

## Features

| Feature | Description |
|----------|-------------|
| Algorithm | Smith–Waterman local pairwise alignment with configurable Match, Mismatch, and Gap scores |
| Sequence Types | Auto-detects DNA, RNA, Protein, numeric sequences, and ASCII text |
| Heatmap Canvas | Real-time color-coded scoring matrix rendered on HTML5 canvas with crosshair navigation |
| Interactive Resize | Drag the canvas edge to resize in real time; sliders stay synchronized |
| Scroll Zoom | Mouse wheel zoom (±30 px per step) while preserving proportions |
| Fullscreen Mode | Expand heatmap to full viewport; Escape exits |
| 3D Perspective | Optional CSS 3D tilt with smooth hover-to-flat animation |
| Themes | Normal, Inferno, Alien, Dark, Dark Chem, Age of Empires, European Union, Gentleman, Military, USA, Red Alert |
| Export PNG | Download current heatmap as high-quality PNG |
| Copy Alignment | Copy alignment as Plain Text or FASTA |
| Local Storage | Save up to 100 experiments in browser localStorage |
| Import / Export | Export saved experiments and re-import them |
| Significance Score | Displays P(s), Sigma(s), and Score% |
| Alignment Text | Formatted alignment output with configurable symbols |
| 5′ / 3′ Caps | Optional nucleic acid end labels |

---

## Getting Started

No installation required. The application is a single HTML file.

### Option 1 — Download

Download the repository from GitHub and extract it.

### Option 2 — Clone

```bash
git clone https://github.com/USERNAME/REPOSITORY.git
cd REPOSITORY
```

### Run

1. Open `index.html` in Chrome, Firefox, Edge, or Safari.
2. Enter two sequences in the Run panel.
3. Click **Run**.

The heatmap and alignment text appear instantly.

---

## Parameters

All scoring parameters are adjustable from the Parameters panel.

| Parameter | Default | Description |
|------------|----------|-------------|
| Match score | +10 | Score for matching characters |
| Mismatch score | −5 | Penalty for mismatches |
| Gap penalty | −7 | Penalty for insertions or deletions |
| HeatMap width | dynamic | Width of each matrix cell (pixels) |
| HeatMap height | dynamic | Height of each matrix cell (pixels) |

---

## Keyboard & Mouse Shortcuts

| Input | Action |
|--------|--------|
| Left click | Force alignment from selected cell |
| Click + drag | Resize heatmap in real time |
| Mouse wheel | Zoom in / out |
| Hover | Show matrix coordinates and score |
| Escape | Exit fullscreen |

---

## Browser Compatibility

Tested in:

- Google Chrome 90+  
- Mozilla Firefox 88+  
- Microsoft Edge 90+  
- Safari 14+  

The Clipboard API requires a secure context (`https://` or `localhost`).  
A legacy fallback is included for older browsers.

---

# Changelog

All modifications and additions made to the original application.

---

## 1. Bug Fixes

### 3D Perspective — Deprecated CSS Repaired

- Removed deprecated transform from `<canvas>`
- Added `id="BioDisplayPanel"` wrapper
- Applied perspective to `.scene`
- Updated `perspectiva3D()` to toggle correct element
- Restored smooth hover-to-flat animation

### Run Button Restored

Navbar Run button restored after accidental `display:none`.

### 3D Toggle Restored

Re-enabled 3D checkbox in navigation bar.

---

## 2. UI & Layout Changes

### Run Button Hidden in Panel

Hidden redundant Run button inside Run panel.

### Run Panel Visible by Default

Changed `runAl` to `display:block`.

### Alignment Text Moved Above Canvas

Relocated `#demo` output above heatmap to improve layout.

---

## 3. New Interactive Features

### Drag-to-Resize

- Added mouse event listeners
- Real-time `OBJ.hx` and `OBJ.hy` updates
- Slider synchronization
- Minimum size constraint: 100px
- Cursor feedback
- Dynamic redraw

### Scroll-to-Zoom

- Wheel listener
- ±30px scaling
- Proportional resizing
- Prevented default scroll

### Fullscreen Mode

- Added Fullscreen button
- `position: fixed` expansion
- Dark background
- Exit button
- Escape key support
- Scroll lock

### Copy Alignment

- Dropdown: Plain Text / FASTA
- Toast confirmation
- `navigator.clipboard`
- Fallback for older browsers

---

## 4. Export Features

### Export PNG

- Uses `canvas.toDataURL('image/png')`
- Downloads `heatmap_alignment.png`
- Works with any theme and size

---

BioAlign Heatmap — README & Changelog
