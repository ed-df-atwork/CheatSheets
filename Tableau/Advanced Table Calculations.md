# Tableau Cheat Sheet: Advanced Table Calculations

### 1. Ranking Functions
Tableau offers different ways to rank data; choosing the right one matters for ties.
*   **RANK:** Standard (1, 2, 2, 4).
*   **RANK_DENSE:** No gaps (1, 2, 2, 3).
*   **RANK_UNIQUE:** Forces a unique rank even if values are identical (1, 2, 3, 4).
    ```sql
    RANK(SUM([Sales]), 'desc')
    ```

### 2. Window Functions (Moving Averages)
Used to "smooth out" volatile data trends.
*   **Moving Average:** Calculates the average of the current row and a specified number of previous/following rows.
    ```sql
    // Average of the last 6 months
    WINDOW_AVG(SUM([Sales]), -6, 0)
    ```

### 3. Lookup & Offset (YoY/MoM)
Access values from other rows in the view without using complex joins.
*   **LOOKUP:** Grab a value from a previous period.
    ```sql
    // Difference from previous month
    SUM([Sales]) - LOOKUP(SUM([Sales]), -1)
    ```

### 4. Running Totals
*   **RUNNING_SUM:** Accumulates values across the view (e.g., "Pacing toward goal").
    ```sql
    RUNNING_SUM(SUM([Sales]))
    ```

### 5. "Compute Using" (Addressing vs. Partitioning)
*   **Table (Across):** Calculates across the entire row.
*   **Pane (Down):** Restarts the calculation for every sub-category (e.g., restarts the rank for every Region).
*   **Specific Dimensions:** The most precise way—manually check which dimensions "restart" the calculation and which ones "run" the calculation.
