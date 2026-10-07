# Test Design: Manual Test Cases Suite

**Identifier:** TC-MOB-03  
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
| 1.1 | 2026-05-25 | Annalie Prinsloo | Baseline manual test cases suite. |
| 1.2 | 2026-05-29 | Annalie Prinsloo | Marked suspended pending environment resolution. |
| 1.3 | 2026-09-17 | Annalie Prinsloo | Restructured onto the standard field-based template; added the missing `TC-ACC-01` sub-header (Test Suite 5 previously had no named case heading, despite being referenced everywhere else as `TC-ACC-01`); corrected `TC-INT-01`'s Priority from "Critical" to "High" — Priority and Severity are tracked on separate scales per this portfolio's convention, and "Critical" belongs to the Severity scale, not Priority; identifiers confirmed against `TCOND-MOB-03`. |

---

## 2. High-Level Test Suite Overview
This test suite defines the concrete manual test cases for the UAT phase of the Educational Kids App (Beta). All test cases below are fully designed and ready for execution, but remain unexecuted as of this cycle — see `EL-MOB-03` and `TSR-MOB-03` for the suspension status. All test cases execute on the single target device defined in `TP-MOB-03` §4 (Samsung Galaxy S21 FE 5G, Android 16).

---

## 3. Test Suite 1: Navigation (NAV)

### TC-NAV-01: Main Menu & Tab Navigation Verification
* **Description:** Verify structural view switching and lateral tab navigation responsiveness.
* **Target Test Condition:** `TCOND-NAV-01`
* **Preconditions:** App is installed and freshly launched (cold start); device navigation gestures/buttons are fully functional.
* **Test Data Category:** Primary dashboard tabs and secondary navigation menu items.
* **Expected Result:** App switches views immediately; navigation bar updates active states seamlessly with no screen flickering or structural stalls.
* **Priority:** High

### TC-NAV-02: Deep Section Traversal & Back-Button Validation
* **Description:** Validate backward navigation paths from deep content screens without UI loop traps.
* **Target Test Condition:** `TCOND-NAV-02`
* **Preconditions:** App is running; user is on the main dashboard layout.
* **Test Data Category:** Nested sub-section and child-entry navigation depth; soft back arrow and hardware/system back gesture.
* **Expected Result:** Deep navigation loads correct child elements without performance drops; back-navigation accurately follows the historical stack without trapping the user in UI loops or forcing unexpected app exits.
* **Priority:** High

---

## 4. Test Suite 2: Content Delivery (CON)

### TC-CON-01: High-Accuracy Textual & Asset Rendering
* **Description:** Verify all educational resources, images, and notes populate completely upon tap, including under offline conditions.
* **Target Test Condition:** `TCOND-CON-01`
* **Preconditions:** Stable local network connection active on the Samsung S21 FE device.
* **Test Data Category:** Educational notes containing text and image attachments; offline (Wi-Fi/data disabled) state.
* **Expected Result:** Text displays crisp layout formatting; images render correctly without placeholder errors or blank states. Offline execution displays cached text safely or serves a friendly system alert rather than crashing.
* **Priority:** High

### TC-CON-02: External Resource Link Redirection Integrity
* **Description:** Validate that external web resource links launch safely without breaking the app session.
* **Target Test Condition:** `TCOND-CON-02`
* **Preconditions:** Device has a default internet browser selected in Android settings.
* **Test Data Category:** Caregiving resource articles containing third-party hyperlinks.
* **Expected Result:** Tapping the link safely triggers the external browser; the app remains running in the background and keeps its place in the UI stack upon return.
* **Priority:** Medium

---

## 5. Test Suite 3: UI Interactions (UI)

### TC-UI-01: Input Form Field Boundary & Checkbox Compliance
* **Description:** Test data input entry boundaries within text boxes using multi-field forms.
* **Target Test Condition:** `TCOND-UI-01`
* **Preconditions:** App is open on a caregiving input form view or custom profile configuration screen.
* **Test Data Category:** Valid string data; extreme character boundaries (500+ characters, emoji); empty mandatory fields.
* **Expected Result:** Entry boxes reject overflows or truncate excess strings elegantly; checkboxes toggle cleanly; empty mandatory forms display descriptive validation hints instead of freezing the UI.
* **Priority:** High

### TC-UI-02: Button & Touch Target Responsiveness
* **Description:** Verify touch target distribution responsiveness across active screen boundaries.
* **Target Test Condition:** `TCOND-UI-02`
* **Preconditions:** Display is clean; touch responsiveness calibration on the Exynos 2100 hardware is normal.
* **Test Data Category:** Perimeter-edge taps on action buttons; rapid successive multi-taps across adjacent elements.
* **Expected Result:** Every active asset registers touch accurately within reasonable proximity boundaries; multi-taps resolve without queuing conflicting UI requests or causing race condition lockups.
* **Priority:** Medium

---

## 6. Test Suite 4: Performance (PERF)

### TC-PERF-01: Interface Rendering Stability & Scroll Metrics
* **Description:** Monitor scrolling frame rates and check for sudden UI flickering on long text walls.
* **Target Test Condition:** `TCOND-PERF-01`
* **Preconditions:** No performance-throttling battery-saver profiles are running on the S21 FE device.
* **Test Data Category:** Long-form scrollable text/logging grid views; rapid downward and upward scroll sweeps.
* **Expected Result:** Scrolling runs smoothly with constant refresh frame rates; text remains clear without tearing, stuttering, or random reflow during motion.
* **Priority:** Medium

---

## 7. Test Suite 5: Accessibility (ACC)

### TC-ACC-01: Dynamic Font Scaling & Layout Integrity
* **Description:** Verify text rendering components do not collide or overflow when system-wide text size is maxed.
* **Target Test Condition:** `TCOND-ACC-01`
* **Preconditions:** System font size set to maximum scale (Android Settings → Display → Font size and style) before the app is relaunched.
* **Test Data Category:** Main dashboard, core caregiver notes sections, and action-confirmation button layouts at maximum font scale.
* **Expected Result:** All text auto-scales appropriately; words reflow cleanly into multi-line configurations without clipping boundaries, overlapping other items, or pushing interaction buttons off-screen.
* **Priority:** High

---

## 8. Test Suite 6: Interruption (INT)

### TC-INT-01: Note Preservation During Active Voice Call Interruption
* **Description:** Verify operational note data survives a voice-call interruption mid-entry.
* **Target Test Condition:** `TCOND-INT-01`
* **Preconditions:** App is running; an entry view is open with a half-completed sentence typed into a note input box.
* **Test Data Category:** Incoming voice call interruption lasting at least 15 seconds.
* **Expected Result:** The app retains its exact pre-interruption state; the typed draft sentence remains intact without clearing data or throwing memory management exceptions.
* **Priority:** High

### TC-INT-02: State Retention on Hardware System Interruptions
* **Description:** Verify current reading/input position survives low-battery pop-ups or screen locking.
* **Target Test Condition:** `TCOND-INT-02`
* **Preconditions:** App is active on a deep content or educational notes screen.
* **Test Data Category:** Hardware lock/unlock cycle (30-second lock); simulated low-battery warning overlay.
* **Expected Result:** The app recovers instantly from the sleep transition cycle, retaining exact scroll depth, active tab, and data view state without returning to the boot logo or home screen.
* **Priority:** High
