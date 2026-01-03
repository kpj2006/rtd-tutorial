# How to Use Your Own Markdown Files

This guide explains how to integrate your existing repository markdown files into this Sphinx documentation.

## Overview

Instead of maintaining separate documentation, you can use your existing README and markdown files directly! This approach:

✅ Reduces duplication  
✅ Keeps documentation close to code  
✅ Makes updates easier  
✅ Maintains single source of truth  

## Step-by-Step Guide

### 1. Copy Your Markdown Files

Copy your existing `.md` files to the `docs/source/` directory:

```bash
# Example: Copy your README
cp README.md docs/source/readme.md

# Copy other markdown files
cp CONTRIBUTING.md docs/source/contributing.md
cp CHANGELOG.md docs/source/changelog.md
```

### 2. Add Files to Toctree

Edit `docs/source/index.md` and add your files to the toctree:

````markdown
```{toctree}
:maxdepth: 2
:caption: 📚 Documentation

readme
getting-started
usage
contributing
changelog
api
```
````

### 3. Clean Up Markdown (Optional)

You may need to adjust some markdown syntax for better Sphinx compatibility:

#### Image Paths

```markdown
<!-- Before (GitHub style) -->
![Logo](../public/logo.svg)

<!-- After (Sphinx friendly) -->
![Logo](/_static/logo.svg)
```

#### HTML in Markdown

MyST Parser supports HTML, but some elements work better as directives:

````markdown
<!-- Instead of HTML divs -->
<div align="center">Content</div>

<!-- Use MyST directives -->
```{div} class="center"
Content
```
````

### 4. Organize with Subdirectories

You can organize docs in subdirectories:

```
docs/source/
├── index.md
├── getting-started/
│   ├── installation.md
│   └── quickstart.md
├── guides/
│   ├── beginner.md
│   └── advanced.md
└── api/
    └── reference.md
```

Reference subdirectory files in toctree:

````markdown
```{toctree}
getting-started/installation
getting-started/quickstart
guides/beginner
guides/advanced
```
````

## Advanced Toctree Options

### Multiple Captions

Organize docs into sections with different captions:

````markdown
```{toctree}
:maxdepth: 2
:caption: 🚀 Getting Started

getting-started
installation
quickstart
```

```{toctree}
:maxdepth: 2
:caption: 📖 Guides

guides/beginner
guides/advanced
tutorials
```

```{toctree}
:maxdepth: 2
:caption: 📚 Reference

api
contributing
changelog
```
````

### Toctree Options Explained

```{list-table}
:header-rows: 1

* - Option
  - Description
  - Example
* - `:maxdepth:`
  - How many levels deep to show
  - `:maxdepth: 2`
* - `:caption:`
  - Section title in sidebar
  - `:caption: Getting Started`
* - `:hidden:`
  - Hide from page, show in sidebar only
  - `:hidden:`
* - `:numbered:`
  - Auto-number sections
  - `:numbered:`
* - `:titlesonly:`
  - Show only page titles
  - `:titlesonly:`
```

## File Naming Best Practices

### Good Names ✅

```
getting-started.md
api-reference.md
user-guide.md
contributing.md
```

### Avoid ❌

```
page 1.md          # Spaces
Getting_Started.md # Mixed case (use lowercase)
123-guide.md       # Starting with numbers
```

## Linking Between Pages

### Using MyST Syntax

```markdown
# Cross-reference a document
See the {doc}`getting-started` guide.

# With custom text
Check out {doc}`the API docs <api>`.

# Reference a section
See {ref}`installation-section`.

# External links
[MyST Documentation](https://myst-parser.readthedocs.io/)
```

### Traditional Markdown Links

```markdown
[Getting Started](getting-started.md)
[API Reference](api.rst)
```

## Including Images

### Static Files

Place images in `docs/source/_static/`:

```markdown
![Logo](_static/logo.png)

# Or with MyST
:::{image} _static/logo.png
:alt: Logo
:width: 200px
:::
```

### From URLs

```markdown
![External Image](https://example.com/image.png)
```

## Special MyST Features

### Admonitions

````markdown
```{note}
This is a note box
```

```{tip}
Pro tip for users!
```

```{warning}
Important warning message
```

```{important}
Critical information
```

```{seealso}
Related resources
```
````

### Code Blocks with Options

````markdown
```{code-block} python
:linenos:
:emphasize-lines: 2,3

def example():
    # This line is highlighted
    # This too
    return True
```
````

### Tabs

````markdown
```{tabs}
:::tab{label=Python}
Python code here
:::

:::tab{label=JavaScript}
JavaScript code here
:::
```
````

## Building Your Documentation

### Command Line

```bash
# From docs/ directory
sphinx-build -b html source _build/html

# Or use make
cd docs
make html

# On Windows
.\make.bat html
```

### Live Preview

Install and use sphinx-autobuild:

```bash
pip install sphinx-autobuild

# Auto-rebuild on changes
sphinx-autobuild source _build/html
```

Then open http://localhost:8000

## Example Workflow

Here's a complete workflow for adding your repo docs:

```bash
# 1. Navigate to docs/source
cd docs/source

# 2. Copy your markdown files
cp ../../README.md ./readme.md
cp ../../CONTRIBUTING.md ./contributing.md

# 3. Edit index.md to add them to toctree
# (Use your editor)

# 4. Build the documentation
cd ..
sphinx-build -b html source _build/html

# 5. View in browser
# Open _build/html/index.html
```

## Troubleshooting

### Images Not Showing

- Ensure images are in `_static/` or use absolute paths
- Check file permissions
- Verify image paths don't have spaces

### Links Broken

- Use relative paths from the source directory
- Check file extensions (.md vs .rst)
- Ensure files are listed in toctree

### Markdown Not Rendering

- Verify MyST parser is installed: `pip install myst-parser`
- Check `conf.py` has `"myst_parser"` in extensions
- Ensure file has `.md` extension

### Sidebar Not Updating

- Make sure files are in the toctree
- Try cleaning build: `make clean` then `make html`
- Check indentation in toctree directive

## Tips for Professional Documentation

1. **Consistent Structure**: Use similar formatting across all files
2. **Clear Navigation**: Group related pages together
3. **Good Names**: Use descriptive, URL-friendly filenames
4. **Cross-Reference**: Link between related pages
5. **Update Regularly**: Keep docs in sync with code

## Next Steps

- Paste your markdown content into new files
- Update the toctree in {doc}`index`
- Rebuild and view your documentation
- Customize the theme and styling in `conf.py`

---

Now you're ready to integrate your existing markdown files! 🚀
