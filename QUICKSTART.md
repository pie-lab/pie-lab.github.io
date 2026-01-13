# Quick Start Guide

Get your academic website up and running in 5 minutes!

## 1. Install Hugo

```bash
# macOS
brew install hugo

# Windows (using Chocolatey)
choco install hugo-extended

# Linux
sudo apt-get install hugo
```

## 2. Preview Locally

```bash
hugo server
```

Open http://localhost:1313 in your browser.

## 3. Personalize (Minimum Changes)

Edit these 3 files:

### `config/_default/hugo.yaml`
```yaml
title: Your Name
baseURL: 'https://yourusername.github.io/'
```

### `config/_default/params.yaml`
```yaml
header:
  navbar:
    logo:
      text: "Your Name"
```

### `content/authors/admin/_index.md`
- Change `title`, `first_name`, `last_name`
- Update `role` and `organizations`
- Update social media links (email, GitHub, etc.)
- Update research interests, education, work experience
- Write your bio at the bottom

### Replace your photo
Replace `content/authors/admin/avatar.jpg` with your photo.

## 4. Add Your Content

### Publications
Add to `publications.bib` then run:
```bash
python create_pubs.py
```

### Projects
Create folders in `content/project/` (see examples)

### Blog Posts
Create folders in `content/post/` (see examples)

### Teaching
Create folders in `content/teaching/` (see examples)

## 5. Deploy to GitHub Pages

```bash
# Create a repo named: yourusername.github.io
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/yourusername/yourusername.github.io.git
git push -u origin main
```

Then:
1. Go to repo Settings → Pages
2. Under "Source", select "GitHub Actions"
3. Wait 2-3 minutes for deployment
4. Visit `https://yourusername.github.io`

Done! 🎉

For detailed instructions, see [README.md](README.md).
