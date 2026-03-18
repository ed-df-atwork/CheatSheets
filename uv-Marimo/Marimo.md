### marimo Cheat Sheet

#### Getting Started (with uv)

| Task | Command |
| :--- | :--- |
| Run/Edit a notebook | `uvx marimo edit` |
| Create new notebook | `uvx marimo edit notebook.py` |
| Run in Sandbox mode | `uvx marimo edit --sandbox notebook.py` |
| Convert Jupyter (.ipynb) | `uvx marimo convert old.ipynb > new.py` |
| Run as read-only App | `uvx marimo run notebook.py` |

#### Dependency Management (PEP 723)

| Task | Command |
| :--- | :--- |
| Add package to notebook | `uv add --script notebook.py <package>` |
| Remove package from notebook | `uv remove --script notebook.py <package>` |
| Run notebook as script | `uv run notebook.py` |

#### UI Shortcuts

| Action | Shortcut |
| :--- | :--- |
| Run Cell | `Cmd/Ctrl + Enter` |
| Create Cell Above | `A` (in command mode) |
| Create Cell Below | `B` (in command mode) |
| Delete Cell | `D, D` |
| Toggle Code/UI | `Cmd/Ctrl + .` |
| Search/Command Palette | `Cmd/Ctrl + Shift + P` |

#### Basic Code Snippets
```python
import marimo as mo

# Layout
mo.vstack([item1, item2])
mo.hstack([item1, item2])

# UI Elements
slider = mo.ui.slider(1, 10, label="Value")
text = mo.ui.text(label="Name")

# Output
mo.md(f"The value is {slider.value}")
