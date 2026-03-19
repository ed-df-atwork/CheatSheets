# Data & Business Analyst — General Best Practices

## 1. Problem Definition (The "Why")
*   **The Stakeholder "Why":** Never start a project without a clear business question. Ask: "What decision will be made based on this data?"
*   **KPI Alignment:** Ensure your metrics (Primary vs. Secondary) actually track the business objective, not just "vanity" numbers (e.g., use *Conversion Rate* instead of just *Page Views*).
*   **Success Criteria:** Define what "good" looks like before you analyze.

## 2. Data Quality & Integrity
*   **GIGO (Garbage In, Garbage Out):** Always validate your row counts, null values, and data types before starting analysis.
*   **Source of Truth:** Identify which system is the "Master" (e.g., CRM vs. Finance ERP) to avoid conflicting numbers.
*   **Documentation:** Maintain a Data Dictionary. Define what "Active User" or "Gross Margin" means so everyone is using the same language.

## 3. Analysis Workflow
*   **EDA (Exploratory Data Analysis):** Check for outliers and skewness early. Don't let a single extreme data point ruin your average.
*   **Reproducibility:** If you use Excel, document your steps. If you use SQL/Python, comment your code so a peer can run it and get the same result.
*   **Correlation != Causation:** Just because two things move together doesn't mean one caused the other. Always look for the "hidden" variable.

## 4. Visualization & Communication
*   **Know Your Audience:** 
    *   **Executives:** Need "The Bottom Line" (High-level KPIs, clear trends).
    *   **Managers:** Need "The Driver" (Why is this happening?).
    *   **Operators:** Need "The Action" (List of accounts to call, specific items to fix).
*   **The "So What?":** Every chart should have a headline that explains the takeaway (e.g., instead of "Monthly Revenue," use "Revenue Increased 15% due to Holiday Promo").
*   **Color Theory:** Use color to highlight the *exception*, not just to make it pretty.

## 5. Analyst Soft Skills



| Skill | Best Practice |
| :--- | :--- |
| **Skepticism** | If the data looks too good to be true, it’s probably a tracking bug. |
| **Communication** | Translate "P-values" and "Standard Deviations" into "Business Risk" and "Confidence." |
| **Curiosity** | Don't just report that sales are down; dig into *which* region or product is driving it. |
| **Iteration** | Treat your first dashboard as a draft. Get user feedback early and often. |

## 6. The "Analyst's Toolbox" Logic
*   **Excel:** Best for quick "what-if" modeling and small, ad-hoc data cleaning.
*   **SQL:** Best for large-scale data extraction and transformation (The Foundation).
*   **Tableau/PowerBI:** Best for recurring, interactive storytelling and monitoring.
*   **Python/R:** Best for advanced statistics, automation, and machine learning.

## 7. Final Checklist before Presenting
1. [ ] Did I double-check my totals against a known source?
2. [ ] Are my axes labeled and do they start at zero (unless there's a reason not to)?
3. [ ] Did I answer the original business question?
4. [ ] Is the most important insight the biggest thing on the page?
