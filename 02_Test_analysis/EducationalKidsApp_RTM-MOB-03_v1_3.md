# Requirements Traceability Matrix (RTM)

**Identifier:** RTM-MOB-03  
**Version:** v1.3  
**Test Basis:** Functional Scope & Requirements (Educational Kids App Test Plan: TP-MOB-03)  
**Status:** Suspended (Entry Criteria Failure)  
**Date:** 2026-09-17  
**Author:** Annalie Prinsloo  

---

## 1. Document Control
### 1.1 Revision History
| Version | Date | Author | Description of Changes |
| :--- | :--- | :--- | :--- |
| 1.1 | 2026-05-25 | Annalie Prinsloo | Baseline RTM. |
| 1.2 | 2026-05-29 | Annalie Prinsloo | All requirement lines marked Blocked following suspension; `BLOCKER-01` reference added. |
| 1.3 | 2026-09-17 | Annalie Prinsloo | Restructured onto the standard RTM template; added the missing Test Condition layer (`TCOND-MOB-03`); identifiers migrated to the `*-MOB-03` convention; defect reference renamed `BLOCKER-01` → `BUG-MOB-03-01`; added Verification Metrics Summary. |

*Note: Execution has been formally suspended. All requirement lines are marked Blocked due to a critical environment delivery failure (broken app distribution link), preventing application installation and verification.*

---

## 2. Traceability Ledger
| Req ID | Requirement Category | Requirement Description | Test Condition ID | Test Case ID | Linked Risk ID | Execution Status | Related Defect ID(s) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **`REQ-NAV-01`** | Navigation | Smooth transition between main menus and application tabs. | `TCOND-NAV-01` | `TC-NAV-01` | `PR-01` | Blocked | **`BUG-MOB-03-01`** |
| **`REQ-NAV-02`** | Navigation | Deep section traversal and logical back-button handling. | `TCOND-NAV-02` | `TC-NAV-02` | `PR-01` | Blocked | **`BUG-MOB-03-01`** |
| **`REQ-CON-01`** | Content Delivery | High-accuracy textual and asset loading without failure or blank states. | `TCOND-CON-01` | `TC-CON-01` | `PR-01` | Blocked | **`BUG-MOB-03-01`** |
| **`REQ-CON-02`** | Content Delivery | Resource link redirection integrity. | `TCOND-CON-02` | `TC-CON-02` | `PR-01` | Blocked | **`BUG-MOB-03-01`** |
| **`REQ-UI-01`** | UI Interactions | Interactive input form fields and checkbox functional compliance. | `TCOND-UI-01` | `TC-UI-01` | `PR-02` | Blocked | **`BUG-MOB-03-01`** |
| **`REQ-UI-02`** | UI Interactions | Button, toggle, and clickable asset interaction handling. | `TCOND-UI-02` | `TC-UI-02` | `PR-01` | Blocked | **`BUG-MOB-03-01`** |
| **`REQ-PERF-01`** | Performance | Interface rendering stability and scroll smoothness. | `TCOND-PERF-01` | `TC-PERF-01` | `PR-01` | Blocked | **`BUG-MOB-03-01`** |
| **`REQ-ACC-01`** | Accessibility | Dynamic font scaling support for system-wide large text selections. | `TCOND-ACC-01` | `TC-ACC-01` | `PR-01` | Blocked | **`BUG-MOB-03-01`** |
| **`REQ-INT-01`** | Interruption | Operational note preservation during voice calls or hardware interruptions. | `TCOND-INT-01` | `TC-INT-01` | `PR-02` | Blocked | **`BUG-MOB-03-01`** |
| **`REQ-INT-02`** | Interruption | State retention during automated system-level UI interruptions. | `TCOND-INT-02` | `TC-INT-02` | `PR-02` | Blocked | **`BUG-MOB-03-01`** |

---

## 3. Verification Metrics Summary
* **Total requirements defined:** 10
* **Total requirements covered (traced to a test condition and test case):** 10 / 10 (100%)
* **Total requirements verified (executed):** 0 / 10 (0%) — execution blocked by environment layer
* **Total test conditions defined:** 10
* **Test conditions executed:** 0 / 10 (0%)
* **Test conditions blocked:** 10 / 10 (100%)
* **Master blocking reference:** `BUG-MOB-03-01` (app distribution link unreachable)
* **Unmapped requirements:** 0
