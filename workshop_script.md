# Workshop Script: Build Your Academic Website

**Duration:** 60 minutes | **Format:** Live demo + follow-along | **Prerequisites:** GitHub account, GitHub Desktop installed

---

## Part 1: Introduction & Motivation (5 min)

| **What I Say** | **What I Do** |
|---|---|
| **Why have a personal website?** | Show the live demo site in browser: `sarajweston.com/student_website_template/` |
| - Central hub for your academic identity | Scroll through the demo site slowly |
| - More flexible than a CV | Point out the bio/avatar section at top |
| - Showcases research, teaching, publications in one place | Click through Publications, Projects, Teaching tabs |
| - Employers, collaborators, grad committees Google you | |
| - Free to host on GitHub Pages | |
| | |
| **What we'll do today** | |
| - Fork a ready-made template (no coding from scratch) | |
| - Customize it with your info | |
| - Deploy it live on the internet | |
| - You'll leave with a working website | |
| | |
| **Tech stack — don't panic** | |
| - Hugo = static site generator (turns text files into a website) | |
| - You edit simple text files (YAML + Markdown) | |
| - If you can edit an R script, you can do this | |
| - GitHub Actions builds and deploys automatically | |

---

## Part 2: Fork the Repository (5 min)

| **What I Say** | **What I Do** |
|---|---|
| **Step 1: Go to the template repo** | Navigate to `github.com/sarajweston/student_website_template` (or your repo URL) |
| - This is the template I made for you | Show the repo page — point out the file list, README |
| | |
| **Step 2: Fork it** | Click the **"Fork"** button (top-right of the repo page) |
| - Forking = making your own copy | On the "Create a new fork" page: |
| - Your copy is independent — changes you make won't affect the original | |
| | |
| **Naming your fork** | |
| - **Default (recommended):** name it `yourusername.github.io` | Change **Repository name** to `yourusername.github.io` |
| - This exact naming gives you the cleanest URL: `https://yourusername.github.io` | |
| - e.g., `janedoe.github.io` | |
| | |
| **⚠️ Already have a `username.github.io` repo?** | |
| - That's fine — pick any name, e.g., `my-website` or `academic-site` | |
| - Your site will live at `https://yourusername.github.io/my-website/` instead | |
| - Only difference: you'll need to include the repo name in the `baseURL` later — I'll show you | |
| - **Most of you: use `username.github.io`. Only change if you already have something at that URL.** | |
| | |
| **[LIVE DEMO NOTE]** | Since I already have a `username.github.io` site, change repo name to `demo-website` |
| - I'm going to name mine differently because I already have a personal site | |
| - I'll show you what's different so you'll know both options | |
| | |
| | Uncheck "Copy the `main` branch only" if checked |
| | Click **"Create fork"** |
| | Wait for the fork to complete — show the new repo page |
| | |
| **Pause — make sure everyone has forked** | |
| - Check: you should see the repo under your own username | |
| - URL should say `github.com/YOUR-USERNAME/YOUR-USERNAME.github.io` (or your chosen name) | |

---

## Part 3: Enable GitHub Pages (3 min)

| **What I Say** | **What I Do** |
|---|---|
| **Turn on GitHub Pages** | From your forked repo, click **Settings** (gear icon, top menu bar) |
| - This tells GitHub to actually host your site | In the left sidebar, click **Pages** (under "Code and automation") |
| | Under **"Build and deployment" > Source**, select **"GitHub Actions"** from the dropdown |
| | |
| **That's it — the workflow file is already in the repo** | |
| - The template includes a GitHub Actions file that builds your site automatically | |
| - Every time you push changes, it rebuilds and redeploys | |
| - First build will happen once we push our first change | |
| | |
| **Note: site won't work yet** | |
| - We need to update the base URL first | |
| - Let's do that now | |

---

## Part 4: Clone to Your Computer (5 min)

