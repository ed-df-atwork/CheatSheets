# Narrative & Executive Summaries — Dashboard-to-Story Cheat Sheet

## 1. Executive Summary Framework: Strategic (CARE)
Use this structure to prompt an AI (ChatGPT, Claude, etc.) to translate data into "Business English."


| Letter | Component | Description | Example |
| :--- | :--- | :--- | :--- |
| **C** | **Context** | Background and raw data points. | "Q3 Sales grew 12% but Margin dropped 2%." |
| **A** | **Action** | The specific summary task. | "Identify the primary driver of the margin compression." |
| **R** | **Result** | Desired output format. | "Create a 3-bullet executive summary for the CEO." |
| **E** | **Example** | Sample of the tone. | "Use a 'Headline: [Insight]' format; avoid jargon." |

---

## 2. Converting Dashboard Data to Narrative
Don't just paste an image; paste the **summary statistics** or the **CSV export** for the best results.

### The "Data-to-Narrative" Prompt Pattern:
> "Analyze the following data from my Tableau dashboard. Provide a **One-Page Executive Summary** that answers: 
> 1. What is the 'Bottom Line' (the single most important takeaway)?
> 2. What are the top 3 drivers (the 'Why')?
> 3. What is the 'Next Best Action' (the 'So What')?"

---

## 3. The "So What?" Strategy (Prescriptive Summaries)
Executives care about the **implication**, not just the observation. 


| Instead of Reporting... | AI Should Summarize As... |
| :--- | :--- |
| "Churn is up 5% in the Midwest." | "Midwest churn increased 5%, posing a $200k revenue risk; recommend re-allocating Q4 ad spend to retention." |
| "AOV is $150 per user." | "AOV reached a record $150, driven by the new bundle strategy; suggest expanding this to the West region." |

---

## 4. Refining the Tone & Style
*   **The "Inverted Pyramid":** Tell the AI to put the most important conclusion in the first sentence.
*   **The "BLUF" Method:** Ask for a **Bottom Line Up Front** section.
*   **Constraint Prompting:** "Explain this as if I have only 60 seconds to read it."

```text
PROMPT: "Act as a Strategic Consultant. Summarize the attached performance data. 
Focus on the 'Why' behind the variances. Use the BLUF method. 
Limit the entire response to 250 words. No fluff."
