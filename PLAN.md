# Website Overhaul Plan

## 1. Custom Color Theme + Typography (assets/custom.scss)
Create `assets/custom.scss` with:
- A custom color palette: deep teal primary (#0d6e6e), warm coral accent (#e8734a), dark navy text (#1a2332) — a data-science-meets-personality vibe, distinct from the default cyan
- Import Google Fonts: **Inter** (body) and **DM Sans** (headings) for a modern, clean look
- Subtle card hover animations (lift + shadow on publication/project cards)
- Rounded card corners for a friendlier feel
- Styled navbar with a slight background blur effect
- Custom blockquote and link styling with the coral accent

## 2. Redesigned Homepage (content/_index.md)
Restructure the homepage with:
- **Hero section**: A bold `markdown` block with a tagline like "Understanding people through data" over a geometric background image, with a subtle gradient overlay
- **Research Pillars**: A `features` block with 3 research areas (Personality & Individual Differences, Data Science & Quantitative Methods, Health & Well-being) each with a distinct icon — replaces the plain text "Research Overview"
- **Featured Publications**: Uncomment and enable the featured publications section (article-grid view) — shows 3-5 best papers
- **Recent Publications**: Keep but limit to 5 most recent
- Reorder: Hero → Research Pillars → Featured Pubs → Projects → Recent Pubs → Blog

## 3. Fix Placeholder Content
- **Author profile** (`content/authors/admin/_index.md`): Remove placeholder LinkedIn/Scholar/ORCID URLs (comment them out rather than leave fake links), fix "Prof. Advisor Name" → generic phrasing, fix "Undergraduate University" → generic phrasing, rewrite About Me bio to be polished and personality/data-science focused
- **Blog welcome post** (`content/post/getting-started/index.md`): Replace "University Name" and "Prof. Advisor Name" with generic text
- **Delete 3 template publication stubs**: `conference-paper-2023`, `example-paper-2024`, `workshop-paper-2023`

## 4. Feature Best Publications
Mark these 4 publications as `featured: true`:
- `weston2024person` — JPSP registered report on person-environment fit
- `weston2023selecting` — AMPPS topic modeling tutorial (showcases data science)
- `weston2024role` — Personality traits + health care utilization
- `wood2026effect` — Personality + COVID-19

## 5. Update Skills Section (content/authors/admin/_index.md)
Replace generic percentage bars with two skill groups that reflect data science expertise:
- **Data Science & Analytics**: R, Python, Statistical Modeling, Machine Learning
- **Research Methods**: Experimental Design, Longitudinal Methods, Survey Design, Open Science

## 6. Enable Contact + Reorder Nav (config/_default/menus.yaml)
- Uncomment the Contact menu item
- Reorder nav: Home → Research (new anchor) → Publications → Projects → Teaching → Blog → Contact

## Files Changed
- `assets/custom.scss` (NEW)
- `content/_index.md` (EDIT)
- `content/authors/admin/_index.md` (EDIT)
- `content/post/getting-started/index.md` (EDIT)
- `config/_default/menus.yaml` (EDIT)
- `config/_default/params.yaml` (EDIT — change color to custom)
- `content/publication/weston2024person/index.md` (EDIT — featured: true)
- `content/publication/weston2023selecting/index.md` (EDIT — featured: true)
- `content/publication/weston2024role/index.md` (EDIT — featured: true)
- `content/publication/wood2026effect/index.md` (EDIT — featured: true)
- `content/publication/conference-paper-2023/` (DELETE)
- `content/publication/example-paper-2024/` (DELETE)
- `content/publication/workshop-paper-2023/` (DELETE)
