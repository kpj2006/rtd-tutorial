# Getting Started

Welcome to the Getting Started guide! This page demonstrates how multiple markdown files work together in Sphinx.

## Installation

```bash
pip install your-package-name
```

## Quick Example

Here's a simple example to get you started:

```python
# Example code
import your_package

# Use the package
result = your_package.do_something()
print(result)
```

## Next Steps

After installation, check out:
- [Usage Guide](usage.md) - Learn how to use the features
- [API Reference](api.rst) - Detailed API documentation

```{note}
This is an example file showing how markdown files link together automatically!
```

## Cross-References

You can reference other sections easily:
- See the main {doc}`index` page
- Check the {doc}`usage` guide
- View {doc}`api` documentation

## Admonitions

```{tip}
MyST Parser supports beautiful admonitions!
```

```{warning}
Make sure to configure your environment properly.
```

```{important}
All your markdown files will appear in the left sidebar automatically when added to the toctree.
```
