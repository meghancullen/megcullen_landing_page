# Working Notes — megcullen_landing_page

> **Internal document — not intended for public audiences.**
> This file is for developer and AI assistant reference only. Update it at the end of every working session before closing the repository.

---

## 1. How to Use This File (For AI Assistants)

1. Read this entire file before suggesting any changes or writing any code.
2. Read `README.md` for the public-facing project description and feature list.
3. Do not change the folder structure or file naming conventions without discussing it first.
4. Follow all conventions listed in Section 8 exactly — do not introduce new patterns.
5. Do not suggest any approaches listed in Section 10 (What Was Tried and Rejected).
6. Ask clarifying questions before making large structural changes (e.g., adding a framework, splitting `index.html`, adding JavaScript logic).
7. This project was built with AI assistance (Replit AI Agent). Refactor conservatively — prefer targeted edits over rewrites.

---

## 2. Current State

**Last Updated:** 2026-03-23

This is a complete, functional static landing page. All five required content sections are built and styled. The page is live in the Replit environment and served correctly. No known bugs remain. The page is ready for publishing.

### What Is Working
- [x] Sticky top navigation with anchor links to all sections
- [x] Hero section — name, tagline, circular headshot (220 px)
- [x] About Me section — first-person bio with GPA, Dean's List, MBA aspiration
- [x] Skills section — pill badges for Technical Tools (green) and Analytic Methods (light bg)
- [x] Projects section — three cards in a two-column desktop / single-column mobile grid
- [x] Contact section — LinkedIn, GitHub, UIowa email as labeled icon badges (all open in new tab)
- [x] Bootstrap 5.3 responsive grid and mobile nav toggle
- [x] Inter font loaded from Google Fonts
- [x] All styles externalized to `css/stylesheet.css` — zero inline styles
- [x] WCAG 2.2 AA: descriptive alt text, h1→h2→h3 hierarchy, keyboard nav, contrast ratios
- [x] Fully responsive at 320 px and wider, no horizontal scrolling
- [x] `README.md` — complete with all 16 required sections
- [x] `WORKING_NOTES.md` — this file

### What Is Partially Built
- [ ] `js/scripts.js` — file exists per the STANDARDS.md folder spec but is intentionally empty; no JavaScript has been written yet

### What Is Not Started
- [ ] Analytics / visitor tracking (Plausible or similar)
- [ ] Individual project detail pages or modal expansions
- [ ] Favicon / browser tab icon
- [ ] Dark mode toggle
- [ ] Blog or case study section

---

## 3. Current Task

**What I was working on when I last stopped:**
The initial build of all page sections is complete and merged. The README and WORKING_NOTES files have been generated. The page is live in Replit and has no outstanding bugs. The project is in a clean, publish-ready state.

**The very next step is:**
Add a `LICENSE` file to the GitHub repository (go to the repo on GitHub → Add file → Create new file → name it `LICENSE` → select the MIT license template) to satisfy the README badge and license section.

---

## 4. Architecture and Tech Stack

| Technology | Version | Why It Was Chosen |
|---|---|---|
| HTML5 | — | Required by STANDARDS.md; semantic elements improve accessibility and SEO |
| CSS3 | — | Required by STANDARDS.md; all styles in one external file for maintainability |
| Bootstrap | 5.3 (CDN) | Required by STANDARDS.md; handles responsive grid and mobile nav toggle without custom JS |
| Bootstrap Icons | 1.11.3 (CDN) | Lightweight SVG icon set that pairs with Bootstrap; used for contact badges |
| Google Fonts — Inter | — | Clean, modern sans-serif that reads well at all weights; fits the professional/approachable tone |
| Python 3 http.server | Built-in | Zero-dependency local server; no Node or build tooling required for a static site |

---

## 5. Project Structure Notes

