# 🍃 marimo Cheat Sheet

A quick reference for [marimo](https://marimo.io), the reactive, git-friendly Python notebook.

## 🚀 CLI Commands


| Command | Description |
| :--- | :--- |
| `pip install marimo` | Install marimo via pip |
| `marimo edit` | Create a new notebook or open the editor |
| `marimo edit notebook.py` | Edit an existing notebook file |
| `marimo run notebook.py` | Run a notebook as a read-only web app |
| `marimo tutorial intro` | Launch the interactive introductory tutorial |
| `marimo convert notebook.ipynb -o notebook.py` | Convert a Jupyter notebook to marimo |
| `marimo new "prompt"` | Generate a new notebook using AI (requires API key) |

## 📦 Core Library (`import marimo as mo`)

### 📝 Markdown & Layouts

| Feature | Syntax |
| :--- | :--- |
| **Markdown** | `mo.md("# Hello World")` |
| **Interpolation** | `mo.md(f"The value is {my_var}")` |
| **Latex** | `mo.md(r"$\sigma = \sqrt{\mu}$")` |
| **Columns** | `mo.hstack([item1, item2])` |
| **Rows** | `mo.vstack([item1, item2])` |
| **Tabs** | `mo.tabs({"Tab 1": content1, "Tab 2": content2})` |

### 🎛️ UI Elements (Reactive Inputs)
*Capture values by assigning them: `slider = mo.ui.slider(0, 100)`*


| Element | Syntax |
| :--- | :--- |
| **Slider** | `mo.ui.slider(start, stop, step=1, label="...")` |
| **Button** | `mo.ui.run_button(label="Submit")` |
| **Text Input** | `mo.ui.text(label="Name", placeholder="...")` |
| **Dropdown** | `mo.ui.dropdown(options=["A", "B"], label="...")` |
| **Checkbox** | `mo.ui.checkbox(label="Enable feature")` |
| **Data Table** | `mo.ui.table(data, pagination=True)` |

## ⌨️ Useful Hotkeys (Editor)


| Shortcut | Action |
| :--- | :--- |
| `Ctrl/Cmd + Enter` | Run the current cell |
| `Esc + M` | Convert cell to Markdown |
| `Esc + Y` | Convert cell to Python Code |
| `Ctrl/Cmd + Shift + H` | Open hotkey help menu |
| `Ctrl + Esc` | Enter Vim command mode (if enabled) |

## 💡 Key Concepts
*   **Reactive Execution**: Changing a variable in one cell automatically triggers updates in all cells that reference it.
*   **Pure Python**: Notebooks are saved as standard `.py` files, making them easy to version control with Git.
*   **No Hidden State**: Deleting a cell also deletes its variables from memory, preventing "stale" state bugs.
