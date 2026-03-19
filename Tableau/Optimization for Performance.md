# Optimization for Performance

### 1. The "Golden Rules" of Tableau SQL
Tableau is a metadata-heavy tool; every column and row you pull adds "weight" to the workbook.

*   **Never use `SELECT *`**: Only select the columns you actually need for your dashboard. Extra columns increase the size of the metadata and slow down the initial connection.
*   **Filter in the `WHERE` clause**: Filter data as close to the source as possible. Do not wait to filter in Tableau if the data isn't needed.
*   **Avoid `ORDER BY`**: Tableau has its own sorting engine. Including an `ORDER BY` in your SQL view or Custom SQL adds unnecessary processing time for the database.

---

### 2. Custom SQL vs. Views vs. Initial SQL
How you get data into Tableau matters more than the query itself.


| Method | Performance Impact | Best Use Case |
| :--- | :--- | :--- |
| **Database View** | **High** | Pre-calculated logic handled by the DB engine; highly recommended. |
| **Initial SQL** | **Medium** | Best for setting up Temp Tables or Session variables before the query runs. |
| **Custom SQL** | **Low** | Avoid if possible. Tableau wraps Custom SQL in a subquery, which can bypass DB indexes. |

---

### 3. Aggregating at the Source
If you have 100 million rows of transactions but only show **Monthly Sales** in your dashboard, do not pull the raw transactions.

```sql
-- SLOW: Pulling raw data and letting Tableau aggregate
SELECT transaction_date, sale_amount, store_id FROM sales_table;

-- FAST: Aggregating in SQL to reduce row count
SELECT 
    DATE_TRUNC('month', transaction_date) as sale_month,
    store_id,
    SUM(sale_amount) as total_sales
FROM sales_table
GROUP BY 1, 2;
```

---

### 4. Join Optimization
Tableau's "Relationships" (the Noodles) are generally faster than hard-coding Joins in SQL because they use **Join Culling** (only joining tables when fields from both are used).

*   **Join on Integers**: Joining on `ID` (integer) is significantly faster than joining on `String` names.
*   **Minimize Joins**: If you must join in SQL, ensure the join keys are **indexed** in the database.
*   **Union All**: If combining data, use `UNION ALL` instead of `UNION`. `UNION` performs a distinct check to remove duplicates, which is much slower.

---

### 5. Advanced Query Techniques
Using modern SQL features to make your data "Tableau-ready."

#### Common Table Expressions (CTEs)
Use CTEs instead of nested subqueries for readability and often better execution plans.
```sql
WITH regional_sales AS (
    SELECT region_id, SUM(sales) as total
    FROM sales
    GROUP BY region_id
)
SELECT r.region_name, s.total
FROM regional_sales s
JOIN regions r ON s.region_id = r.id;
```

#### Handling Distinct Counts
`COUNT(DISTINCT user_id)` is one of the most expensive operations in Tableau. If possible, create a flag or a pre-aggregated table in SQL.
```sql
-- Create a unique flag in a View to avoid "Count Distinct" overhead
SELECT user_id, 
       MIN(transaction_date) OVER(PARTITION BY user_id) as first_purchase
FROM sales;
```

---

### 6. Data Types & Formatting
*   **Cast Dates correctly**: Ensure date columns are actual `DATE` or `DATETIME` types. If they are strings, Tableau has to "guess" or convert them, which adds latency.
*   **Boolean Flags**: Convert strings like 'Yes'/'No' to `1/0` or `True/False` at the SQL level.
*   **Clean Strings**: Use `TRIM()` and `UPPER()` in your SQL view so Tableau doesn't have to process string cleanup on every refresh.
```sql
SELECT 
    TRIM(UPPER(customer_name)) as customer_name_clean,
    COALESCE(phone_number, 'Unknown') as contact_info
FROM customers;
```

### 7. Filter Efficiency
*   **Context Filters:** Right-click a filter and select **Add to Context** (it turns gray). This forces Tableau to filter the data *before* other filters or LODs are calculated.
*   **Data Types:** Use **Boolean** (True/False) or **Integer** (0, 1) filters. They are significantly faster for Tableau to process than long String filters.

### 8. Data Cleaning & Extraction
*   **Hide Unused Fields:** In the Data Pane menu, select **Hide All Unused Fields**. This reduces the size of your `.hyper` extract and improves load times.
*   **Extract Filters:** Apply filters at the **Extract** level (during the data connection phase) to remove rows you don't need before they even enter the workbook.

### 9. Reducing Marks
*   **The Tip:** A dashboard with 50,000 marks will be slow. Use **Summary Tables** or **Aggregated Views** first, and allow users to "drill down" to the details to keep the initial load fast.
