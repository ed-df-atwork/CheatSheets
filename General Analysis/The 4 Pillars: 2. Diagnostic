# Pillar 2: Diagnostic Analytics (Insight)
**Goal:** Dig deeper into the descriptive data to answer "Why did it happen?"

## 1. Core Objectives
*   Identify anomalies and outliers.
*   Discover correlations between different variables.
*   Perform root-cause analysis on performance gaps.

## 2. Common Techniques
*   **Drill-Downs:** Breaking a high-level metric (National Sales) into sub-components (Region > Store > Product).
*   **Data Mining:** Finding hidden patterns or clusters in the data.
*   **Correlation Analysis:** Determining if two variables move together (e.g., "Does website speed affect bounce rate?").

## 3. Python Implementation
```python
# Correlation Heatmap to find relationships
import seaborn as sns
import matplotlib.pyplot as plt

# Identify which factors correlate with Customer Churn
plt.figure(figsize=(10, 8))
correlation_matrix = df.corr()
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm')
plt.title('Diagnostic Correlation Matrix')
plt.show()
```

## 4. Best Practices
*   **Isolate Variables:** Use A/B testing to confirm if a specific change caused a specific result.
*   **Skepticism:** Correlation does not equal causation. Always look for "Confounding Variables."
*   **Context:** Check external factors (e.g., "Did sales drop because of a holiday or a website bug?").
