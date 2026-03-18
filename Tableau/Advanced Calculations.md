# Tableau Cheat Sheet: Advanced Calculations

### 1. Level of Detail (LOD) Expressions
LODs allow you to calculate values independent of the dimensions in your current view.
*   **FIXED:** Ignores view dimensions (except Context Filters).
    ```sql
    { FIXED [Region] : SUM([Sales]) }
    ```
*   **INCLUDE:** Adds a dimension to the calculation even if it isn't in the view.
    ```sql
    { INCLUDE [Customer Name] : AVG([Sales]) }
    ```
*   **EXCLUDE:** Removes a dimension from the calculation for that specific metric.
    ```sql
    { EXCLUDE [Category] : SUM([Sales]) }
    ```

### 2. Handling Nulls (ZN & IFNULL)
Ensure your calculations don't break when data is missing.
*   **ZN:** Converts a null value to zero.
    ```sql
    ZN([Sales]) + ZN([Profit])
    ```
*   **IFNULL:** Replaces a null with a specific value or string.
    ```sql
    IFNULL([Member Name], "Unknown")
    ```

### 3. Ad-Hoc Calculations
*   **The Trick:** Double-click any empty space on the **Rows**, **Columns**, or **Marks** shelf to type a formula directly (e.g., `SUM([Sales]) * 1.1`) without creating a named field in the data pane.
