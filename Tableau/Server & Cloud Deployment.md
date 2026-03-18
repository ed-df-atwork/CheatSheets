# Tableau Cheat Sheet: Server & Cloud Deployment

### 1. Row-Level Security (RLS)
Ensure users only see data relevant to them (e.g., a Regional Manager only sees their region).
*   **The Filter:** Create a calculation using `USERNAME()` or `FULLNAME()`.
    ```sql
    // Logic: Is the user signed in the same as the Manager field?
    USERNAME() = [Manager Username]
    ```
*   **The Trick:** Add this to the **Data Source Filter** (not just the sheet filter) to ensure it applies globally and securely.

### 2. Published vs. Embedded Data Sources
*   **Published (.tds):** Managed centrally on the server. If you update the calculation in the published source, it updates in **all** workbooks using it. (Best for "Single Source of Truth").
*   **Embedded:** Stored inside the `.twb` file. Good for one-off explorations but harder to maintain across a team.

### 3. Extract Refresh Scheduling
*   **Incremental Refresh:** Only adds new rows based on a ID or Date column. Much faster than a full refresh for massive datasets.
*   **Failure Notifications:** Go to **My Account Settings** on the Server/Cloud to enable email alerts if an extract fails to refresh.

### 4. Project Folders & Permissions
*   **Locked Projects:** Set permissions at the Project level so all workbooks inside inherit the same security. This prevents "permission creep" where individual dashboards have different access rules.
*   **Web Authoring:** Use this to make small "emergency" tweaks to a dashboard directly in the browser without needing Tableau Desktop.
