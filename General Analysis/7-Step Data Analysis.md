# 7-Step Data Analysis — The Analytical Lifecycle

## 1. Define
**Goal:** Convert a vague business problem into a clear, measurable question.
*   **Identify Stakeholders:** Who is the decision-maker for this data?
*   **The SMART Question:** Avoid "How are sales?" Instead, ask "Why did Q3 sales in the Northeast drop by 12% compared to Q2?"
*   **Define Success:** What metric (KPI) will prove the hypothesis?

---

## 2. Collect
**Goal:** Gather the raw data from internal and external "Sources of Truth."
*   **Internal:** SQL Databases (Snowflake, SQL Server), CRM (Salesforce), ERP.
*   **External:** APIs, Web Scraping, or Market Research.
*   **Data Log:** Document the source and the "As-Of" date to ensure data freshness.

```sql
-- Example: Extracting raw transaction and user data
SELECT 
    t.transaction_id, 
    t.amount, 
    u.signup_date, 
    u.region
FROM transactions AS t
JOIN users AS u ON t.user_id = u.id
WHERE t.status = 'completed';
```

---

## 3. Clean
**Goal:** Fix inconsistencies to prevent "Garbage In, Garbage Out."
*   **De-duplication:** Remove identical or redundant rows.
*   **Formatting:** Ensure dates are `YYYY-MM-DD` and currency is numeric.
*   **Handling Nulls:** Decide to **Drop** (remove row), **Impute** (fill with mean/median), or **Flag** (mark as 'Unknown').

```python
# Standard Cleaning in Python
df.drop_duplicates(inplace=True)
df['amount'] = df['amount'].fillna(0)
df['signup_date'] = pd.to_datetime(df['signup_date'])
```

---

## 4. Explore (EDA)
**Goal:** Use stats and quick visuals to find the "shape" of your data.
*   **Summary Stats:** Check the Mean, Median, and Standard Deviation.
*   **Outliers:** Identify extreme values that might skew the average.
*   **Distribution:** Use Histograms to see if data is normally distributed or skewed.

---

## 5. Analyze
**Goal:** Apply technical methods to find the actual "Why."
*   **Segmentation:** Compare different groups (e.g., "New Users" vs. "Returning Users").
*   **Trend Analysis:** Look for patterns over time (Seasonality, Cycles).
*   **Correlation:** Calculate if two variables move together.

```python
# Checking correlation between Marketing Spend and Revenue
correlation = df['marketing_spend'].corr(df['revenue'])
print(f"Correlation Strength: {correlation:.2f}")
```

---

## 6. Interpret
**Goal:** Translate the "Data Speak" back into "Business Action."
*   **Synthesize:** Don't just report numbers; explain the *finding* (e.g., "The 5% price increase led to a 15% drop in volume among budget-tier users").
*   **The "So What?":** Identify the business impact of the results.
*   **Limitations:** Be honest about data gaps or small sample sizes.

---

## 7. Visualize & Share
**Goal:** Create the final delivery that drives a decision.
*   **Choose the Right Chart:** 
    *   **Trends:** Line Chart.
    *   **Comparison:** Bar Chart.
    *   **Relationships:** Scatter Plot.
*   **Headline-First:** Every chart title should be the "Key Insight" (e.g., "Northeast Sales are Down 12%").
*   **Call to Action:** End with **Prescriptive** advice on what to do next.

---

## Summary Checklist
- [ ] **Define:** Is the question specific enough to answer?
- [ ] **Collect:** Do I have the "Master" tables?
- [ ] **Clean:** Are the data types correct and duplicates gone?
- [ ] **Explore:** Did I find any weird outliers?
- [ ] **Analyze:** Did I account for seasonality?
- [ ] **Interpret:** Can I explain this to a non-technical manager?
- [ ] **Visualize:** Is the "Action Item" clearly visible?
