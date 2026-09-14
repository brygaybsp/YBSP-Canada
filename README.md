# YBSP Canada — Production Website Release (v12)

## Quick Setup & Deployment Guide

### 1. Photo Placement (To make your photo display)
- Copy your photo file into the **`images/`** folder.
- Ensure it is named: **`leis-bruel-haragirimana.jpg`**.
- The website code searches directly in `images/leis-bruel-haragirimana.jpg` (with resilient fallbacks). If placed there, it will render automatically.

### 2. How to Preview Locally (100% Free & Offline)
1. Right-click this ZIP file and select **Extract All...** to extract all files into a regular folder.
   *(Do not open files from inside the temporary Windows ZIP preview).*
2. Open the extracted folder and double-click `index.html` or `about.html`.
3. You can browse all pages, switch languages, test forms, and verify layouts completely offline.

### 3. How to Deploy to GitHub & Netlify (Single Commit)
1. Go to your GitHub repository: `https://github.com/brygaybsp/YBSP-Canada`.
2. Click **Add file** ➔ **Upload files**.
3. Select and drag all files from the extracted folder (`index.html`, `about.html`, `programs.html`, `get-involved.html`, `events.html`, `news.html`, `news-single.html`, `careers.html`, `contact.html`, `donate.html`, `_redirects`, `netlify.toml`, the `docs/` folder with all PDFs, and the `images/` folder with your photo) into GitHub.
4. Click **Commit changes**. Netlify will deploy the update automatically within 30 seconds at zero cost.

### 4. Key Verification Standards in Version 12
- **Mobile Menu Accessibility**: Menu button features dynamic `aria-expanded` ("false" <-> "true") and `aria-controls="main-nav-menu"` matching `<nav id="main-nav-menu">`.
- **Background Scrolling Restoration**: `document.body.style.overflow` is cleanly restored to `''` upon closing via hamburger toggle, leaf link clicks, backdrop clicks, Escape key, or screen resize above 992px.
- **Unified Navigation & Logo**: Identical 9-item single-line navbar and 44px authentic YBSP monogram logo across all 10 pages.
- **Zero Em-Dashes**: Strictly 0 em-dashes across all site text and documents.
