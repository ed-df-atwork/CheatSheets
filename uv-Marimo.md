# UV & MARIMO CHEAT SHEET

## SECTION 1: UV PACKAGE MANAGER
The modern, high-performance Python package and project manager.

---

### Project & Environment Setup

| Action | Command |
| :--- | :--- |
| **New Project** | `uv init` |
| **Create Environment** | `uv venv` |
| **Sync/Install All** | `uv sync` |
| **Activate (Linux/macOS)** | `source .venv/bin/activate` |
| **Activate (Windows)** | `.venv\Scripts\activate` |

### Dependency Management

| Action | Command |
| :--- | :--- |
| **Add Package** | `uv add <package>` |
| **Add Dev-Only** | `uv add --dev <package>` |
| **Remove Package** | `uv remove <package>` |
| **Import requirements** | `uv pip install -r requirements.txt` |
| **Export requirements** | `uv export --format requirements-txt > requirements.txt` |

### Running & Tools

| Action | Command |
| :--- | :--- |
| **Run Script** | `uv run <file.py>` |
| **Run CLI Tool** | `uvx <tool_name>` (e.g., `uvx ruff`) |
| **Python REPL** | `uv run python` |

---

## SECTION 2: MARIMO NOTEBOOKS
The reactive, reproducible Python notebook that doubles as a script.

---

### Execution & Integration

| Action | Command |
| :--- | :--- |
| **Edit/Create** | `uvx marimo edit <file.py>` |
| **Sandbox Mode** | `uvx marimo edit --sandbox <file.py>` |
| **Run as App** | `uvx marimo run <file.py>` |
| **Convert Jupyter** | `uvx marimo convert <file.ipynb> > <file.py>` |

### Inline Dependencies (PEP 723)
*Manage dependencies directly inside your .py notebook file.*


| Action | Command |
| :--- | :--- |
| **Add to Notebook** | `uv add --script <file.py> <package>` |
| **Remove from Notebook** | `uv remove --script <file.py> <package>` |
| **Execute Notebook** | `uv run <file.py>` |

### Essential Keyboard Shortcuts

| Action | Shortcut |
| :--- | :--- |
| **Run Cell** | `Ctrl + Enter` |
| **Toggle Code/UI** | `Ctrl + .` |
| **New Cell (Above)** | `A` (Command Mode) |
| **New Cell (Below)** | `B` (Command Mode) |
| **Delete Cell** | `D, D` (Double Tap) |

---

## SECTION 3: CODE SNIPPETS
Common layout and UI patterns for your notebooks.

```python
import marimo as mo

# Layout Elements
mo.vstack([item1, item2])  # Vertical
mo.hstack([item1, item2])  # Horizontal

# Interactive UI
slider = mo.ui.slider(1, 10, label="Input")
text_box = mo.ui.text(label="Enter Name")

# Reactive Display
mo.md(f"Current Value: {slider.value}")
