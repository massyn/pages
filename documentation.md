---
layout: default
title: Documentation
nav_order: 3
---

# Documentation

## Setting Up GitHub Pages

To use this demo in your own repository:

1. **Enable GitHub Pages**:
   - Go to your repository settings
   - Scroll to "Pages" section
   - Select "Deploy from a branch"
   - Choose "main" branch and "/ (root)" folder

2. **Customize the Site**:
   - Edit `_config.yml` to update site title and description
   - Modify the CSS in `_layouts/default.html` for custom styling
   - Add your own pages with proper front matter

## Adding New Pages

To add a new page that appears in navigation:

```yaml
---
layout: default
title: Your Page Title
nav_order: 4
---

# Your Content Here
```

## Navigation Features

- **Automatic Generation**: Navigation is built from all pages with titles
- **Ordering**: Use `nav_order` to control menu position
- **Exclusion**: Set `nav: false` in front matter to exclude from navigation
- **Active State**: Current page is highlighted in navigation

## Customization Options

### Styling
- Colors and gradients in the CSS section of `_layouts/default.html`
- Responsive breakpoints for mobile/tablet
- Typography and spacing

### Configuration
- Site metadata in `_config.yml`
- Jekyll plugins and settings
- Theme customization options