# 5. Modern Data Infrastructure (Analytic Engineer Lite)

### 1. Data Transformation (dbt)
The logic layer between raw data and the final dashboard.
*   **Modular SQL**: Write code in small, reusable models rather than 1,000-line scripts.
*   **Testing**: Use schema tests to ensure keys are unique and values stay in range.
*   **Documentation**: Every column should have a description in the metadata.

### 2. Version Control (Git) Basics
Essential for collaboration and "undoing" mistakes.
*   **Commit**: Saving your local changes with a descriptive message.
*   **Pull Request (PR)**: Asking a peer to review your code before it goes live.
*   **Merge**: Combining your verified changes into the "Main" production branch.

### 3. Cloud Data Warehouse Patterns
How to interact with Snowflake or BigQuery efficiently.
*   **Snowflake**: Focus on "Virtual Warehouses" (scaling compute separately from storage).
*   **BigQuery**: Focus on "Partitioning" and "Clustering" to reduce query costs.
*   **Syntax Tip**: Use `QUALIFY` in Snowflake/BigQuery to filter window functions without a subquery.
