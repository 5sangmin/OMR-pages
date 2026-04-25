🌐 Language: [한국어](./README.md) | [English](./README.en.md)

# OMR Answer Sheet

<p align="center">
  <a href="https://5sangmin.github.io/OMR-pages/"><img src="https://img.shields.io/badge/Live%20Demo-GitHub%20Pages-1440A0?style=for-the-badge&logo=githubpages&logoColor=white" alt="Live Demo"></a>
  <img src="https://img.shields.io/badge/PWA-Installable-176CB0?style=for-the-badge" alt="PWA Installable">
  <img src="https://img.shields.io/badge/Vanilla%20JS-Single%20Page-F7DF1E?style=for-the-badge&logo=javascript&logoColor=111" alt="Vanilla JS">
  <img src="https://img.shields.io/badge/Status-Deployed-success?style=for-the-badge" alt="Status">
</p>

<p align="center">
  A single-page OMR answer sheet web app built with HTML, CSS, and vanilla JavaScript.
  It provides timer modes, answer marking, grading, per-question time analysis, and installable PWA support.
</p>

***

## Live Demo

**URL:** https://5sangmin.github.io/OMR-pages/

***

## Overview

OMR Answer Sheet is a lightweight browser-based app for multiple-choice practice and exam simulation. It combines a timer, a visual OMR-style answer grid, grading logic, wrong-answer feedback, and time analysis in one page.

This project is designed to be simple for end users while still being portfolio-friendly from a frontend engineering perspective.

***

## Features

### Core user features

- OMR-style 5-choice answer sheet UI
- Adjustable question count
- Exam mode with countdown timer
- Practice mode with stopwatch
- Manual answer key input
- Instant grading summary
- Wrong / blank answer breakdown
- Weighted scoring rule panel
- Per-question time analysis
- Installable PWA experience

### Time analysis UX

- Average time per answered question
- Total elapsed solving time
- Per-question duration list sorted in descending order
- Fixed summary area with scrollable list area
- Reserved list height even when the list is empty

### PWA-related support

- `manifest.webmanifest`
- `service worker` registration
- app icons for installation
- theme color metadata

***

## Screens and flow

### 1. Timer card

The top card controls the session mode and timer behavior.

- **Exam mode** uses a countdown timer.
- **Practice mode** uses a stopwatch.
- The **Analysis** button opens the time-analysis panel.

### 2. OMR answer sheet

The center card renders the answer grid.

- Users can select answers from 1 to 5.
- The question count can be updated dynamically.
- The marked answer count is shown at the bottom.

### 3. Answer key and grading

The grading card accepts an answer key as numbers separated by spaces or commas.

- `Grade` calculates the result.
- `Clear` resets the answer key input.
- `Scoring` opens a weighted scoring rule panel.

### 4. Result card

After grading, the result panel shows:

- correct answers
- wrong answers
- blank answers
- total graded questions
- weighted score
- detailed wrong / blank list

***

## Tech stack

- **HTML5**
- **CSS3**
- **Vanilla JavaScript**
- **GitHub Pages** for hosting
- **PWA assets** via manifest and service worker

This project intentionally avoids frameworks and build tools, making it easy to inspect, deploy, and extend.

***

## Project structure

```text
.
├── index.html
├── manifest.webmanifest
├── sw.js
└── icons/
    ├── icon-192.png
    └── icon-512.png
```

### What each file does

- `index.html` — main UI and application logic
- `manifest.webmanifest` — install metadata for PWA behavior
- `sw.js` — service worker for cache/PWA support
- `icons/` — application icons used during installation

***

## Run locally

### Minimal usage

If the goal is just to use the core app features, opening `index.html` in a browser is enough.

1. Download or clone the project.
2. Open `index.html` directly in a browser.
3. Use the timer, OMR grid, grading, and analysis features.

### Recommended local setup

If the goal is to test PWA behavior, use a local static server.

Examples:

```bash
python -m http.server
```

or

```bash
npx serve
```

Then open the local server URL in the browser.

***

## Deployment

This project is already deployed on GitHub Pages.

**Production URL:** https://5sangmin.github.io/OMR-pages/

Because the app is fully static, GitHub Pages is sufficient for hosting and distribution.

***

## PWA support

This project includes installable PWA support so the web app can behave more like a native application on supported browsers.

Included PWA-related parts:

- `manifest.webmanifest`
- install icons (`192x192`, `512x512`)
- `theme-color` metadata
- `serviceWorker.register("./sw.js")`

### Installation guide

#### Desktop (Chrome / Edge)

1. Open https://5sangmin.github.io/OMR-pages/
2. Click the install icon in the address bar, or open the browser menu and choose the install option.
3. Run it as a standalone installed app.

#### Android (Chrome)

1. Open https://5sangmin.github.io/OMR-pages/
2. Open the browser menu.
3. Tap **Add to Home screen** or **Install app**.
4. Launch it from the home screen after installation.

#### iPhone / iPad (Safari)

1. Open https://5sangmin.github.io/OMR-pages/ in Safari.
2. Tap the **Share** button.
3. Choose **Add to Home Screen**.
4. Launch it from the generated home-screen icon.

***

## Hard refresh

If a newly deployed version does not appear immediately, the browser may still be using cached files.

Use a hard refresh:

- **Windows / Linux**: `Ctrl + Shift + R`
- **macOS**: `Cmd + Shift + R`

This is especially helpful when checking service worker or cached asset updates.

***

## Example user flow

1. Open the app.
2. Choose exam mode or practice mode.
3. Start the timer.
4. Mark answers on the OMR sheet.
5. Open the analysis panel if needed.
6. Paste the answer key.
7. Grade the result.
8. Review score, wrong answers, blank answers, and timing data.

***

## Developer notes

From a portfolio perspective, this project demonstrates:

- single-page interaction design without a framework
- state handling with vanilla JavaScript
- dynamic DOM rendering for variable question counts
- custom grading logic and weighted scoring
- UI handling for fixed-summary + scrollable-analysis layout
- PWA integration with install support
- static deployment through GitHub Pages

It is a good example of turning a simple educational utility into a more complete frontend product with measurable interaction flows.
