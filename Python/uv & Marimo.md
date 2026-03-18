# Python Environment & Notebooks: uv + marimo

### 1. The `uv` CLI (Fast Package Management)
Replaces `pip`, `venv`, and `conda` with a single, lightning-fast Rust-based tool.

# Install uv
curl -LsSf https://astral.sh | sh

# Create and activate a virtual environment
uv venv
source .venv/bin/activate  # macOS/Linux
.venv\Scripts\activate     # Windows

# Install packages at 10x speed
uv pip install pandas polars marimo

### 2. Modern Notebooks with `marimo`
A reactive Python notebook that stores code as a pure `.py` script, making it version-control friendly.

# Initialize a new notebook
uv run marimo edit analysis.py

# Run a notebook as a read-only interactive web app
uv run marimo run analysis.py

### 3. Reproducible Analysis Workflow
The best practice for 2026: define dependencies directly inside your script for total reproducibility.

# analysis.py
# /// script
# dependencies = ["polars", "marimo", "plotly"]
# ///

import marimo as mo
import polars as pl

# In marimo, when you change a cell, all dependent cells 
# update automatically (Reactive Execution)
df = pl.read_csv("data.csv")
mo.ui.table(df)

### 4. Key Advantages for Analysts
*   No More Out-of-Order Execution: Marimo ensures cell 2 can't run before cell 1.
*   Git Friendly: Marimo files are .py, so you can read "Diffs" in GitHub PRs.
*   Instant Dashboards: Share any notebook as a UI with mo.ui sliders and buttons.
