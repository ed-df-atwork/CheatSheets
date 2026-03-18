# Tableau Cheat Sheet: Performance Optimization

### 1. Filter Efficiency
*   **Context Filters:** Right-click a filter and select **Add to Context** (it turns gray). This forces Tableau to filter the data *before* other filters or LODs are calculated.
*   **Data Types:** Use **Boolean** (True/False) or **Integer** (0, 1) filters. They are significantly faster for Tableau to process than long String filters.

### 2. Data Cleaning & Extraction
*   **Hide Unused Fields:** In the Data Pane menu, select **Hide All Unused Fields**. This reduces the size of your `.hyper` extract and improves load times.
*   **Extract Filters:** Apply filters at the **Extract** level (during the data connection phase) to remove rows you don't need before they even enter the workbook.

### 3. Reducing Marks
*   **The Tip:** A dashboard with 50,000 marks will be slow. Use **Summary Tables** or **Aggregated Views** first, and allow users to "drill down" to the details to keep the initial load fast.
