# Custom Styling Guide

These are custom CSS extensions for our Jekyll-based GitHub Pages site.

**Base theme:** [jekyll-theme-minimal](https://github.com/pages-themes/minimal)

The styles below extend the base theme with additional components.

## Callouts / Alerts

GitHub-style callout boxes using Kramdown block attributes.

### Syntax

```markdown
> **Title**
> Your content here.
{: .classname}
```

### Available Classes

| Class | Intensity | Use for |
|-------|-----------|---------|
| `.note` | Lightest | General information |
| `.tip` | Light | Helpful suggestions |
| `.warning` | Medium | Things to be aware of |
| `.caution` | Dark | Potentially dangerous |
| `.important` | Darkest | Critical information |

### Example

```markdown
> **Note**
> This is informational content that readers should be aware of.
{: .note}

> **Important**
> This is critical information that must not be missed.
{: .important}
```

---

## Tree Views

Hierarchical folder/file displays.

### Collapsible Tree

```html
<div class="tree-view-collapsible">
  <details open>
    <summary><strong>Folder Name</strong></summary>
    <ul class="tree-content">
      <li>Item 1</li>
      <li>Item 2</li>
    </ul>
  </details>
</div>
```

- Use `open` attribute on `<details>` to expand by default
- Folder icons change when expanded/collapsed

### Static Tree

```html
<ul class="tree-view">
  <li><strong>Folder</strong>
    <ul>
      <li>File 1</li>
      <li>File 2</li>
    </ul>
  </li>
</ul>
```

---

## Stylesheet Location

All custom styles are in: `docs/assets/css/style.scss`
