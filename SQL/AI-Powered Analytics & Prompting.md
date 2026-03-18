# AI-Powered Analytics & Prompting Cheat Sheet

### 1. The R-O-C-E Prompting Framework
Structure requests to Large Language Models (LLMs) to ensure accurate code and analysis.
*   **Role**: Define the persona (e.g., "Act as a Senior SQL Developer").
*   **Objective**: State the goal (e.g., "Optimize this JOIN for a billion-row table").
*   **Context**: Provide schema details (e.g., "Using BigQuery syntax").
*   **Expectation**: Define the output (e.g., "Return only the code with comments").

### 2. SQL Debugging & Refactoring
Use AI to explain errors or modernize legacy scripts.
Prompt: "Explain why this query is hitting a memory limit and rewrite it using CTEs for better readability."

-- AI Output Example:
WITH MonthlySales AS (
    SELECT user_id, SUM(amount) as total 
    FROM sales 
    GROUP BY 1
)
SELECT * FROM MonthlySales WHERE total > 1000;

### 3. Synthetic Data Generation
Generate mock datasets for testing logic without using sensitive production data.
Prompt: "Generate a Python script to create a CSV with 100 rows of 'User_ID' and 'Tier' (Free, Pro)."

import pandas as pd
import random
data = {
    'User_ID': range(1, 101),
    'Tier': [random.choice(['Free', 'Pro']) for _ in range(100)]
}
df = pd.DataFrame(data)

### 4. Natural Language to Python/Pandas
Translate business questions into executable data manipulation code.
Prompt: "Using the 'df' dataframe, write the Pandas code to find the month-over-month growth rate of 'Revenue'."

# Calculate MoM Growth
df['MoM_Growth'] = df['Revenue'].pct_change() * 100

### 5. Automated Insight Summary
Feed AI a summary of results to generate stakeholder-ready bullet points.
Prompt: "I have a 15% drop in churn but a 5% decrease in ARPU. Summarize this for a manager."

*   Insight 1: Retention efforts are working (Churn is down).
*   Insight 2: New users are likely opting for cheaper plans (ARPU dilution).
*   Action: Investigate if churn reduction is coming from low-value segments.