```
megcullen_landing_page/
├── index.html              # Single-page app — all five sections in one file
├── css/
│   └── stylesheet.css      # All custom styles — this is the only place styles are written
├── js/
│   └── scripts.js          # Empty placeholder required by STANDARDS.md; do not delete
├── images/
│   └── headshot_2025.jpeg  # Headshot referenced in hero; must stay at this exact path
├── PRD.md                  # Product requirements — source of truth for content and goals
├── STANDARDS.md            # Technical and design standards — source of truth for code rules
├── README.md               # Public project documentation
├── WORKING_NOTES.md        # This file
└── resume.docx             # Source resume used to populate content; not linked on the page
```

**Non-obvious decisions:**
- `js/scripts.js` is intentionally empty. It exists only because STANDARDS.md specifies the folder structure. Do not add JavaScript here without discussion — the architecture is designed to be static.
- `resume.docx` must remain in the repo root (it was the content source) but must never be linked to or embedded anywhere in `index.html` — this is an explicit STANDARDS.md constraint.
- The `images/` path `images/headshot_2025.jpeg` is hardcoded in `index.html`. If the image is renamed or moved, the `src` attribute must be updated to match.

**Files that must not be changed without discussion:**
- `STANDARDS.md` — defines all technical rules for the project
- `PRD.md` — defines all content requirements
- The folder structure itself

---

## 6. Data / Database

This project has no persistent data, database, or flat data files. It is a fully static site. All content is hardcoded in `index.html`. No backend, no API calls, no form submissions are processed.

---

## 7. Conventions

### Naming Conventions
- HTML file: `index.html` (singular, lowercase, project root)
- Stylesheet: `css/stylesheet.css` (exactly — referenced by this relative path in `index.html`)
- Scripts: `js/scripts.js` (exactly — per STANDARDS.md spec)
- Images: stored in `images/`, referenced by relative path (e.g., `src="images/headshot_2025.jpeg"`)
- CSS custom properties: kebab-case prefixed with `--color-` for colors, `--font-` for fonts (e.g., `--color-accent`, `--font-main`)
- CSS class names: BEM-inspired kebab-case (e.g., `.skill-tag`, `.skill-tag--accent`, `.hero-photo`)

### Code Style Rules
- No inline `style=""` attributes anywhere in HTML — ever
- No `<style>` tags in any HTML file — ever
- All CSS goes in `css/stylesheet.css`
- External links must always include `target="_blank" rel="noopener noreferrer"`
- All `<img>` elements must have a descriptive `alt` attribute
- Heading hierarchy must never skip levels: `<h1>` → `<h2>` → `<h3>`
- Link text must always be descriptive — no "click here" or bare URLs

### Framework-Specific Patterns
- Bootstrap grid via `col-md-6` / `col-md-12` for the project card layout
- Bootstrap `sticky-top` on the `<nav>` for the sticky navigation
- Bootstrap `navbar-expand-md` for the responsive nav collapse
- Bootstrap Icons rendered via `<i class="bi bi-[name]">` with `aria-hidden="true"`

### Git Commit Message Style
- Imperative mood, present tense (e.g., "Add contact section", "Fix skill badge colors")
- No period at end
- Keep the subject line under 72 characters
- For larger changes, use a short subject line followed by a blank line and bullet details

---

## 8. Decisions and Tradeoffs

- **Single `index.html` file, no separate section pages:** Required by STANDARDS.md. Do not suggest splitting into multiple HTML files.
- **Bootstrap 5.3 via CDN, not installed locally:** Keeps the project dependency-free and matches the course tool requirement. The `integrity` attribute was removed from the Bootstrap JS `<script>` tag because the SRI hash caused a mismatch in the Replit proxy environment.
- **No JavaScript logic written:** STANDARDS.md specifies a static site. Bootstrap JS is loaded only for the mobile nav toggle. Do not add custom JS without explicit discussion.
- **Army green (`#2d5a1b`) as accent color:** Chosen from the STANDARDS.md direction of "navy / army green / white." Provides sufficient contrast (>4.5:1) against white backgrounds for WCAG AA compliance.
- **Third project card spans full width (`col-md-12`):** With an odd number of project cards (three), making the third card full-width produces a cleaner layout than leaving a half-width card with blank space beside it.
- **Analytic Methods badges use light background (`#e8edf2`) with dark text:** STANDARDS.md specifies "secondary background with dark text" for this category. An earlier version used dark navy — this was corrected to match the spec.
- **Email `mailto:` link includes `target="_blank"`:** Required by the task spec so all three contact links open in a new tab consistently.

