# Project Handoff: Prism International Website

This document serves as a comprehensive guide for the transition of the Prism International website project.

## 1. Project Overview
The website is a high-end, professional "statement" site designed for **Prism International Private Limited**. It features a modern "New Age" aesthetic with glassmorphism, bold typography, and a dashboard-style single-page flow.

- **Primary URL:** [https://prism-international.in](https://prism-international.in)
- **Tech Stack:** Standard HTML5, CSS3 (Modern Grid/Flexbox), Vanilla JavaScript (minimal for UI interactions).
- **Design System:** 
  - **Fonts:** Montserrat (Headings, bold/impactful), Inter (Body, clean/professional).
  - **Colors:** Deep Professional Blue (`#005f87`), Accent Blue (`#2596be`), Slate Dark (`#020617`).
  - **Styles:** Glassmorphism headers, interactive accordion sections, and responsive card layouts.

---

## 2. Website Features & Layout

### Homepage (`index.html`)
1.  **Header:** Sticky glassmorphism header with a centered company name and a left-aligned logo. Includes a "Contact Us" anchor link on the right (hidden on mobile).
2.  **Introduction:** Verbatim legal text identifying the company as a registered NBFC-CIC.
3.  **Group Companies:** Two distinct cards for *Perfect Communications Private Limited* (Subsidiary) and *Gateway Distriparks Limited* (Associate).
4.  **Company Information:** Interactive accordion system containing:
    - **Board & Committees:** Detailed lists of directors (Prem, Arun, Ishaan, Samvid) with specific committee compositions.
    - **Policies:** Direct download links to PDF files stored in `files/policies/`.
5.  **Footer:** A dark, contrasted contact section with Registered Office details, CIN, and unified communication lines.

### Disclaimer Page (`disclaimer.html`)
A standalone document page that inherits the design language of the homepage but focuses on formal legal terminology (archaic "old school" style).

---

## 3. File Structure
The project is organized in the `website-data/` directory:
- `index.html`: Main entry point.
- `disclaimer.html`: Legal disclaimer page.
- `CNAME`: GitHub Pages domain configuration file.
- `files/`:
    - `logo.jpg`: The primary brand asset and favicon.
    - `policies/`: Contains the actual policy PDF documents.

---

## 4. Hosting & Infrastructure

### GitHub Pages
- **Repository:** `dutchkimble/prism-website`
- **Branch:** `main`
- **Deployment:** The site deploys automatically from the root of the `main` branch.

### Custom Domain (Cloudflare/DNS)
The site is linked to `prism-international.in`. To maintain this:
1.  **A Records:** Point the apex domain (`@`) to GitHub's IPs:
    - `185.199.108.153`
    - `185.199.109.153`
    - `185.199.110.153`
    - `185.199.111.153`
2.  **CNAME Record:** Point `www` to `dutchkimble.github.io`.
3.  **Cloudflare Nuance:** If using Cloudflare proxy (Orange Cloud), ensure the **SSL/TLS encryption mode** is set to **"Full"** or **"Full (strict)"** to avoid redirect loops, as GitHub Pages enforces its own HTTPS.

---

## 5. Maintenance Workflow
Since you will be using **Claude**, you can simply provide it with the contents of `index.html` or `disclaimer.html` to make edits.

### To push updates to the live site:
1. Open the terminal in the `website-data` folder.
2. Run:
   ```bash
   git add .
   git commit -m "Description of changes"
   git push
   ```
3. GitHub will rebuild the site in ~60 seconds.

## 6. Mobile Responsiveness
The site includes a media query breakpoint at **768px**. 
- On phones: The header "Contact Us" link is hidden, and the font size is reduced for better fit.
- On Desktop/iPad: The full dashboard view is preserved.

---
*Document prepared for project handover - May 2026.*
