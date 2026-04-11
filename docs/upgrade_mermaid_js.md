# Upgrading Mermaid

## Steps

1. Check the [Mermaid releases page](https://github.com/mermaid-js/mermaid/releases) for the target version.

2. In `layouts/baseof.html`, update the version number in the import URL:

```javascript
import mermaid from "https://cdn.jsdelivr.net/npm/mermaid@11.4.1/dist/mermaid.esm.min.mjs";
```

3. Verify the site works locally:

```bash
hugo server
```

Check a page with a Mermaid diagram renders correctly.

4. Commit the change:

```bash
git commit -m "chore: upgrade mermaid to v11.x.x"
```

## Notes

- Mermaid is loaded from jsDelivr CDN only on pages that contain a Mermaid diagram. Pages without diagrams are not affected.
- To find the latest stable version, you can also run `npm show mermaid version`.