---

## 9. What Was Tried and Rejected

- **Dark navy background for Analytic Methods skill badges:** Used `--color-nav-bg` (dark navy) with white text. Rejected because STANDARDS.md specifies a light/secondary background with dark text for analytic method tags. Replaced with `--color-secondary-bg` (`#e8edf2`) and dark text.
- **`integrity` attribute on Bootstrap JS CDN tag:** Caused an SRI hash mismatch error in the Replit proxied dev environment, blocking the script from loading. Removed the `integrity` attribute; the JS CDN link now loads without it.

---

## 10. Known Issues and Workarounds

- **Bootstrap JS `integrity` attribute removed:** The official shields.io integrity hash for Bootstrap 5.3.3's JS bundle produced an SRI mismatch error in the Replit dev environment. **Workaround in place:** The `integrity` attribute has been removed from the `<script>` tag. The CDN still loads correctly. Do not add the `integrity` attribute back without testing that it resolves cleanly in this environment.

---

## 11. Browser / Environment Compatibility

**Expected to work (per STANDARDS.md):**
- Chrome (latest)
- Safari (latest)
- Edge (latest)
- Firefox (latest)
- Mobile browsers at 375 px viewport width and wider

**Tested during build:**
- Chromium-based browser via Replit preview (screenshot-verified)

**Known incompatibilities:**
- None identified. No CSS features outside broad browser support are used. CSS custom properties (`var()`) have full support in all target browsers.

**Dev environment:**
- Replit (NixOS, stable-25_05 channel)
- Python 3 built-in `http.server` on port 5000
- No Node, npm, or build toolchain

---

## 12. Open Questions

- Should individual project cards link out to GitHub repositories? The PRD mentions "linking existing GitHub repositories for projects" as in-scope, but no repo URLs were provided during the build session.
- Should a favicon be added? No favicon file or brand icon currently exists.
- Is there a preferred analytics tool? The PRD lists unique site visits as a success metric but the choice of tool was not specified.
- Will the page eventually move to a custom domain, or stay on the default `.replit.app` domain?

---

## 13. Session Log

### 2026-03-23
- Read `PRD.md`, `STANDARDS.md`, `resume.docx`, and reviewed the headshot image before writing any code
- Created `css/`, `js/` folders; replaced placeholder `index.html` with complete five-section landing page
- Built `css/stylesheet.css` from scratch — navy/green/white palette, Inter font, 800 px max-width, sticky nav, pill badges, responsive grid
- Fixed two issues flagged in code review: (1) added `target="_blank"` to the email contact link; (2) corrected Analytic Methods badge background from dark navy to light secondary
- Fixed third project card to span full width (`col-md-12`) to avoid an orphaned half-width card
- Generated `README.md` with all 16 required sections including badges, changelog, and Vibe Coded badge
- Generated `WORKING_NOTES.md` (this file)
- Left incomplete: no favicon, no project GitHub links in project cards, `js/scripts.js` is empty
- Next step when resuming: add MIT `LICENSE` file to GitHub repo, then consider adding project repo links to the three project cards

---

## 14. Useful References

- [Bootstrap 5.3 Documentation](https://getbootstrap.com/docs/5.3/)
- [Bootstrap Icons](https://icons.getbootstrap.com/)
- [Google Fonts — Inter](https://fonts.google.com/specimen/Inter)
- [MDN: HTML5 Semantic Elements](https://developer.mozilla.org/en-US/docs/Glossary/Semantics#semantic_elements)
- [WCAG 2.2 Quick Reference](https://www.w3.org/WAI/WCAG22/quickref/)
- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/) — used to verify color contrast ratios
- [shields.io](https://shields.io/) — badge generation for README
- **AI tools used:** Replit AI Agent generated the initial HTML/CSS structure, all page content, README, and WORKING_NOTES based on `PRD.md`, `STANDARDS.md`, and `resume.docx`. All output was reviewed against the source documents before publishing.
