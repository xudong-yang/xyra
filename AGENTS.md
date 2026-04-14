# Xyra Theme Development Guide

## Overview
Xyra is a minimal Hugo theme with light/dark mode support, Mermaid diagram rendering, and custom shortcodes.

## Requirements
- Hugo **0.146.0+** (standard, not extended)
- Go 1.26.1+

## Build Commands
```bash
hugo server    # Development server with live reload
hugo           # Production build
```

## Project Structure
```
xyra/
├── layouts/           # HTML templates
│   ├── _default/      # Base templates (list, single, markup renderers)
│   ├── _partials/     # Reusable components (header, footer, head)
│   ├── shortcodes/    # Custom shortcodes (badge, badges, youtube, carousel)
│   ├── baseof.html    # Root template
│   └── home.html      # Homepage template
├── assets/            # Build assets (CSS, JS)
│   ├── css/           # CSS files (main, header, home, posts, post, badge, carousel)
│   └── js/            # JavaScript files
├── content/           # Sample content
├── static/            # Static files (favicon.ico)
├── archetypes/         # Content scaffolds
├── hugo.toml          # Configuration
└── go.mod             # Hugo module definition
```

## CSS Architecture
- Main variables in `assets/css/main.css` (color-scheme, colors, fonts)
- Component-specific CSS files imported via `layouts/_partials/head/css.html`
- CSS custom properties for theming: `--bg`, `--text`, `--border`, `--accent`
- Light/dark mode via `prefers-color-scheme` media query

## Modifying Styles
1. **Global styles**: Edit `assets/css/main.css`
2. **Component styles**: Edit respective CSS files in `assets/css/`
3. **Templates**: Edit files in `layouts/_partials/`

## Shortcodes
| Shortcode | Usage |
|-----------|-------|
| `{{< badge >}}` | `image`, `name`, `link` attributes |
| `{{< badges >}}` | Container for multiple badges |
| `{{< youtube "VIDEO_ID" >}}` | Embed YouTube (privacy-enhanced) |
| `{{< carousel >}}` | Horizontal scrolling image container |

## Markup Renderers
- **Code blocks**: Syntax highlighting with line numbers
- **Mermaid**: Dynamic CDN loading (jsDelivr) when diagrams present
- **Images**: Lazy loading, captions support
- **Links**: External links auto-open in new tab

## Mermaid.js Upgrade
When upgrading Mermaid.js, update the CDN URL in `layouts/_partials/mermaid.html`.

## Hugo Asset Pipeline
- CSS files are fingerprinted and minified via Hugo pipes
- JS files are fingerprinted and minified via Hugo pipes
- Files should be placed in `assets/` directory

## Content Front Matter
```toml
+++
title = 'Post Title'
date = 2023-01-05T09:00:00-07:00
draft = true
tags = ['tag1', 'tag2']
+++
```
