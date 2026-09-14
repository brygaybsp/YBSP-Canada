# YBSP Canada — Production Website Release (v12)

## Quick Setup & Deployment Guide

### 1. Photo Placement
- Copy your portrait photo into the **`images/`** folder as **`leis-bruel-haragirimana.jpg`**.
- The website code searches directly in `images/leis-bruel-haragirimana.jpg` with multi-path fallbacks.
- If you have an authentic photo of community youth in Burundi, you can place it in `images/` as **`burundi-sisterhood.jpg`**.

### 2. How to Preview Locally (100% Free & Offline)
1. Right-click this ZIP file and select **Extract All...** to extract all files into a regular folder.
   *(Do not open files from inside the temporary Windows ZIP preview).*
2. Open the extracted folder and double-click `index.html` or `about.html`.
3. You can browse all pages, toggle between English and French, test forms, and verify layouts completely offline.

### 3. How to Deploy to GitHub & Netlify (Single Commit)
1. Go to your GitHub repository: `https://github.com/brygaybsp/YBSP-Canada`.
2. Click **Add file** ➔ **Upload files**.
3. Select and drag all files from the extracted folder (`index.html`, `about.html`, `programs.html`, `get-involved.html`, `events.html`, `news.html`, `news-single.html`, `careers.html`, `contact.html`, `donate.html`, `_redirects`, `netlify.toml`, the `docs/` folder, and the `images/` folder with your photo) into GitHub.
4. Click **Commit changes**. Netlify will deploy the update automatically within 30 seconds at zero cost.

### 4. Key Fixes in This Release
- **Language Switcher Active Color Fix**: Fixed the issue where FR did not highlight green when clicked. Both EN and FR now actively toggle the Emerald Green background and white text when selected.
- **Board of Directors Roster Updated**:
  1. **Yves Dushimimana** (Director & Community Liaison)
  2. **Nader Diab** (Director & Strategic Partnerships)
  3. **Leis Bruel Haragirimana** (Founder & Board Director)
- **Zero Em-Dashes**: Strictly 0 em-dashes across all 10 pages and all document files.
- **Single-Line Donate Button**: Fixed to stay on a single horizontal line in both English ("Donate") and French ("Faire un don").
