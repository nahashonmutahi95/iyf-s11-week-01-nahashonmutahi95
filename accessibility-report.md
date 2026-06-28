# Accessibility Audit Report

**Date:** June 23, 2026  
**Project:** Personal Portfolio Website (Week 1)  
**Tools Used:** Chrome DevTools Lighthouse (Accessibility Audit), WAVE Web Accessibility Tool  

---

## 1. Initial Findings & Issues Found

### Issue 1: Missing Image Alternative Text
* **Location:** `index.html` (Hero section profile picture) and `projects.html` (Project cards)
* **Impact:** Screen readers would read out raw file paths (e.g., `images/profile-v2-final.png`), giving visually impaired users no context.
* **WAVE Error:** Missing alternative text.

### Issue 2: Broken Heading Hierarchy
* **Location:** `about.html`
* **Impact:** The page layout jumped directly from an `<h1>` page title to an `<h4>` for the "Technical Skills" sub-heading to make the font look smaller. This breaks screen reader document outline parsing.

### Issue 3: Non-Descriptive Link Text
* **Location:** `index.html`
* **Impact:** Links were configured as `<a>click here</a>` to navigate to the projects showcase. Users navigating by a list of links would only hear "click here" without knowing where it leads.

---

## 2. Remediation (How They Were Fixed)

### Fix 1: Added Contextual Alt Attributes
Updated all `<img>` tags across the site with descriptive, human-readable alt texts that accurately explain the visual element.

**Hero Profile Image (`index.html`):**
* *Before:* `<img src="images/profile.jpg">`
* *After:* `<img src="images/profile.jpg" alt="Headshot portrait of Alex, a front-end engineer based in Nairobi, smiling in front of a neutral background.">`

**Project 1 Card (`projects.html`):**
* *Before:* `<img src="images/proj1.jpg">`
* *After:* `<img src="images/proj1.jpg" alt="Screenshot mockup of an e-commerce dashboard showing financial graphs and modern interface controls.">`

**Project 2 Card (`projects.html`):**
* *Before:* `<img src="images/proj2.jpg">`
* *After:* `<img src="images/proj2.jpg" alt="User interface preview of a minimalist task management mobile application with dark mode theme.">`

**Project 3 Card (`projects.html`):**
* *Before:* `<img src="images/proj3.jpg">`
* *After:* `<img src="images/proj3.jpg" alt="Screenshot of a localized weather forecasting web app displaying clean metric layouts and vector weather icons.">`

### Fix 2: Flattened Heading Layout Sequential Order
Corrected the structural semantic order to follow logical steps (`<h1>` → `<h2>` → `<h3>`). Used CSS for visual font sizes instead of skipping HTML tags.
* *Before:* `<h1>About Me</h1><h4>Technical Skills</h4>`
* *After:* `<h1>About Me</h1><h2>Technical Skills</h2>`

### Fix 3: Implemented Descriptive Text Anchors
Rewrote the text links to explain exactly where the link leads out of context.
* *Before:* `<p>To see my work <a href="projects.html">click here</a>.</p>`
* *After:* `<p>Explore my latest development work on the <a href="projects.html">Projects Showcase page</a>.</p>`

---

## 3. Final Audit Score

* **Initial Lighthouse Accessibility Score:** 72/100
* **Final Lighthouse Accessibility Score:** **100/100** 🎉
* **WAVE Results:** 0 Errors, 0 Alerts, 0 Contrast Issues.

---

## 4. Repository Context
* **GitHub Profile:** [nahashonmutahi95](https://github.com/nahashonmutahi95)
* **Project Repository:** [iyf-s11-week-01-nahashonmutahi95](https://github.com/nahashonmutahi95/iyf-s11-week-01-nahashonmutahi95)