# ⚡ uv Cheat Sheet

### 🚀 Project Setup

| Task | Command |
| :--- | :--- |
| **Initialize new project** | `uv init` |
| **Create a virtual env** | `uv venv` |
| **Activate (macOS/Linux)** | `source .venv/bin/activate` |
| **Activate (Windows)** | `.venv\Scripts\activate` |
| **Sync dependencies** | `uv sync` |

### 📦 Managing Packages

| Task | Command |
| :--- | :--- |
| **Add a package** | `uv add <package>` |
| **Add dev-only package** | `uv add --dev <package>` |
| **Remove a package** | `uv remove <package>` |
| **Install from file** | `uv pip install -r requirements.txt` |
| **Export to requirements**| `uv export --format requirements-txt > requirements.txt` |

### 🏃 Running Code

| Task | Command |
| :--- | :--- |
| **Run a script** | `uv run <file.py>` |
| **Run a CLI tool** | `uvx <tool_name>` (e.g., `uvx ruff`) |
| **Open Python REPL** | `uv run python` |

### 🐍 Python Management

| Task | Command |
| :--- | :--- |
| **Install Python version**| `uv python install 3.12` |
| **List installed versions**| `uv python list` |
| **Pin version for project**| `uv python pin 3.11` |

### 🧹 Maintenance

| Task | Command |
| :--- | :--- |
| **Clear global cache** | `uv cache clean` |
| **Update uv** | `uv self update` |
