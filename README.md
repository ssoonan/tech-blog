# Tech Blog

A multilingual technical blog built with Hugo and the hugo-coder theme.

## Features

- **Multilingual Support**: English (default) and Korean
- **4 Main Sections**: Articles, Thoughts, Projects, About
- **Auto-redirect**: Home page automatically redirects to Articles
- **Responsive Design**: Mobile-friendly layout
- **Syntax Highlighting**: Code blocks with syntax highlighting
- **SEO Optimized**: Built-in SEO features

## Prerequisites

- Hugo Extended (v0.152.2 or later)
- Git

## Installation

The blog is already set up! If you need to clone it elsewhere:

```bash
git clone <your-repo-url>
cd tech-blog
git submodule update --init --recursive
```

## Local Development

### Start the development server:

```bash
hugo server -D
```

The site will be available at `http://localhost:1313`

### Start with Korean language:

```bash
hugo server -D --defaultContentLanguage=ko
```

## Creating New Content

### Create a new article:

```bash
# English
hugo new articles/my-new-article.md

# Korean
hugo new articles/my-new-article.ko.md
```

### Create a new thought:

```bash
# English
hugo new thoughts/my-thought.md

# Korean
hugo new thoughts/my-thought.ko.md
```

### Create a new project:

```bash
# English
hugo new projects/my-project.md

# Korean
hugo new projects/my-project.ko.md
```

## Front Matter Template

Use this template at the top of your markdown files:

```markdown
+++
title = "Your Title"
date = "2025-01-25"
author = "Your Name"
description = "Brief description"
tags = ["tag1", "tag2"]
categories = ["Category"]
+++

# Your Content Here
```

## Building for Production

Generate static files for deployment:

```bash
hugo --minify
```

The generated files will be in the `public/` directory.

## Deployment Options

### GitHub Pages

1. Create a new repository on GitHub
2. Add the remote:
   ```bash
   git remote add origin <your-repo-url>
   ```
3. Push your code:
   ```bash
   git add .
   git commit -m "Initial commit"
   git push -u origin main
   ```
4. Configure GitHub Pages to use the `public/` folder or set up GitHub Actions

### Netlify

1. Push your code to GitHub
2. Connect your repository to Netlify
3. Build command: `hugo --minify`
4. Publish directory: `public`

### Vercel

1. Push your code to GitHub
2. Import project in Vercel
3. Framework Preset: Hugo
4. Build command: `hugo --minify`
5. Output directory: `public`

## Configuration

Edit [hugo.toml](hugo.toml) to customize:

- Site title and description
- Author information
- Social media links
- Menu items
- Theme colors
- And more...

## Directory Structure

```
tech-blog/
├── archetypes/          # Content templates
├── content/             # All content files
│   ├── articles/        # Technical articles
│   ├── thoughts/        # Personal thoughts
│   ├── projects/        # Project showcases
│   ├── about.md         # About page (English)
│   └── about.ko.md      # About page (Korean)
├── layouts/             # Custom layouts
│   └── index.html       # Home redirect to Articles
├── static/              # Static assets (images, etc.)
├── themes/              # Hugo themes
│   └── hugo-coder/      # The hugo-coder theme
├── hugo.toml            # Site configuration
└── README.md            # This file
```

## Customization

### Change the redirect target

Edit [layouts/index.html](layouts/index.html) to redirect to a different section:

```html
window.location.replace("{{ .Site.BaseURL }}thoughts/");
```

### Add social media links

Edit [hugo.toml](hugo.toml) and add to the `[params]` section:

```toml
[[params.social]]
  name = "Github"
  icon = "fa-brands fa-github"
  weight = 1
  url = "https://github.com/yourusername/"

[[params.social]]
  name = "Twitter"
  icon = "fa-brands fa-twitter"
  weight = 2
  url = "https://twitter.com/yourusername/"
```

### Change theme colors

Edit [hugo.toml](hugo.toml):

```toml
[params]
  colorScheme = "dark"  # Options: "light", "dark", "auto"
```

## Language Switching

The hugo-coder theme includes a language switcher in the navigation. Users can toggle between English and Korean by clicking the language selector.

## Troubleshooting

### Theme not loading

Make sure the theme submodule is initialized:

```bash
git submodule update --init --recursive
```

### Content not showing

Check that:
1. The content file has proper front matter
2. The `draft` parameter is not set to `true`
3. You're using the `-D` flag with `hugo server` to show drafts

### Build errors

Clear Hugo's cache:

```bash
hugo --gc
rm -rf public/ resources/
```

## Resources

- [Hugo Documentation](https://gohugo.io/documentation/)
- [hugo-coder Theme](https://github.com/luizdepra/hugo-coder)
- [Markdown Guide](https://www.markdownguide.org/)

## License

Your license here (e.g., MIT, Apache 2.0, etc.)
