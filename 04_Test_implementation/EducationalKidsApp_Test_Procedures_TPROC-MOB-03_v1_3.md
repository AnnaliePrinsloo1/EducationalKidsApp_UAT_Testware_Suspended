# Test Implementation: Test Procedures & Execution Scripts

**Identifier:** TPROC-MOB-03  
**Version:** v1.3  
**Test Basis:** Functional Scope & Requirements (Educational Kids App Test Plan: TP-MOB-03)  
**Status:** Suspended (Entry Criteria Failure) — defined but not yet executed  
**Date:** 2026-09-17  
**Author:** Annalie Prinsloo  

---

## 1. Document Control
### 1.1 Revision History
| Version | Date | Author | Description of Changes |
| :--- | :--- | :--- | :--- |
| 1.1 | 2026-05-25 | Annalie Prinsloo | Baseline test procedures. |
| 1.2 | 2026-05-29 | Annalie Prinsloo | Pre-execution setup annotated with the build-link failure. |
| 1.3 | 2026-09-17 | Annalie Prinsloo | Restructured onto the standard step-table template; procedures assigned dedicated `TPROC-xx-00` identifiers; removed the duplicated "Test Procedures: Navigation (NAV)" heading block that appeared twice in a row; removed inline execution-outcome annotations (`[PASSED]`, `[CRITICAL FAILURE]`, `[BLOCKED]`) from the procedure script — this document stays a neutral, reusable script, with actual outcomes recorded in `EL-MOB-03`. |

---

## 2. Pre-Execution Setup & Environmental Verification Checklist
### Preconditions
* The physical test device is fully unboxed, charged to at least 50%, and powered on.
* A stable Wi-Fi or local mobile network connection is active.
* Biometric authentication (fingerprint) and a backup PIN lock are pre-configured in the OS.

### Procedure
1. Open the system settings app on the device and navigate to About Phone → Software Information.
2. Verify and document that the model code matches SM-G990E/DS, the Android version is 16, and the UI layer reads Samsung One UI 8.0.
3. Open the provided distribution link and install Build v1.1.4.a of the Educational Kids App from Google Play Beta.
4. Open the app immediately after installation to verify initialization parameters, then perform a complete application close from the recent apps manager tray to ensure a clean state.

### Expected Results
* The device firmware details exactly match the environment matrix parameters defined in `TP-MOB-03` §4.
* The application package installs without compilation or runtime exceptions.
* The application boots safely to its home landing viewport on the first launch attempt.

---

## 3. Test Procedure Suite

### TPROC-NAV-01: Main Menu & Tab Navigation Verification
* **Associated Test Case:** `TC-NAV-01`
* **Environmental Setup Steps:** Application is fully installed on the physical device and closed (not running in the background memory stack).

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Tap the app icon on the home screen or app drawer to execute a cold start. | Cold Start | App launches and dashboard views populate. |
| 2 | Locate the secondary navigation sub-tabs or menu categories. | Visual Check | Sub-tabs render clearly. |
| 3 | Sequentially tap each secondary sub-tab item, pausing 1 second after each. | Tab Tap | Views switch instantaneously; active state highlights correctly each time. |
| 4 | Locate the primary horizontal bottom navigation bar. | Visual Check | Bottom nav bar renders at the base of the UI structure. |
| 5 | Tap the second primary menu icon, then sequentially cycle through all remaining primary tabs. | Tab Tap | Screen transitions are clean with no flickering, frozen headers, or frame-rate drops. |

---

### TPROC-NAV-02: Deep Section Traversal & Back-Button Validation
* **Associated Test Case:** `TC-NAV-02`
* **Environmental Setup Steps:** Application is actively running and displaying the root dashboard home panel.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | From the home dashboard, tap a core feature category. | Category Tap | Primary feature panel opens. |
| 2 | Tap a nested sub-section container within that category. | Sub-Section Tap | Deeper content layer loads without rendering delays. |
| 3 | Select an individual child asset or detailed log entry to reach maximum stack depth. | Deep Navigation | Content elements populate accurately. |
| 4 | Tap the app's integrated soft back arrow at the top-left of the UI header. | Soft Back Tap | View shifts up exactly one step in the operational hierarchy. |
| 5 | Perform the physical hardware system back control or One UI back gesture. | System Back | Android system back follows the app history stack without getting stuck or forcing an unintended app exit. |

---

### TPROC-CON-01: High-Accuracy Textual & Asset Rendering
* **Associated Test Case:** `TC-CON-01`
* **Environmental Setup Steps:** Device is connected to an active local network.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Navigate to the primary caregiver educational notes resource listing view. | Navigation | Resource listing renders. |
| 2 | Select a note containing long paragraphs, bold titles, and image attachments. | Note Selection | Note opens with text and images. |
| 3 | Perform a rapid, continuous scroll sweep to the bottom of the text block view. | Scroll Sweep | Text displays exact alignment without overlapping strings or broken font shapes; images load instantly without placeholder errors. |
| 4 | Minimize the app, disable Wi-Fi and mobile data via quick settings, and re-enter the app. | Offline Toggle | App remains open. |
| 5 | Select the identical note from the directory index. | Offline Note Access | Offline execution pulls the local cached content securely, or shows a friendly warning rather than crashing. |

