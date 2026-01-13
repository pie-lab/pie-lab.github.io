# Academic Website Template - Information

## What's Included

This template provides a complete, ready-to-deploy academic website with:

### Content Sections
- **Homepage**: Bio, research overview, recent publications, projects, and blog posts
- **Publications**: Automatically generated from BibTeX or manually created
- **Projects**: Showcase your research projects and software
- **Teaching**: Highlight courses you've taught or assisted with
- **Blog**: Share your thoughts, tutorials, and insights
- **Experience/CV**: Display your education, work experience, and skills

### Example Content
The template comes with realistic example content to help you understand the structure:
- 3 example publications (journal article, conference paper, workshop paper)
- 2 example projects (ML framework, data visualization)
- 2 example blog posts (introduction, research tips)
- 2 example teaching entries (machine learning, data structures)
- Complete example CV/bio

### Customization Options
- **Color themes**: Choose from 10+ professional color schemes
- **Flexible layout**: Show/hide sections as needed
- **Responsive design**: Looks great on all devices
- **SEO optimized**: Built-in support for search engines
- **Social media integration**: Connect your GitHub, LinkedIn, Scholar, ORCID, etc.

## File Structure

```
.
├── config/
│   └── _default/
│       ├── hugo.yaml        # Site title, URL, basic settings
│       ├── params.yaml      # Theme, colors, SEO settings
│       ├── menus.yaml       # Navigation menu
│       ├── module.yaml      # Hugo modules (don't edit)
│       └── languages.yaml   # Language settings (don't edit)
├── content/
│   ├── _index.md           # Homepage content
│   ├── experience.md       # CV/Experience page
│   ├── authors/
│   │   └── admin/
│   │       ├── _index.md   # Your profile/bio
│   │       └── avatar.jpg  # Your photo
│   ├── publication/        # Publication folders
│   ├── project/            # Project folders
│   ├── post/              # Blog post folders
│   └── teaching/          # Teaching folders
├── static/
│   └── uploads/           # Put your CV PDF here
├── assets/
│   └── media/            # Background images, icons
├── .github/
│   └── workflows/
│       └── hugo.yaml      # GitHub Pages deployment
├── publications.bib       # BibTeX file for publications
├── create_pubs.py        # Script to generate publication pages
├── README.md             # Full documentation
├── QUICKSTART.md         # Quick start guide
└── LICENSE.md            # MIT License
```

## Minimal vs. Full Customization

### Minimal Customization (5 minutes)
To get a working site quickly, just edit:
1. `config/_default/hugo.yaml` - site title and URL
2. `content/authors/admin/_index.md` - your info
3. Replace `content/authors/admin/avatar.jpg` - your photo

### Full Customization
For a polished, complete site:
1. Update all config files
2. Replace all example content with your own
3. Customize colors, themes, and layout
4. Add your publications, projects, blog posts
5. Upload your CV PDF

## Getting Help

### Documentation
- **Quick Start**: See `QUICKSTART.md`
- **Full Guide**: See `README.md`
- **Hugo Docs**: https://gohugo.io/documentation/
- **Hugo Blox Docs**: https://docs.hugoblox.com/

### Common Questions

**Q: Do I need to know how to code?**
A: No! You just need to edit text files (YAML and Markdown). The README provides clear examples.

**Q: Can I use this for free?**
A: Yes! The template is free to use, and GitHub Pages hosting is free.

**Q: How do I add my publications?**
A: Either use the Python script with BibTeX, or manually create folders. See the README for details.

**Q: Can I customize the colors?**
A: Yes! Edit `config/_default/params.yaml` and change the `color` setting.

**Q: How do I deploy to a custom domain?**
A: The README has detailed instructions for setting up custom domains with GitHub Pages.

## Credits

This template is based on the [Hugo Academic CV theme](https://github.com/HugoBlox/theme-academic-cv) by HugoBlox.

## License

MIT License - Free to use and modify for your own website.

---

**Ready to get started?** See `QUICKSTART.md` for a 5-minute setup guide!
