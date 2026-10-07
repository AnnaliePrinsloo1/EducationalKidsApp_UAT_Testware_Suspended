## Defect Report: BUG-MOB-03-01

### 1. Summary Information
* **Defect ID:** BUG-MOB-03-01  
* **Title:** Google Play Beta build distribution link unreachable / returns 404 routing error  
* **Status:** New  
* **Date Logged:** 2026-05-29  
* **Reporter:** Annalie Prinsloo  
* **Target Fix Version:** N/A — environment/deployment issue, not a product build  

### 2. Classifications
* **Defect Type:** Environment / Deployment (Build Distribution)
* **Severity:** Critical
* **Priority:** High
* **Reproducibility:** Consistent

### 3. Traceability & Environment
* **Traced To:** All 10 test conditions in `TCOND-MOB-03` (environment-level blocker, not isolated to a single condition)
* **Hardware/Device:** Samsung Galaxy S21 FE 5G (Android 16, One UI 8.0)
* **Build Version:** Google Play Beta Build v1.1.4.a (deployment layer / distribution endpoint)

### 4. Description & Steps to Reproduce
* **Description:** During environment verification, the provided Google Play Beta application distribution link failed to resolve across both Wi-Fi and cellular network infrastructure. Because the application package cannot be installed onto the physical target device, all 10 planned test cases are completely blocked. Severity was assessed as Critical because this is the most severe possible impact under this portfolio's severity scale — it prevents 100% of planned testing activity outright, with no workaround available. Note: this project's original documentation used a non-standard "Blocker" severity label; it has been remapped to Critical (the top of this portfolio's Critical/Major/Minor/Trivial scale) for consistency, since "Blocker" isn't an ISTQB-defined severity tier. Priority was assessed as High given the urgency of unblocking the entire UAT cycle.

* **Steps to Reproduce:**
  1. On the target device, launch the internet browser.
  2. Navigate to the formal Beta package deployment link provided by development.
  3. Trigger the navigation event and observe the result.
  4. Repeat using an independent cellular 5G network profile to isolate local network constraints.

### 5. Test Results
* **Expected Results:** The distribution link resolves cleanly, launching the Google Play Beta store page, automatically checking safety signatures, and successfully downloading installable build v1.1.4.a to local storage.
* **Actual Results:** The browser attempts to route the address but fails to locate a live endpoint, dropping into a dead landing page with a server error (e.g. "404 URL Not Found" or "Item Unresolved on Store"). No installation wrapper or package asset can be pulled onto the device.

### 6. Evidence & Attachments
* **Communications Log:**
  * 2026-05-29 08:45 — Environment deployment failure confirmed.
  * 2026-05-29 09:30 — Pinged the primary developer chat channel with the link string and error screenshots. *(Status: Unread / No Response)*
  * 2026-05-29 11:00 — Escalated via email to the project management distribution list, flagging developer channel silence. *(Status: Awaiting Review)*

### 7. Closure & Resolution
* **Status:** Not yet resolved (see Section 1 for current status)
* **Resolution Reason:** N/A — defect remains open pending fix
* **Closing Comment:** N/A
