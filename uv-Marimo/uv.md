# ⚡ uv Cheat Sheet

A quick reference for [uv](https://github.com/astral-sh/uv), the extremely fast Python package and project manager.

## 🚀 Getting Started

| Command | Description |
| :--- | :--- |
| `uv init` | Initialize a new Python project (creates `pyproject.toml`) |
| `uv init --python 3.12` | Initialize with a specific Python version |
| `uv sync` | Install all dependencies and sync the virtual environment |
| `uv lock` | Create or update the `uv.lock` file |

## 📦 Dependency Management

| Command | Description |
| :--- | :--- |
| `uv add <pkg>` | Add a package to project dependencies |
| `uv add --dev <pkg>` | Add a package as a development dependency |
| `uv remove <pkg>` | Remove a package from the project |
| `uv add -r requirements.txt` | Import dependencies from a requirements file |
| `uv tree` | View the dependency tree for the current project |

## 🛠️ Running Code & Tools

| Command | Description |
| :--- | :--- |
| `uv run <script.py>` | Run a script in the project's virtual environment |
| `uv run <command>` | Execute a command (e.g., `uv run pytest`) |
| `uvx <tool>` | Run a tool in an ephemeral environment (alias for `uv tool run`) |
| `uv tool install <pkg>` | Install a Python tool globally in an isolated environment |

## 🐍 Python Version Management

| Command | Description |
| :--- | :--- |
| `uv python list` | List available Python versions |
| `uv python install 3.11` | Install a specific Python version |
| `uv python pin 3.10` | Pin the current project to a specific Python version |

## 🔧 Pip-Compatible Interface
*Use these if you need a drop-in replacement for standard `pip` commands.*

| Command | Description |
| :--- | :--- |
| `uv pip install <pkg>` | Install a package into the active environment |
| `uv pip compile reqs.in` | Compile a requirements file (replaces `pip-compile`) |
| `uv pip sync reqs.txt` | Sync environment with a requirements file |
| `uv venv` | Create a new virtual environment |
