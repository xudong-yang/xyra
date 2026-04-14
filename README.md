# Xyra

A minimal Hugo theme with light/dark mode support.

## Requirements

- Hugo 0.146.0+ (standard, not extended)
- Go 1.26.1+

## Installation

### As a Hugo Module

1. Initialize your site as a Hugo module:
   ```bash
   hugo mod init github.com/username/your-site
   ```

2. Add to your site's `hugo.toml`:
   ```toml
   [module]
     [[module.imports]]
       path = "github.com/xudong-yang/xyra"
   ```

3. Get the theme:
   ```bash
   hugo mod get
   ```

### As a Git Submodule

```bash
git submodule add https://github.com/xudong-yang/xyra.git themes/xyra
```

Then add to your `hugo.toml`:
```toml
theme = ['xyra']
```

## Configuration

### Basic `hugo.toml`

```toml
title = 'Your Site'
baseURL = 'https://example.org/'
languageCode = 'en-US'

[params]
  description = "Your site description"

[menu]
  [[menu.main]]
    name = 'posts'
    pageRef = '/posts'
    weight = 20
```

### Code Highlighting

The theme enables line numbers for code blocks by default. This can be configured:

```toml
[markup]
  [markup.highlight]
    lineNos = true
    lineNumbersInTable = true
```

## Shortcodes

### Badge

Display certification or achievement badges:

```
{{< badge image="/images/badge.png" name="Certificate" link="https://example.com" >}}
```

### Badges

Container for multiple badges:

```
{{< badges >}}
{{< badge image="/images/badge1.png" name="Badge 1" >}}
{{< badge image="/images/badge2.png" name="Badge 2" link="https://example.com" >}}
{{< /badges >}}
```

### YouTube

Embed YouTube videos (privacy-enhanced mode):

```
{{< youtube dQw4w9WgXcQ >}}
```

### Carousel

Horizontal scrolling image carousel:

```
{{< carousel >}}
![Image 1](/images/img1.png)
![Image 2](/images/img2.png)
{{< /carousel >}}
```

## Mermaid Diagrams

Create diagrams using fenced code blocks with the `mermaid` language:

````markdown
```mermaid
graph TD
    A[Start] --> B{Decision}
    B -->|Yes| C[Action]
    B -->|No| D[End]
```
````

## Content Structure

### Front Matter

```toml
+++
title = 'Post Title'
date = 2023-01-05T09:00:00-07:00
draft = false
tags = ['tag1', 'tag2']
+++

Your content here.
```

### Relative Links

Use Hugo's `relref` for internal links:

```markdown
[Link to Post]({{% relref path="post-2.md" %}})
```

## Development

Run the development server:

```bash
hugo server
```

Build for production:

```bash
hugo
```

## License

MIT License - see [LICENSE](LICENSE)
