# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static, single-page website for Yuverse Technica Private Limited, a software services company. The site is hosted on GitHub Pages with a custom domain (yuversetechnica.com).

**Key characteristics:**
- Pure HTML/CSS/JavaScript (no build system or frameworks)
- Single-file architecture (index.html contains all code)
- GitHub Pages deployment
- Three main sections: Home, About Us, and Contact

## Architecture

**Single-Page Application (Vanilla JS)**
The entire website is contained in `index.html` with all HTML, CSS (embedded in `<style>` tags), and JavaScript (embedded in `<script>` tags) together. Navigation between sections is handled client-side by showing/hiding sections with the `.active` class.

**Section Structure:**
- Each major section (home, about, contact) is a `<section>` element with a unique ID
- Only one section has the `.active` class at a time
- Navigation is controlled by the `showSection()` JavaScript function (index.html:889)

**Styling Approach:**
- CSS custom properties defined in `:root` (index.html:23-33) for colors and design tokens
- Gradient-based color scheme using `--primary-gradient` and `--secondary-gradient`
- Glass-morphism effects with backdrop-filter
- Responsive design with mobile breakpoints at 768px and 480px

## Deployment

**GitHub Pages:**
- Site is deployed via GitHub Pages
- Custom domain configured through CNAME file
- Any push to the `main` branch automatically deploys changes
- No build process required

## Development Workflow

Since this is a static site with no build system:

1. **Making changes:** Edit `index.html` directly
2. **Testing:** Open `index.html` in a browser locally
3. **Deploying:** Commit and push to the `main` branch

**Common editing tasks:**

- **Update contact information:** Edit the contact section around index.html:793-823
- **Modify services:** Edit service cards in the services grid around index.html:700-726
- **Change colors/branding:** Update CSS custom properties in index.html:23-33
- **Add new sections:** Create new `<section>` elements and update navigation in index.html:679-683

## Technical Details

**Dependencies:** None (no package.json, no npm modules)

**Browser Support:** Modern browsers with support for:
- CSS Grid and Flexbox
- CSS Custom Properties
- IntersectionObserver API
- Backdrop-filter

**Key JavaScript Functions:**
- `showSection(sectionName)` (index.html:889) - Controls section visibility and navigation
- `toggleMobileMenu()` (index.html:912) - Mobile navigation toggle
- Form submission handler (index.html:918) - Handles contact form validation (currently simulated)

## Important Notes

- The site uses inline styles and scripts for simplicity - everything is self-contained
- Form submission is currently simulated with an alert (index.html:947) - no backend integration
- Statistics shown in About section (150+ projects, 75+ clients, 6+ years) are hardcoded in index.html:744-755
- Contact details are embedded in the Contact section HTML - update there directly when company info changes
