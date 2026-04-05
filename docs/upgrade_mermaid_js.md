# Upgrade Mermaid

## Steps

1. Check the [Mermaid releases page](https://github.com/mermaid-js/mermaid/releases) for the latest version.

2. In the project root, run:

```bash
NEW_VERSION=11.5.0  # replace with target version

npm pack mermaid@$NEW_VERSION
tar -xf mermaid-$NEW_VERSION.tgz
rm -rf static/js/mermaid
cp -r package/dist static/js/mermaid
rm -rf package mermaid-$NEW_VERSION.tgz
```

3. Verify the site works locally:

```bash
hugo server
```

Check a page with a Mermaid diagram renders correctly.

4. Commit the updated files:

```bash
git add static/js/mermaid
git commit -m "chore: upgrade mermaid to v$NEW_VERSION"
```

