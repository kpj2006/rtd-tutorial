# Welcome to Your Documentation

```{note}
This is a professionally structured documentation site using Sphinx with MyST Markdown parser.
All your markdown files will be automatically linked and displayed in the left sidebar.
```

## Quick Start

This documentation demonstrates how to:
- ✨ Use multiple markdown files seamlessly
- 📁 Organize docs with automatic sidebar generation
- 🔗 Link between pages effortlessly
- 🎨 Create professional documentation from your existing README files

## Documentation Structure

Below are all available documentation sections. Click any link to navigate:

```{toctree}
:maxdepth: 2
:caption: 📚 Contents
:hidden:

getting-started
usage
advanced-features
using-your-files
api
```

## Getting Started

Navigate through the sections using the sidebar on the left. Each markdown file you add to the `source/` directory can be automatically included in the documentation.

### How to Add Your Own Markdown Files

1. **Copy your markdown files** to `docs/source/` directory
2. **Add them to the toctree** in this index.md file (see below)
3. **Rebuild the docs** with `sphinx-build`

### Example Toctree Configuration

To add more pages, update the toctree directive above:

````markdown
```{toctree}
:maxdepth: 2
:caption: 📚 Contents

usage
api
your-new-file
another-file
```
````

## Features

:::{admonition} MyST Markdown Features
:class: tip

This documentation supports:
- Standard Markdown syntax
- Cross-references between pages
- Admonitions and callouts
- Code blocks with syntax highlighting
- Math equations
- Tables and more!
:::

## Project Links

For more information about the project, check out the [Usage Guide](usage.md) and [API Reference](api.rst).

---

*Documentation built with [Sphinx](https://www.sphinx-doc.org/) and [MyST Parser](https://myst-parser.readthedocs.io/)*
