# AI Prompting Frameworks for Analysts

## 1. The ROCE Framework
**Best For:** Standardizing technical requests and ensuring consistent output formats.


| Letter | Component | Description | Example |
| :--- | :--- | :--- | :--- |
| **R** | **Role** | Define the persona. | "Act as an Alteryx Lead Developer." |
| **O** | **Objective** | The specific goal. | "Optimize this workflow for the AMP engine." |
| **C** | **Context** | Background info. | "The current workflow joins 5 tables from Snowflake." |
| **E** | **Expectation**| The final format. | "Provide a list of 5 specific tool changes." |

---

## 2. The RISEN Framework
**Best For:** Complex strategic research and deep problem-solving.

*   **Role:** Senior Business Analyst.
*   **Input:** "I have a CSV of Q3 churn data."
*   **Scenario:** "Our top competitors just launched a 50% discount campaign."
*   **Expectation:** "Identify the top 3 segments most likely to switch."
*   **Nuance:** "Keep the tone professional and avoid overly technical ML terms."

---

## 3. The CARE Framework
**Best For:** Drafting summaries or communicating results to stakeholders.

*   **Context:** "We just finished the year-end financial audit."
*   **Action:** "Summarize the findings regarding operational spend."
*   **Result:** "Create a 3-bullet summary for the CFO."
*   **Example:** "Use a style like: [Category] - [Status] - [Delta]."

---

## 4. The CODE Framework (Technical Tasks)
**Best For:** Generating SQL, Python, or automated logic.

```text
TASK: Write a Snowflake SQL query.
OBJECTIVE: Calculate 7-day rolling revenue per customer.
ENVIRONMENT: Table 'orders' with columns 'cust_id', 'order_date', and 'total'.
FORMAT: Use a Common Table Expression (CTE) and include inline comments.
```

---

## 5. Advanced Prompting Techniques

### Chain-of-Thought (CoT)
Forces the AI to "think step-by-step," reducing errors in math or logic.
*   **The Magic Phrase:** "Let's work through this step-by-step."
*   **Usage:** Essential when asking the AI to interpret a statistical result or debug complex code.

### N-Shot Prompting
Providing examples within the prompt to steer the AI toward a specific pattern.
*   **Zero-Shot:** "Write a Python script to clean this date column."
*   **One-Shot:** "Write a Python script. Example: [Input Format] -> [Cleaned Format]."
*   **Few-Shot:** Providing 3+ examples. (Best for complex parsing like Regex).

---

## 6. Analyst’s "Prompt Refinement" Checklist
- [ ] **Persona:** Did I tell the AI who it is (e.g., "Act as a Tableau Expert")?
- [ ] **Constraints:** Did I tell it what *not* to do (e.g., "Do not use subqueries")?
- [ ] **Format:** Did I specify the output (e.g., "Table," "Markdown," "JSON")?
- [ ] **Clarification:** Did I end with "Ask me 3 questions to ensure you have enough context"?