---

### TPROC-CON-02: External Resource Link Redirection Integrity
* **Associated Test Case:** `TC-CON-02`
* **Environmental Setup Steps:** A standard default browser is set under device system settings.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Open a caregiving resource article containing third-party hyperlinks. | Navigation | Article opens. |
| 2 | Tap the highlighted external hyperlink text. | Link Tap | External browser engine is safely triggered. |
| 3 | Observe the system transition behavior. | Visual Check | Target web resource loads successfully in the system browser. |
| 4 | Execute the system back action to return to the app. | System Back | App remains running in the background, keeping its place in the UI stack. |

---

### TPROC-UI-01: Input Form Field Boundary & Checkbox Compliance
* **Associated Test Case:** `TC-UI-01`
* **Environmental Setup Steps:** App is open on a caregiving input form view or custom profile configuration screen.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Select the primary text input field and enter valid string data. | Valid Input | Field accepts input normally. |
| 2 | Attempt to input extreme character boundaries (500+ characters, or emoji). | Boundary Input | Field rejects overflow or truncates excess strings elegantly. |
| 3 | Tap all individual checkbox selection items visible on the profile layout. | Checkbox Taps | Checkboxes toggle cleanly. |
| 4 | Clear the text input completely and attempt to submit. | Empty Submission | Descriptive validation hint displays instead of the UI freezing. |

---

### TPROC-UI-02: Button & Touch Target Responsiveness
* **Associated Test Case:** `TC-UI-02`
* **Environmental Setup Steps:** Display is clean; touch calibration on the Exynos 2100 hardware is normal.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Tap closely along the outermost perimeter edge of an interface action button. | Edge Tap | Touch registers accurately within reasonable proximity. |
| 2 | Perform rapid, successive taps on a single toggle switch. | Rapid Multi-Tap | No queuing conflicts or race-condition lockups. |
| 3 | Tap adjacent interactive elements in quick succession across the layout. | Sequential Tap | Each element responds correctly without cross-triggering. |

---

### TPROC-PERF-01: Interface Rendering Stability & Scroll Metrics
* **Associated Test Case:** `TC-PERF-01`
* **Environmental Setup Steps:** No performance-throttling battery-saver profiles are active on the S21 FE.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Navigate into a highly detailed text section or large scrollable grid view. | Navigation | Section loads. |
| 2 | Drag downward rapidly for an aggressive scroll sweep to the bottom edge. | Scroll Down | Scrolling runs smoothly at a constant frame rate. |
| 3 | Drag upward instantly back to the top edge. | Scroll Up | No tearing, stuttering, or reflow shifts during motion. |
| 4 | Watch screen composition for visual anomalies or frame drops. | Visual Check | No anomalies observed. |

---

### TPROC-ACC-01: Dynamic Font Scaling & Layout Integrity
* **Associated Test Case:** `TC-ACC-01`
* **Environmental Setup Steps:** Exit the app. Go to Android System Settings → Display → Font size and style. Set the Font Size slider to maximum scale.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Relaunch the application. | Relaunch | App opens with max font scale applied. |
| 2 | Inspect text alignment and spacing across the main dashboard. | Visual Check | Text auto-scales appropriately. |
| 3 | Navigate through the core caregiver notes sections. | Navigation | Words reflow cleanly into multi-line configurations without clipping or overlapping. |
| 4 | Inspect text presentation on views with action confirmation buttons at the base of the UI. | Visual Check | Buttons remain fully on-screen, not pushed off by text reflow. |

---

### TPROC-INT-01: Note Preservation During Active Voice Call Interruption
* **Associated Test Case:** `TC-INT-01`
* **Environmental Setup Steps:** App is running; an entry view is open with a half-completed sentence typed into a note input box.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Trigger an incoming voice call or mock background dialer call. | Incoming Call | Call screen overlay appears. |
| 2 | Allow the call overlay to block the app UI for at least 15 seconds. | Wait (15s) | App is fully backgrounded. |
| 3 | Terminate or decline the incoming call. | Decline/End Call | Call overlay dismisses. |
| 4 | Resume the app from the recent applications tray. | Resume | App retains its exact pre-interruption state; the draft sentence remains intact without data loss or memory exceptions. |

---

### TPROC-INT-02: State Retention on Hardware System Interruptions
* **Associated Test Case:** `TC-INT-02`
* **Environmental Setup Steps:** App is active on a deep content or educational notes screen.

| Step # | Action Description | Target Data/Input | Expected System Response |
| :--- | :--- | :--- | :--- |
| 1 | Press the hardware Power/Lock button to lock the screen completely. | Lock | Screen locks. |
| 2 | Keep the device locked for 30 seconds. | Wait (30s) | — |
| 3 | Unlock using biometric or PIN authentication. | Unlock | App recovers instantly from the sleep transition without returning to the boot logo or home screen. |
| 4 | Trigger a simulated low-battery warning, or pull down and clear the quick settings shade. | System Overlay | App retains exact scroll depth, active tab, and data view state. |
