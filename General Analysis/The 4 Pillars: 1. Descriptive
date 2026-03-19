# Pillar 1: Descriptive Analytics (Hindsight)
**Goal:** Summarize historical data to explain "What happened?" This is the foundation of all reporting.

## 1. Core Objectives
*   Identify trends over time.
*   Compare actual performance against targets or historical benchmarks.
*   Summarize large datasets into digestible KPIs.

## 2. Common Techniques
*   **Aggregations:** Using `SUM`, `AVG`, `COUNT`, `MIN`, `MAX`.
*   **Time-Series Tracking:** Year-over-Year (YoY) or Month-over-Month (MoM) growth.
*   **Distribution:** Understanding the spread of data using Histograms.

## 3. SQL Implementation
```sql
-- Calculating Monthly Revenue and Growth
SELECT 
    DATE_TRUNC('month', order_date) AS month,
    SUM(revenue) AS current_month_revenue,
    LAG(SUM(revenue)) OVER (ORDER BY DATE_TRUNC('month', order_date)) AS prev_month_revenue,
    (SUM(revenue) - LAG(SUM(revenue)) OVER (ORDER BY DATE_TRUNC('month', order_date))) / 
     NULLIF(LAG(SUM(revenue)) OVER (ORDER BY DATE_TRUNC('month', order_date)), 0) * 100 AS growth_pct
FROM sales_data
GROUP BY 1;
```

## 4. Best Practices
*   **Standardize Metrics:** Ensure "Revenue" is calculated the same way across all reports.
*   **Visuals:** Use **Line Charts** for trends and **Bar Charts** for comparisons.
*   **Data Freshness:** Clearly state the "As-of" date (e.g., "Data refreshed as of 8:00 AM").

