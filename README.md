# YBSP Canada — Production Website Release (v8)

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

### 4. Key Fixes in This Release
- **Event Registration Modal**: Added a functional, interactive modal on `events.html` where attendees can enter their Name, Email, Phone, and Attendance Mode, connected directly to Netlify Forms.
- **Photo Albums Showcase**: Upgraded the photo gallery into a filterable album showcase featuring Sunday Meal & Feed A Child, #SororaIkaye School Kits, #MurabireKazoza Toolkits, Canadian Mentorship, and the Annual Solidarity Gala, based on authentic historical documents.
- **Fixed Logo Size in news.html**: Strictly locked the logo SVG to 44px by 44px with CSS and HTML attributes across all pages.
- **Zero Em-Dashes**: All em-dashes have been replaced across the entire site with natural punctuation (commas, colons, hyphens).
- **CA & BI Badges & Bullet Alignment**: Replaced distorted flag SVGs with crisp CA/BI badges and cleanly aligned bullet items in the International Structure section.
- **Official Documents Library**: Real generated PDFs for the Fact Sheet, Gala Press Release, Burundi Cooperation Communiqué, Financial Statement, and Brand Guidelines & Logo Pack ZIP.
