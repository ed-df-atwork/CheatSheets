# Tableau Tips and Tricks Cheat Sheet

### 1. Repeat Row Labels (The `INDEX()` Trick)
Used to force Tableau to repeat dimension labels on every row instead of merging them, which is essential for text-based reports or Excel exports.

**Step-by-Step Instructions:**
1.  **Create a Calculation:** Create a new calculated field named `Index` with the formula: `INDEX()`.
2.  **Add to Rows:** Drag the `Index` field to the **Rows** shelf.
3.  **Make Discrete:** Right-click the Index pill in the Rows shelf and select **Discrete** (it will turn blue).
4.  **Position:** Drag the Index pill to the **far left** of the row shelf, before all other dimensions.
5.  **Hide Header:** Right-click the Index pill again and uncheck **Show Header**. This hides the numbers while forcing the labels to repeat.

**Key Takeaways:**
*   **Result:** Treats every row as a unique record, repeating dimensions that would normally be merged.
*   **Use Case:** Ideal for creating detailed table reports designed for exporting to Excel.
*   **Note:** This is a display trick; it does not perform true data densification in the underlying data set.

---

### 2. Global Sorting (The "Discrete Measure" Hack)
Allows you to sort values across different categories/dimensions effectively.

**Step-by-Step Instructions:**
1.  **Duplicate Measure:** Hold **Ctrl** and drag the measure (the column you want to sort by) to the **far left** of the Rows shelf.
2.  **Make Discrete:** Right-click that measure on the shelf and select **Discrete** (it will turn blue).
3.  **Sort:** Right-click it again and select **Sort** to set your ascending or descending order.
4.  **Hide Header:** Right-click the pill once more and uncheck **Show Header** to hide the "sorting column" while maintaining the specific order.

---

### 3. Date Selection (Current vs. Previous)
A common trick for "Month-over-Month" or "Year-over-Year" comparisons.

```sql
// Create a Boolean calculation to filter to current year
YEAR([Order Date]) = YEAR(TODAY())

// Create a calculation for "YTD" (Year to Date)
[Order Date] <= TODAY() AND DATEDIFF('year', [Order Date], TODAY()) = 0
```

---

### 4. Dynamic Titles & Tooltips
Make your dashboard more interactive by using Parameters in your text.

*   **Step:** Insert a parameter or field into a Title by clicking **Insert** at the top right of the "Edit Title" dialog.
*   **Use Case:** "Sales Performance for <Region Parameter>" will update automatically as the user changes the filter.

---

### 5. Performance Optimization
*   **Hide Unused Fields:** Before publishing, go to the Data Pane menu and select **Hide All Unused Fields** to reduce extract size.
*   **Context Filters:** Right-click a filter and select **Add to Context** (turns gray) to force it to run before other filters—useful for Top N filters.
*   **Boolean/Integer Filters:** Use `0/1` or `True/False` instead of String filters for faster processing on large datasets.