| **What I Say** | **What I Do** |
|---|---|
| **Get the files on your machine** | Open **GitHub Desktop** |
| - We need local copies to edit | Click **File > Clone Repository** (or the "Clone a repository" button) |
| | Switch to the **GitHub.com** tab |
| | Find and select your `yourusername.github.io` repo from the list |
| | Choose a local path (e.g., Documents/GitHub/) |
| | Click **"Clone"** |
| | |
| **While that downloads...** | |
| - This is just like cloning any repo | |
| - GitHub Desktop will track all your changes | |
| - You edit files locally, then "push" to GitHub | |
| - GitHub Actions then rebuilds the site | |
| | |
| **Open the folder** | Once cloned, click **"Open in Visual Studio Code"** or **"Show in Finder/Explorer"** |
| - Let's look at the file structure | Show the folder structure in the file browser |
| - `config/` = site settings | Point to each folder |
| - `content/` = all your actual content | |
| - `content/authors/admin/` = your profile | |
| - `.github/workflows/` = the auto-deploy recipe (don't touch this) | |

---

## Part 5: Edit the Configuration Files (10 min)

| **What I Say** | **What I Do** |
|---|---|
| **Open files in any text editor** | Open the project folder in VS Code, RStudio, or any text editor |
| - RStudio works great — just open individual files | |
| - Or use VS Code, Sublime, Notepad++, TextEdit — anything | |
| | |
| **--- File 1: `config/_default/hugo.yaml` ---** | Open `config/_default/hugo.yaml` |
| | |
| **Two lines to change:** | |
| - `title:` — change `Your Name` to your actual name | Change `title: Your Name` to `title: Sara Weston` (or your name) |
| | |
| **`baseURL` — this depends on how you named your fork:** | |
| - If you named it `username.github.io`: set `baseURL: https://yourusername.github.io/` | Show the line in the file |
| - If you used a custom name (like `my-website`): set `baseURL: https://yourusername.github.io/my-website/` | |
| - **The baseURL must match your repo name exactly, or CSS/links will break** | |
| - Always include the trailing slash | |
| | |
| **[LIVE DEMO]** | Change `baseURL:` to `https://sarajweston.github.io/demo-website/` |
| - Mine is `demo-website`, so I include that in the path | Point out the `/demo-website/` subpath |
| - If yours is `username.github.io`, you do NOT need a subpath — just `https://yourusername.github.io/` | |
| - Save the file | **Save** (Cmd+S / Ctrl+S) |
| | |
| **--- File 2: `config/_default/params.yaml` ---** | Open `config/_default/params.yaml` |
| | |
| **Things to change:** | |
| - `appearance: color:` — pick a theme color! | Show the line `color: cyan` — change it to another option |
| - Options: ocean, emerald, forest, dark, strawberry, coffee, rose, earth, blue, teal, purple, sky, etc. | e.g., change to `color: emerald` |
| - `org_name:` — change to your name | Find `org_name: 'Your Name'` and update |
| - `logo: text:` — change to your name (this shows in the nav bar) | Find `text: "Your Name"` under `header > navbar > logo` and update |
| - `footer: copyright: notice:` — change `Your Name` | Find `© {year} Your Name` and update |
| - Save | **Save** |
| | |
| **--- File 3: `config/_default/menus.yaml` ---** | Open `config/_default/menus.yaml` |
| | |
| **Navigation bar items** | Show the menu entries |
| - These are the tabs across the top of your site | |
| - Each has a `name` (display text), `url` (page link), `weight` (order) | |
| - Lower weight = further left | |
| - Don't need a section? Comment it out with `#` or delete it | Demo commenting out the Blog entry by adding `#` in front of each line |
| - Want to reorder? Change the weight numbers | |
| - Save | **Save** |

---

## Part 6: Edit Your Profile (10 min)

| **What I Say** | **What I Do** |
|---|---|
| **This is the most important file** | Open `content/authors/admin/_index.md` |
| - This controls your bio, photo, links, education, everything on the main page | |
| | |
| **Top section — basic info** | |
| - `title:` — your display name | Change `title: Your Name` |
| - `first_name:` / `last_name:` — used for SEO | Update both |
| - `role:` — your title/position | e.g., `role: PhD Student in Psychology` |
| - `organizations:` — your university and department URL | Update `name:` and `url:` |
| | |
| **Social links — `profiles:` section** | Scroll to the `profiles:` block |
| - Email, GitHub, LinkedIn, Google Scholar, ORCID | |
| - Update the URLs to point to your actual profiles | Change `your.email@university.edu` to real email |
| - Don't have Google Scholar or ORCID yet? Delete those lines or comment out with `#` | Change GitHub URL, LinkedIn URL |
| - Icon names are preset — don't change the `icon:` values | Demo deleting the ORCID entry if not needed |
| | |
| **Interests** | Scroll to `interests:` |
| - Replace these with your actual research interests | Replace the four example interests |
| - Simple list format — one per line with a dash | |
| | |
| **Education** | Scroll to `education:` |
| - Two entries by default (PhD and BA) | Update institution names, dates, area |
| - Change institution, dates, area, summary | Change the `summary:` text |
| - Add more by copying the pattern | |
| - `date_end: ''` means "ongoing/present" | |
| | |
| **Work experience** | Scroll to `work:` |
| - Same pattern as education | Update or add positions |
| - Position, company, dates, responsibilities | |
| | |
| **Bio text — at the very bottom** | Scroll to the bottom, below the `---` |
| - This is Markdown — write naturally | Replace the three example paragraphs |
| - `## About Me` is the heading | Write 2-3 sentences about yourself for now |
| - Keep it short for now, polish later | |
| - Save | **Save** |
| | |
| **Replace the avatar photo** | Navigate to `content/authors/admin/` in Finder/Explorer |
| - Find `avatar.jpeg` in `content/authors/admin/` | Delete (or rename) the existing `avatar.jpeg` |
| - Replace with your own photo | Copy your photo into this folder |
| - **Must be named `avatar.jpeg` or `avatar.png` or `avatar.jpg`** | Rename it to `avatar.jpg` (or `.jpeg`/`.png`) |
| - Square crop works best | |
| - If you don't have one ready, skip for now | |

---

## Part 7: Edit the Homepage (5 min)

| **What I Say** | **What I Do** |
|---|---|
| **Homepage is block-based** | Open `content/_index.md` |
| - Each `- block:` entry is a section on your homepage | Scroll through the file, pointing out each block |
| - `about.avatar` = your bio + photo | |
| - `markdown` = the "Research Overview" text | |
| - `collection` blocks = Publications, Projects, Blog Posts | |
| | |
| **Customize Research Overview** | Find the `block: markdown` section |
| - This is the paragraph under "Research Overview" | Select the `text:` content |
| - Replace with your own 2-3 sentence research summary | Type a replacement summary |
| | |
| **Hide sections you don't need yet** | |
| - No publications yet? Comment out that block | Demo adding `#` in front of every line of the Recent Publications block |
| - Use `#` at the start of each line in the block | |
| - Same for Projects or Blog if you want | |
| - You can always uncomment later | |
| - Save | **Save** |

---

## Part 8: Push & Deploy (5 min)

| **What I Say** | **What I Do** |
|---|---|
| **Let's get this live!** | Switch to **GitHub Desktop** |
| | |
| **Review your changes** | GitHub Desktop shows all changed files in the left panel |
| - GitHub Desktop shows every file you modified | Click through a few to show the red/green diff |
| - Red = removed, Green = added | |
| | |
| **Commit your changes** | In the bottom-left, type a commit message: `Customize site with my info` |
| - A "commit" = a snapshot of your changes | Click **"Commit to main"** |
| - Write a short description | |
| - Think of it like "Save" but for version control | |
| | |
| **Push to GitHub** | Click **"Push origin"** (top bar) |
| - This uploads your changes to GitHub | |
| - Which triggers the automatic build | |
| | |
| **Watch it build** | Go to `github.com/YOUR-USERNAME/YOUR-USERNAME.github.io` in browser |
| - Go to your repo on GitHub.com | Click the **"Actions"** tab |
| - Click the "Actions" tab | Show the running workflow (orange dot = in progress) |
| - You'll see a workflow running | Click into it to show the build log |
| - Takes about 2-3 minutes | |
| | |
| **Check your site!** | Once the workflow shows a green checkmark: |
| - Once the green checkmark appears, your site is live | |
| - If repo is `username.github.io` → go to `https://yourusername.github.io` | Navigate to your site URL |
| - If repo is a custom name → go to `https://yourusername.github.io/repo-name/` | |
| - Bookmark it! | Show the live site with the customized content, click through pages |
| | |
| **[LIVE DEMO]** | Navigate to `https://sarajweston.github.io/demo-website/` |
| - Mine is at the subpath because I used a custom repo name | |
| | |
| **Troubleshooting** | |
| - **404 error:** check that repo name matches `username.github.io` exactly (or check the subpath URL if using a custom name) | |
| - **Site looks broken (no styling, broken links):** `baseURL` in `hugo.yaml` doesn't match your actual URL — most common mistake! | |
| - For `username.github.io` repos: `baseURL: https://username.github.io/` | |
| - For custom-named repos: `baseURL: https://username.github.io/repo-name/` | |
| - **Build fails:** click the red X in Actions to see the error log | |

---

## Part 9: Content Deep-Dive — Adding Your Own Content (7 min)

| **What I Say** | **What I Do** |
|---|---|
| **All content follows the same pattern** | Open `content/` folder and show subfolders |
| - Each item = a folder with an `index.md` inside | Open `content/publication/` to show the structure |
| - The folder name becomes the URL slug | |
| - e.g., `content/project/my-cool-study/index.md` becomes `/project/my-cool-study/` | |
| | |
| **--- Publications ---** | Open `content/publication/example-paper-2024/index.md` |
| - Each publication gets its own folder | Show the YAML front matter |
| - Key fields: `title`, `authors`, `date`, `publication_types`, `publication` (journal name) | Highlight `publication_types: article-journal` |
| - `publication_types` options: `article-journal`, `paper-conference`, `thesis`, `book` | Show `featured: true` |
| - `featured: true` = appears in Featured Publications block | |
| - Add DOI, abstract, links to PDF/code/data | |
| | |
| **Shortcut: auto-generate from BibTeX** | Open `publications.bib` |
| - Add your citations to `publications.bib` | Show the example entries |
| - Run `python create_pubs.py` in Terminal | (Demo only if students have Python — otherwise just mention it) |
| - It creates the folders and `index.md` files for you | |
| - Great if you already have a `.bib` file from Zotero or similar | |
| | |
| **--- Projects ---** | Open `content/project/data-visualization/index.md` |
| - Same folder structure as publications | Show the YAML front matter |
| - Key fields: `title`, `summary`, `date`, `tags` | |
| - Add `url_code:`, `url_pdf:`, or `external_link:` for links | |
| - To add a new project: copy an existing folder, rename it, edit `index.md` | Demo: duplicate the `data-visualization/` folder, rename to `new-project/` |
| | |
| **--- Teaching ---** | Open `content/teaching/psy-201/index.md` |
| - Same pattern — one folder per course | Show the fields |
| - `summary:` = short description shown on the card | |
| - Body text (below `---`) = full course description | |
| | |
| **--- Blog Posts ---** | Open `content/post/getting-started/index.md` |
| - Great for research updates, conference recaps, tutorials | Show the front matter |
| - `tags:` and `categories:` help organize posts | |
| - Write in Markdown — same as RMarkdown without the R chunks | |
| | |
| **General pattern for adding content:** | |
| 1. Copy an existing folder in the right section | |
| 2. Rename the folder (this becomes the URL) | |
| 3. Edit the `index.md` inside | |
| 4. Commit and push | |

---

## Part 10: Quick Customization Tips (3 min)

| **What I Say** | **What I Do** |
|---|---|
| **Change your color theme anytime** | Open `config/_default/params.yaml` |
| - Edit `appearance: color:` in `params.yaml` | Show the `color:` line |
| - Just one word to change | |
| - No CSS needed | |
| | |
| **Add a CV/resume PDF** | Navigate to `static/uploads/` |
| - Replace `static/uploads/resume.pdf` with your actual CV | Show the existing placeholder file |
| - The "Download CV" button on the homepage links here | |
| | |
| **Remove sections you don't use** | |
| - Comment out blocks in `content/_index.md` (homepage) | |
| - Comment out or delete menu items in `config/_default/menus.yaml` (nav bar) | |
| - Delete content folders you don't need (e.g., `content/teaching/` if not teaching) | |
| | |
| **The workflow for ongoing updates** | |
| 1. Edit files locally | |
| 2. Open GitHub Desktop — review changes | |
| 3. Write a commit message — Commit | |
| 4. Push origin | |
| 5. Wait 2-3 min — check your site | |
| - That's the whole process, every time | |

---

## Part 11: Wrap-Up & Q&A (2 min)

| **What I Say** | **What I Do** |
|---|---|
| **What you've accomplished today** | Show the student's live site one more time |
| - Forked and deployed a professional academic website | |
| - Customized your profile, config, and homepage | |
| - Learned the pattern for adding any content | |
| | |
| **Next steps on your own** | |
| - Add your real publications, projects, teaching | |
| - Write a proper bio | |
| - Upload your actual CV PDF | |
| - Add a professional headshot | |
| - Optional: register a custom domain (e.g., `yourname.com`) | |
| | |
| **Resources** | Display these URLs on screen |
| - Template README: detailed docs in the repo itself | |
| - Hugo Blox docs: `docs.hugoblox.com` | |
| - Markdown cheat sheet: Google "markdown cheat sheet" | |
| - YAML syntax: just be careful with indentation (spaces, not tabs!) | |
| | |
| **Common gotchas** | |
| - YAML is whitespace-sensitive — use spaces, not tabs | |
| - Strings with colons or special chars need quotes | |
| - `baseURL` must match your repo name exactly (including the subpath if you used a custom repo name!) | |
| - File/folder names: use lowercase and hyphens, no spaces | |
| | |
| **Questions?** | |

---

## Timing Summary

| Section | Duration | Cumulative |
|---|---|---|
| 1. Introduction & Motivation | 5 min | 5 min |
| 2. Fork the Repository | 5 min | 10 min |
| 3. Enable GitHub Pages | 3 min | 13 min |
| 4. Clone to Computer | 5 min | 18 min |
| 5. Edit Configuration Files | 10 min | 28 min |
| 6. Edit Your Profile | 10 min | 38 min |
| 7. Edit the Homepage | 5 min | 43 min |
| 8. Push & Deploy | 5 min | 48 min |
| 9. Content Deep-Dive | 7 min | 55 min |
| 10. Quick Customization Tips | 3 min | 58 min |
| 11. Wrap-Up & Q&A | 2 min | 60 min |

---

## Pre-Workshop Checklist

- [ ] Template repo is public and forkable
- [ ] Live demo site is up and working
- [ ] Your demo fork (`demo-website` or similar) is deployed and working at the subpath URL
- [ ] Delete any previous demo fork if re-using the same name
- [ ] Text editor installed on demo machine (VS Code or RStudio)
- [ ] GitHub Desktop installed and logged in
- [ ] Browser tabs pre-loaded: template repo, GitHub Pages docs
- [ ] Slides/projector tested
- [ ] Spare headshot image ready (in case students want to test with a sample photo)
