# Customization Guide

This guide provides tips and tricks for customizing your academic website beyond the basics.

## Changing the Theme/Colors

### Quick Color Change

Edit `config/_default/params.yaml`:
```yaml
appearance:
  mode: system  # Options: system, light, dark
  color: ocean  # Your theme here
```

### Available Themes
- `ocean` - Professional blue (default in this template)
- `emerald` - Fresh green
- `forest` - Deep green
- `dark` - Dark mode friendly
- `minimal` - Clean gray
- `strawberry` - Warm red
- `coffee` - Brown tones
- `rose` - Pink tones
- `earth` - Natural tones
- `mr robot` - Hacker aesthetic

Try different themes to see what works best for your personal brand!

## Customizing the Homepage Layout

### Reordering Sections

In `content/_index.md`, sections appear in the order they're listed. To reorder, just move the blocks around:

```yaml
sections:
  - block: resume-biography-3  # Bio appears first
  - block: markdown            # Research overview second
  - block: collection          # Publications third
  # etc.
```

### Hiding Sections

To hide a section temporarily, comment it out with `#`:

```yaml
# - block: collection
#   id: projects
#   content:
#     title: Projects
```

### Adding a Custom Section

Add a markdown block anywhere:

```yaml
- block: markdown
  content:
    title: 'Custom Section Title'
    text: |
      Your content here in **Markdown**.

      - Bullet points
      - Work too
```

## Customizing the Navigation Menu

Edit `config/_default/menus.yaml`:

```yaml
main:
  - name: Home          # What appears in menu
    url: /              # Where it links to
    weight: 10          # Order (lower = earlier)
  - name: Publications
    url: /publication/
    weight: 20
  # Add more items...
```

### Adding External Links

```yaml
- name: Google Scholar
  url: https://scholar.google.com/citations?user=YOURID
  weight: 100
```

## Advanced Publication Customization

### Featuring Publications

In any publication's `index.md`, set:
```yaml
featured: true
```

Featured publications appear in the "Featured Publications" section on your homepage (if enabled).

### Adding Publication Links

In publication `index.md`:
```yaml
url_pdf: 'https://arxiv.org/pdf/example.pdf'
url_code: 'https://github.com/you/repo'
url_dataset: 'https://data.example.com'
url_poster: '/uploads/poster.pdf'
url_project: '/project/related-project/'
url_slides: '/uploads/slides.pdf'
url_video: 'https://youtube.com/watch?v=...'
```

### Publication Types

Available types for `publication_types`:
- `article-journal` - Journal articles
- `paper-conference` - Conference papers
- `chapter` - Book chapters
- `book` - Books
- `thesis` - PhD/Masters theses
- `report` - Technical reports
- `manuscript` - Preprints/working papers

## Adding Images

### Project Images

Add `featured.jpg` or `featured.png` to any project folder:
```
content/project/my-project/
  ├── index.md
  └── featured.jpg  # Will display as project thumbnail
```

### Blog Post Images

Same for blog posts:
```
content/post/my-post/
  ├── index.md
  └── featured.jpg  # Will display with post
```

### Image in Markdown

```markdown
![Alt text](image.jpg)

Or with a caption:
{{< figure src="image.jpg" caption="My caption" >}}
```

## Custom CSS (Advanced)

To add custom styling:

1. Create `assets/custom.scss`
2. Add your CSS/SCSS:
```scss
// Custom button color
.btn-primary {
  background-color: #ff6b6b;
}

// Custom heading style
h2 {
  color: #2d3748;
  border-bottom: 2px solid #edf2f7;
}
```

## Changing Fonts (Advanced)

Edit `config/_default/params.yaml`:
```yaml
appearance:
  theme_day: custom_theme
  theme_night: custom_theme
  font: custom_font
  font_size: L  # Options: S, M, L, XL
```

Then create custom theme/font definitions in Hugo Blox format (see their docs).

## Adding Google Analytics

Edit `config/_default/params.yaml`:
```yaml
marketing:
  analytics:
    google_analytics: 'G-XXXXXXXXXX'  # Your Google Analytics ID
```

## SEO Optimization

### Update Site Description

Edit `config/_default/params.yaml`:
```yaml
marketing:
  seo:
    description: 'Detailed description of your research and expertise for search engines'
```

### Publication Keywords

In publication `index.md`, add tags:
```yaml
tags:
- Machine Learning
- Natural Language Processing
- Deep Learning
```

These help with discoverability.

## Social Media Cards

When someone shares your site, Hugo automatically generates preview cards. To customize:

Edit `config/_default/params.yaml`:
```yaml
marketing:
  seo:
    twitter: 'yourusername'  # For Twitter cards
```

Add a square image at `assets/media/icon.png` (512x512px) for the site icon.

## Multi-Language Support (Advanced)

Hugo supports multiple languages. See the [Hugo i18n docs](https://gohugo.io/content-management/multilingual/) for details.

Basic setup in `config/_default/languages.yaml`:
```yaml
en:
  languageName: English
  weight: 1
es:
  languageName: Español
  weight: 2
```

## Performance Tips

### Optimize Images

Before adding images:
1. Resize to appropriate dimensions (max 2000px wide)
2. Compress with tools like [TinyPNG](https://tinypng.com/)
3. Use JPG for photos, PNG for graphics with transparency

### Minimize Custom Code

The template is already optimized. Only add custom CSS/JS if absolutely necessary.

## Troubleshooting Customizations

### Changes Not Showing

1. Stop the server (`Ctrl+C`)
2. Delete `/resources/` folder if it exists
3. Restart: `hugo server`

### Broken Layout

1. Check YAML syntax (indentation matters!)
2. Ensure all quotes and brackets are closed
3. Review error messages in terminal

### Need to Reset

Keep the original example files! You can always refer back to:
- Example publications in `content/publication/`
- Example projects in `content/project/`
- Original config files

## Getting More Help

- [Hugo Blox Blocks Reference](https://docs.hugoblox.com/reference/content/blocks/)
- [Hugo Documentation](https://gohugo.io/documentation/)
- [Markdown Cheat Sheet](https://www.markdownguide.org/cheat-sheet/)

## Community Themes

Want a completely different look? Check out:
- [Hugo Blox Templates](https://hugoblox.com/templates/)
- [Hugo Themes](https://themes.gohugo.io/)

Most Hugo themes can work with your content with minimal modifications.
