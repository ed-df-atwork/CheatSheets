# Deep Dive: How to Perform the 4 Pillars of Analytics

## Pillar 1: Descriptive Analytics (What happened?)
**The Goal:** Summarize raw data into a coherent "Current State" narrative.

### 1. Identify the Grain of Data
Decide the level of detail (e.g., Daily Sales, Hourly Web Traffic).
### 2. Aggregate Data (SQL)
Use `SUM()`, `AVG()`, `COUNT()`, and `GROUP BY` to condense millions of rows.
### 3. Benchmarking
Compare current numbers against a baseline (Last Year, Last Month, or a Goal).

```sql
-- Calculating Year-over-Year (YoY) Sales Growth
SELECT 
    EXTRACT(YEAR FROM order_date) AS year,
    SUM(revenue) AS current_year_rev,
    LAG(SUM(revenue)) OVER (ORDER BY EXTRACT(YEAR FROM order_date)) AS prev_year_rev
FROM orders
GROUP BY 1;
```

---

## Pillar 2: Diagnostic Analytics (Why did it happen?)
**The Goal:** Isolate variables and find the "Root Cause."

### 1. Drift & Variance Analysis
Calculate the difference between "Actual" and "Expected." If Sales are down 10%, where is that 10% coming from?
### 2. Drill-Downs (Tableau/Alteryx)
Break the data into segments (Region, Product Category, Customer Tier) to see which segment is "pulling the average down."
### 3. Correlation Testing
Use a Scatter Plot or Correlation Matrix to see if two variables move together.

```python
# Check if Page Load Speed affects Conversion Rate
import pandas as pd
correlation = df['load_speed'].corr(df['conversion_rate'])
print(f"Correlation Coefficient: {correlation:.2f}")
# If < -0.7, slow speeds are likely CAUSING the lower conversions.
```

---

## Pillar 3: Predictive Analytics (What will happen?)
**The Goal:** Move from "Historical Patterns" to "Future Probabilities."

### 1. Feature Engineering
Identify "Leading Indicators." For a "Churn Prediction" model, a leading indicator might be "Days since last login."
### 2. Selection of Model
*   **Time Series (Prophet/ARIMA):** For trends over time (Sales Forecast).
*   **Classification (Logistic Regression/Random Forest):** For Yes/No outcomes (Will they buy?).
*   **Regression:** For predicting a specific number (How much will they spend?).
### 3. Validation
Always split your data into **Train** and **Test** sets. If your model works on the "Train" data but fails on the "Test" data, it has "overfit" and is useless.

```python
from sklearn.ensemble import RandomForestClassifier
# Train model to predict churn (1 = Yes, 0 = No)
model = RandomForestClassifier()
model.fit(X_train, y_train)
# Predict probability for current customers
probabilities = model.predict_proba(X_current_customers)
```

---

## Pillar 4: Prescriptive Analytics (How can we make it happen?)
**The Goal:** Provide a "Decision Engine" or a specific "Next Best Action."

### 1. Scenario Modeling ("What-If" Analysis)
Create a model where users can change variables (e.g., "If we increase ad spend by 10%, what is the projected ROI?").
### 2. Optimization Algorithms
Use math to find the best outcome given specific constraints (e.g., Route optimization for delivery trucks to save fuel).
### 3. Business Rule Logic
Automate the recommendation based on the Predictive score.

```sql
-- Automating Prescriptive Actions based on Predictive Scores
SELECT 
    customer_id,
    churn_probability,
    CASE 
        WHEN churn_probability > 0.85 THEN 'Call customer immediately with 20% discount offer'
        WHEN churn_probability BETWEEN 0.60 AND 0.85 THEN 'Send re-engagement email sequence'
        ELSE 'Maintain standard marketing'
    END AS next_best_action
FROM model_predictions;
```

---

## Summary Checklist for the Analyst
1. **Descriptive:** Did I define the "What" accurately?
2. **Diagnostic:** Did I find the specific segment or "Why" driving the change?
3. **Predictive:** Did I provide a "Confidence Interval" or probability for my forecast?
4. **Prescriptive:** Did I give the stakeholder a clear, actionable instruction?
