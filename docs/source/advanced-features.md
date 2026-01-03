# Advanced Features

This page demonstrates advanced MyST Markdown features in Sphinx documentation.

## Code Blocks with Highlighting

Python code with syntax highlighting:

```python
def hello_world():
    """A simple function."""
    print("Hello, World!")
    return True

# Call the function
if __name__ == "__main__":
    hello_world()
```

JavaScript example:

```javascript
function greet(name) {
    console.log(`Hello, ${name}!`);
}

greet("Documentation");
```

## Math Equations

Inline math: $E = mc^2$

Block math:

$$
\int_{0}^{\infty} e^{-x^2} dx = \frac{\sqrt{\pi}}{2}
$$

## Tables

| Feature | Status | Notes |
|---------|--------|-------|
| Markdown Support | ✅ | Full MyST support |
| Code Highlighting | ✅ | Multiple languages |
| Cross-references | ✅ | Auto-linking |
| Math Equations | ✅ | LaTeX syntax |

## Task Lists

- [x] Set up Sphinx with MyST
- [x] Create multiple markdown files
- [x] Configure sidebar navigation
- [ ] Add your custom content
- [ ] Deploy documentation

## Nested Sections

### Level 3 Heading

Content under level 3...

#### Level 4 Heading

Even deeper content with automatic sidebar navigation!

## Definition Lists

Term 1
: Definition of term 1

Term 2
: Definition of term 2 with more details

## Links Between Pages

Navigate to other documentation pages:
- Go back to {doc}`index`
- Read the {doc}`getting-started` guide
- Check {doc}`usage` examples

## Callout Boxes

:::{admonition} Pro Tip
:class: tip
Use the `toctree` directive to control sidebar structure!
:::

:::{admonition} Important Note
:class: important
All markdown files in source/ can be linked automatically.
:::

:::{admonition} See Also
:class: seealso
Check the [MyST Parser documentation](https://myst-parser.readthedocs.io/) for more features.
:::

## Summary

This page shows how Sphinx renders complex markdown content professionally with:
- ✨ Syntax highlighting
- 🔗 Automatic cross-references
- 📊 Tables and lists
- ⚡ Math equations
- 🎨 Beautiful admonitions
