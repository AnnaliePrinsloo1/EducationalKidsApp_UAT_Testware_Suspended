# Test Analysis: Test Conditions

**Identifier:** TCOND-MOB-03  
**Version:** v1.0  
**Test Basis:** Functional Scope & Requirements (Educational Kids App Test Plan: TP-MOB-03)  
**Status:** Suspended (Entry Criteria Failure) — defined but not yet executed  
**Date:** 2026-09-17  
**Author:** Annalie Prinsloo  

---

## 1. Document Control
### 1.1 Revision History
| Version | Date | Author | Description of Changes |
| :--- | :--- | :--- | :--- |
| 1.0 | 2026-09-17 | Annalie Prinsloo | New document. The original documentation set had no Test Analysis artifact — the RTM linked requirements directly to test cases. This document derives 10 test conditions from the 10 requirements in `RTM-MOB-03`, restoring the standard ISTQB Test Analysis → Test Design → Test Implementation structure. None of these conditions have been executed; all remain blocked per `TP-MOB-03` §6.3. |

---

## 2. Purpose and Methodology
Test conditions in this document define exactly **what** must be verified during the UAT phase for the Educational Kids App (Beta, Build v1.1.4.a). These conditions are derived from the 10 in-scope requirements defined in the Test Plan (`TP-MOB-03` §3.2). Execution of all 10 conditions is currently blocked — see `RTM-MOB-03` and `EL-MOB-03` for status.

**Priority Matrix:**
* **High:** Core navigation, content integrity, data-input boundaries, and interruption-resilience conditions directly tied to the app's caregiver-safety risk profile.
* **Medium:** Secondary interaction polish and scroll/rendering performance.

## 3. Test Conditions Inventory
| Condition ID | Source Requirement | Test Condition (What to Test) | Technique Applied | Priority |
| :--- | :--- | :--- | :--- | :--- |
| **TCOND-NAV-01** | `REQ-NAV-01` | Verify structural view switching and lateral tab navigation responsiveness. | State Transition Testing | High |
| **TCOND-NAV-02** | `REQ-NAV-02` | Verify backward navigation paths from deep content screens without UI loop traps. | State Transition Testing | High |
| **TCOND-CON-01** | `REQ-CON-01` | Verify all educational resources, images, and notes populate completely upon tap. | Equivalence Partitioning | High |
| **TCOND-CON-02** | `REQ-CON-02` | Verify external web resource links launch safely without breaking app session. | State Transition Testing | Medium |
| **TCOND-UI-01** | `REQ-UI-01` | Verify data input entry boundaries within text boxes using multi-field forms. | Boundary Value Analysis | High |
| **TCOND-UI-02** | `REQ-UI-02` | Verify touch target distribution responsiveness across active screen boundaries. | Boundary Value Analysis | Medium |
| **TCOND-PERF-01** | `REQ-PERF-01` | Verify scrolling frame rates and check for sudden UI flickering on long text walls. | Usability / Exploratory | Medium |
| **TCOND-ACC-01** | `REQ-ACC-01` | Verify text rendering components do not collide or overflow when the system text size is maxed. | Accessibility / Checklist-Based | High |
| **TCOND-INT-01** | `REQ-INT-01` | Verify operational note data survives a voice-call interruption mid-entry. | Interruption / State Transition | High |
| **TCOND-INT-02** | `REQ-INT-02` | Verify current reading/input position survives low-battery pop-ups or screen locking. | Interruption / State Transition | High |
