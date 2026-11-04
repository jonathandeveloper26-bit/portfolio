# Jonathan Vinton — Portfolio

Personal portfolio built for the Epitech Paris **Portfolio** project (brief v1.1).
Live site: **https://jonathandeveloper26-bit.github.io/portfolio/**

Engineer turned developer. The site presents who I am, what I have built, what I am learning at Epitech, and how to contact me, with the goal of securing a six-month internship (January–June 2027).

---

## 1. How the site is published

Publication is automated with **GitHub Pages**, deploying straight from the repository:

| Setting | Value |
|---|---|
| Source | branch `main`, folder `/` (root) |
| Build | none — the files are served as-is |
| URL | `https://jonathandeveloper26-bit.github.io/portfolio/` |

Every push to `main` is live within about a minute, with no manual step. There is no build tool, bundler or pre-processor: what is in the repository is exactly what the browser receives.

To change the deployment settings: repository **Settings → Pages**.

## 2. Repository structure

```
portfolio/
├── index.html              Home: hero, skills, education, experience, selected work
├── about.html              Who I am, quick facts
├── cv.html                 Curriculum vitae (print-to-PDF via the "Download CV" button)
├── projects.html           Project overview cards
├── project_1_VSI.html      Case study: annual turnover process (Village Schools International)
├── project_2_VSI.html      Case study: master information & analytics system (VSI)
├── project_3_PSNS.html     Case study: naval systems maintenance (U.S. Dept. of Defense)
├── learning_journey.html   What each Epitech pool covered and what I took from it
├── contact_form.html       Contact form (Formspree) and direct contact details
│
├── style.css               Site stylesheet: design tokens + all component styles
├── style_cv.css            CV-only rules; imports style.css
│
├── css/materialize(.min).css   Materialize v1.0.0 (UI kit), unmodified
├── js/materialize(.min).js     Materialize v1.0.0 JavaScript, unmodified
│
├── assets/
│   ├── my_profile.jpg      Portrait (own photo)
│   ├── favicon.png
│   ├── github_mark.png     GitHub "Invertocat" mark
│   └── linkedin-svgrepo-com.svg
│
├── presentation/           Slide decks for the project defence (.pptx)
├── portfolio-project.pdf   The Epitech brief this site answers
└── README.md
```

Every HTML page is self-contained and shares the same `<header>` (navigation) and `<footer>`. There is no templating, so a change to the navigation must be made in every page.

## 3. Stack and why

| Choice | Reason |
|---|---|
| **Plain HTML + CSS, no build step** | 40-hour budget, nine pages. Nothing to install, nothing that can break on deploy, and every file is readable by anyone. |
| **Materialize v1.0.0** (UI kit) | Learned during the Epitech Web Pool. Provides the responsive 12-column grid, buttons, chips, form fields and the mobile side-navigation. It is the only JavaScript component on the site. |
| **One hand-written stylesheet** (`style.css`) | A small design system layered on Materialize. All colours, fonts, radii and shadows are CSS custom properties declared once in `:root`, so the whole site can be retuned in one place. |
| **GitHub Pages** | Free, automated, deploys from the branch. Meets the brief's "no manual step" requirement. |
| **Formspree** | Working contact form with no backend, as the brief is front-end only. |

### Design system in brief

- **Colours:** forest green `#1b4332` (identity), warm off-white `#f6f4ef` (page), charcoal `#1f2421` (text), a single gold accent `#b5832b` (dates, rules, active page).
- **Type:** Cormorant Garamond for headings, Inter for body text, loaded from Google Fonts.
- **Layout:** Materialize grid (`s` / `m` / `l` breakpoints at 600 px and 992 px), content measure capped at 1040 px.
- **Patterns:** `.panel` cards, `.timeline` + `.entry` for dated items, `.skill-list` with CSS-drawn dot ratings, `.page-head` band on sub-pages, sticky footer via flexbox.

## 4. Running it locally

No dependencies. Either open any `.html` file in a browser, or serve the folder so paths behave exactly as on GitHub Pages:

```bash
python -m http.server 8080
```

then open <http://localhost:8080/>. (VS Code's **Live Server** extension works too; the workspace is configured for port 5502.)

## 5. Accessibility and SEO

- One `<h1>` per page and a sequential heading order (h1 → h2 → h3).
- Descriptive `alt` text on portraits; empty `alt=""` on decorative icons.
- Colour contrast above WCAG AA for all text on all backgrounds.
- Navigation and side-nav reachable and operable with the keyboard; the mobile menu has a labelled open and close control.
- Each page has a unique `<title>`, `<meta name="description">` and self-referencing `<link rel="canonical">`.
- Responsive from 320 px up, verified at phone, tablet and laptop widths.

## 6. Credits

| Resource | Source | Licence |
|---|---|---|
| Materialize 1.0.0 | https://materializecss.com | MIT |
| Cormorant Garamond, Inter | Google Fonts | SIL Open Font License 1.1 |
| Material Icons | Google | Apache License 2.0 |
| GitHub mark | https://github.com/logos | Used per GitHub's logo usage guidelines |
| LinkedIn icon | SVG Repo, https://www.svgrepo.com | See the icon's page on SVG Repo |
| Portrait, text, case studies | Jonathan Vinton | All rights reserved |

Formspree handles the contact form submissions (https://formspree.io).

## 7. Roadmap

- Move the shared navigation into a template (static-site generator) so it lives in one file.
- Add a committed PDF export of the CV beside the print option.
- Publish Lighthouse accessibility and SEO scores.
- French and Kiswahili versions of the site.
- Keep `learning_journey.html` current after every Epitech pool.
