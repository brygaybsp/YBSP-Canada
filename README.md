# YBSP Canada — Production Website Release (v12)

## Quick Setup & Deployment Guide

### 1. Photo Placement (How to Replace Any Picture)
- Refer to `images/README_PHOTOS.txt` for the full list of picture filenames.
- For your Executive Director portrait: copy your photo to `images/leis-bruel-haragirimana.jpg`.
- For the Burundi Sisterhood photo on About Us: save your favorite photo from your Google Drive folder (0B7fNLEmvk2OvSnFKRFdVMll1UDQ) to `images/burundi-sisterhood.jpg`.
- For the Why YBSP in Canada photo: save your photo to `images/why-ybsp-canada.jpg`.

### 2. How to Preview Locally (100% Free & Offline)
1. Right-click this ZIP file and select **Extract All...** to extract all files into a regular folder.
   *(Do not open files from inside the temporary Windows ZIP preview).*
2. Open the extracted folder and double-click `index.html`.
3. You can browse all pages, toggle between English and French, test forms, and verify layouts completely offline.

### 3. How to Deploy to GitHub & Netlify (Single Commit)
1. Go to your GitHub repository: `https://github.com/brygaybsp/YBSP-Canada`.
2. Click **Add file** ➔ **Upload files**.
3. Select and drag all files from the extracted folder (`index.html`, `about.html`, `programs.html`, `get-involved.html`, `events.html`, `news.html`, `news-single.html`, `careers.html`, `contact.html`, `donate.html`, `_redirects`, `netlify.toml`, `docs/`, and `images/`) into GitHub.
4. Click **Commit changes**. Netlify will deploy the update automatically within 30 seconds at zero cost.

### 4. Key Fixes in This Release
- **Language Switcher (French & English)**: Fully functional, unified bilingual dictionary with automatic language persistence across all 10 pages.
- **Top Utility Bar Removed**: Removed the redundant top bar containing email, national scope, and federal numbers. The language toggle (`EN | FR`) is now cleanly integrated directly into the main navigation bar.
- **Footer Cleaned**: Removed the duplicate secondary footer strip (duplicate logo, redundant follow us, and second donate button).
- **Donate Button Strictly on One Line**: Added strict non-wrapping styling so "Donate" and "Faire un don" never break into multiple lines.
- **Removed Unaffiliated Partners**: Removed Desjardins and Government of Canada from partner listings.
- **Zero Em-Dashes**: Confirmed 0 em-dashes across the entire website codebase.
- **Updated Leadership Roster**: Added Benit Carolis Nikuza (Director of Programs & Youth Mentorship) and Eric Mayer (Independent Director & Audit Chair).
