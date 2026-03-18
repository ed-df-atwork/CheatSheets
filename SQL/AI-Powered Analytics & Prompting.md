# AI-Powered Analytics & Prompting Cheat Sheet

### 1. The R-O-C-E Prompting Framework
Structure requests to Large Language Models (LLMs) to ensure accurate code and analysis.
*   **Role**: Define the persona (e.g., "Act as a Senior SQL Developer").
*   **Objective**: State the goal (e.g., "Optimize this JOIN for a billion-row table").
*   **Context**: Provide schema details (e.g., "Using BigQuery syntax").
*   **Expectation**: Define the output (e.g., "Return only the code with comments").

### 2. SQL Debugging & Refactoring
Use AI to explain errors or modernize legacy scripts.
**Prompt:** *"Explain why this query is hitting a memory limit and rewrite it using CTEs for better readability."*

```sql
-- AI Output: Optimized with CTEs
WITH MonthlySales AS (
    SELECT user_id, SUM(amount) as total 
    FROM sales 
    GROUP BY 1
)
SELECT * FROM MonthlySales WHERE total > 1000;
