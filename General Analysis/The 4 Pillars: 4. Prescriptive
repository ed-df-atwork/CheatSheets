# Pillar 4: Prescriptive Analytics (Optimization)
**Goal:** Suggest specific actions to answer "How can we make it happen?"

## 1. Core Objectives
*   Recommend the "Next Best Action" for a customer or business unit.
*   Optimize resources (Budget allocation, Staffing levels, Logistics).
*   Automate decision-making processes.

## 2. Common Techniques
*   **What-If Simulations:** Testing different scenarios (e.g., "What if we increase the price by 5%?").
*   **Optimization Algorithms:** Finding the "Best" path given constraints (e.g., Linear Programming).
*   **Heuristic Logic:** Creating business rules based on predictive scores.

## 3. SQL/Logic Implementation
```sql
-- Generating Automated Recommendations
WITH customer_risk AS (
    SELECT 
        customer_id, 
        churn_score -- Generated from Predictive Model
    FROM churn_predictions
)
SELECT 
    customer_id,
    CASE 
        WHEN churn_score > 0.9 THEN 'IMMEDIATE: Assign Account Manager for Retention Call'
        WHEN churn_score > 0.7 THEN 'HIGH: Send 20% Discount Email'
        WHEN churn_score > 0.5 THEN 'MEDIUM: Include in Educational Newsletter'
        ELSE 'LOW: No Action Needed'
    END AS prescriptive_action
FROM customer_risk;
```

## 4. Best Practices
*   **Actionable Output:** Don't just provide data; provide a specific instruction (e.g., "Buy," "Sell," "Call").
*   **Feedback Loops:** Track if the suggested action actually improved the outcome.
*   **Constraints:** Account for real-world limits like limited budget, time, or inventory.
