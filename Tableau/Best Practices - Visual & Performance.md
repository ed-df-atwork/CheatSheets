# Tableau — Visual & Performance Best Practices

## 1. Dashboard Design & Layout
* **The 5-Second Rule:** A user should understand the main message or most critical KPI within five seconds of looking at the dashboard.
* **Hierarchy (F-Pattern):** Place the most important high-level KPIs in the **top-left** corner, as Western audiences naturally scan in an "F" or "Z" pattern.
* **BANs (Big Angry Numbers):** Use large, bold summary metrics at the top to provide immediate headlines before diving into charts.
* **Limit Views:** Stick to **2–4 worksheets** per dashboard. Overcrowding obscures the "big picture".
* **Fixed Sizing:** Use **fixed-size layouts** instead of "Automatic" to improve performance, as Tableau can reuse a single cached layout.

## 2. Visual Clarity (Data-Ink Ratio)
* **Maximize Data-Ink:** Remove non-essential "chartjunk" like heavy borders, dark grid lines, and unnecessary tick marks.
* **Color with Purpose:**
    * Use a neutral base (gray/white) and save bright colors for highlighting key data or alerts.
    * Limit your palette to **under 5 colors** to avoid "visual noise".
    * Use intuitive associations: Red for "Hot/Negative," Blue/Green for "Cold/Positive".
* **Simplify Tooltips:** Don't just list fields; rewrite them into clear, formatted sentences (e.g., "The total sales for [Region] were [Sales]").

## 3. Performance Optimization
* **Extracts vs. Live:** Prioritize **Extracts (.hyper)** over Live connections for faster local querying and calculation materialization.
* **Filter Efficiency:**
    * Use **Extract Filters** or **Data Source Filters** to limit the data Tableau ever "sees".
    * Use **Context Filters** sparingly to create a temporary results table that other filters run against.
    * Avoid "Exclude" filters; they are slower to process than "Include" filters.
* **Calculations:**
    * Push complex logic to the **database level** (SQL/ETL) whenever possible.
    * Use **Booleans or Integers** in calculations rather than Strings, as they are significantly faster to process.
    * Use `MIN`/`MAX` instead of `ATTR` or `AVG` where possible to reduce computation load.

## 4. Interactivity Best Practices
* **Filter Actions:** Use Dashboard Actions instead of "Quick Filters" (drop-downs) to let users click marks to filter. This is more intuitive and faster to render.
* **Guided Navigation:** Provide subtle instructions (e.g., "Click a region to drill down") to help users explore without getting lost.
* **Parameters:** Use parameters to allow "What-If" scenarios or to let users swap between different measures/dimensions dynamically.

## 5. Quick Development Shortcuts


| Action | Shortcut (Windows) | Shortcut (Mac) |
| :--- | :--- | :--- |
| **New Worksheet** | `Ctrl + M` | `Cmd + T` |
| **Swap Rows/Columns** | `Ctrl + W` | `Ctrl + Cmd + W` |
| **Undo / Redo** | `Ctrl + Z` / `Y` | `Cmd + Z` / `Shift + Z` |
| **Show Me Menu** | `Ctrl + 1` | `Cmd + 1` |
| **Clear Worksheet** | `Alt + Shift + Backspace` | `Opt + Shift + Delete` |
