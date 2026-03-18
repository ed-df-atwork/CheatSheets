# 🍃 marimo + uv Cheat Sheet

### 🚀 Getting Started (with uv)

| Task | Command |
| :--- | :--- |
| **Run/Edit a notebook** | `uvx marimo edit` |
| **Create new notebook** | `uvx marimo edit notebook.py` |
| **Run in Sandbox mode** | `uvx marimo edit --sandbox notebook.py` |
| **Convert Jupyter (.ipynb)**| `uvx marimo convert old.ipynb > new.py` |
| **Run as read-only App** | `uvx marimo run notebook.py` |

### 🛠️ Dependency Management (PEP 723)
*Marimo works best when dependencies are stored **inside** the `.py` file.*


| Task | Command |
| :--- | :--- |
| **Add pkg to notebook** | `uv add --script notebook.py <package>` |
| **Remove pkg from nb** | `uv remove --script notebook.py <package>` |
| **Run nb as script** | `uv run notebook.py` |

### 🎹 Common UI & Shortcuts

| Action | Shortcut |
| :--- | :--- |
| **Run Cell** | `Cmd/Ctrl + Enter` |
| **Create Cell Above** | `A` (in command mode) |
| **Create Cell Below** | `B` (in command mode) |
| **Delete Cell** | `D, D` (double tap D) |
| **Toggle Code/UI** | `Cmd/Ctrl + .` |
| **Search/Command Pal.** | `Cmd/Ctrl + Shift + P` |

### 📦 Essential marimo Code Snippets
```python
import marimo as mo

# Layout & Containers
mo.vstack([item1, item2]) # Vertical stack
mo.hstack([item1, item2]) # Horizontal stack
mo.accordion({"Title": content}) # Collapsible section

# Interactive Inputs (state is reactive!)
slider = mo.ui.slider(1, 10, label="Value")
text = mo.ui.text(label="Name")
dropdown = mo.ui.dropdown(["A", "B"], value="A")

# Outputting Values
mo.md(f"The value is {slider.value}")
