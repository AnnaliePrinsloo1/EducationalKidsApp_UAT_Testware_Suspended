# User Acceptance Test Plan: Educational Kids App (Beta)

Identifier: TP-MOB-03  
Test Level: User Acceptance Testing (UAT) / Beta Phase  
Current Status: Suspended (Entry Criteria Failure)  
Version: v1.3  
Date: 2026-09-17  
Author: Annalie Prinsloo  

---

## 1. Document Control
### 1.1 Revision History
| Version | Date | Author | Description of Changes |
| :--- | :--- | :--- | :--- |
| 1.1 | 2026-05-25 | Annalie Prinsloo | Baseline UAT Beta Test Plan initialization. |
| 1.2 | 2026-05-29 | Annalie Prinsloo | Project suspended: documented critical failure of Entry Criterion 1 (build delivery). Added formal Suspension and Resumption Criteria. |
| 1.3 | 2026-09-17 | Annalie Prinsloo | Restructured onto the standard testware template (Test Objectives, Device Matrix, and Test Monitoring & Control sections added; renumbered to match `TP-MOB-01`/`TP-MOB-02`); identifiers migrated to the `*-MOB-03` convention; Risk IDs renamed `RISK-xx` → `PR-xx`; removed status emoji in favor of plain text, matching the rest of the portfolio. |

### 1.2 References
* Educational Kids App Beta Specifications (Build v1.1.4.a)
* ISTQB Foundation Level Syllabus (CTFL v4.0)

---

## 2. Test Objectives
- **Verify Core Functionality:** Confirm that sections, buttons, and content load correctly.
- **Assess Usability:** Identify confusing user flows or design elements for non-technical users.
- **Evaluate Performance:** Monitor system stability, smoothness, and device resource handling.
- **Identify Defects:** Uncover crashes, freezes, and unexpected behaviors on the target device.

---

## 3. Context & Scope
### 3.1 Context of Testing (System Under Test)
The System Under Test (SUT) is the **Educational Kids App (Beta, Build v1.1.4.a)** for Android, a specialized app engineered to support parents and caregivers of children with neurodevelopmental needs. The app provides structured resources, tracking tools, and interactive content to assist in daily developmental care. This UAT phase evaluates the app under real-world conditions to confirm usability, stability, and proper functionality.

### 3.2 Features to be Tested (In-Scope)
* **`REQ-NAV-01` to `REQ-NAV-02` (Section Navigation):** Transitioning smoothly between menus, application tabs, and structural views.
* **`REQ-CON-01` to `REQ-CON-02` (Content Delivery):** Verifying text accuracy, notes, resource links, and interactive assets load without failure.
* **`REQ-UI-01` to `REQ-UI-02` (UI Interactions):** Testing buttons, clickable links, toggles, form fields, and device-specific layouts.
* **`REQ-PERF-01` (Real-World Performance):** Assessing frame rates, scrolling smoothness, and responsiveness during organic use.
* **`REQ-ACC-01` (Accessibility):** Dynamic font scaling support for system-wide large text selections.
* **`REQ-INT-01` to `REQ-INT-02` (Interruption Resilience):** Operational note and state preservation during voice calls and hardware-level interruptions.

### 3.3 Features Not to be Tested (Out-of-Scope)
* **Back-End Architecture:** Server architecture testing or database endpoint stress testing.
* **Source Code Validation:** Code-level structural validation or static security scanning.
* **Automation:** Automated continuous integration testing or automated regression suites.
* **Unlisted Hardware:** Any device other than the Samsung Galaxy S21 FE 5G.

### 3.4 Assumptions, Constraints, and Dependencies
* **Assumptions:**
  * The Google Play Beta distribution link provided by development resolves to a working, installable build.
* **Constraints:**
  * Testing is restricted to a single physical device; no emulators or cloud test benches are used.
* **Dependencies:**
  * A verified, installable application package (`.apk`) or working distribution endpoint must be delivered by development before execution can begin.
  * Responsive developer and engineering escalation channels are required to resolve any environment-level blockers within the test window.

---

## 4. Physical Device & Environment Matrix
| Device Model | Operating System | Firmware / UI Version | Environment Type |
| :--- | :--- | :--- | :--- |
| Samsung Galaxy S21 FE 5G (Model: SM-G990E/DS, Exynos 2100) | Android 16 | Samsung One UI 8.0 | Local Physical Device |

*Note: Virtual emulators and cloud test benches are explicitly excluded from this cycle.*

---

## 5. Test Strategy & Approach
### 5.1 Test Levels and Test Types
* **Test Level:** User Acceptance Testing (UAT) / Beta Phase.
* **Test Types:**
  * **Functional Testing:** Validating navigation, content delivery, and UI interaction correctness.
  * **Non-Functional Testing:**
    * **Usability & Accessibility Testing:** Confirming text rendering does not collide or overflow under system-wide large fonts, and that button layouts remain accessible to non-technical demographics.
    * **Interruption Testing:** Simulating incoming voice calls, system notifications, fast network switching, power loss threats, and automated screen locking during active use.

### 5.2 Techniques for Test Design
* **Specification-Based Techniques:** Equivalence Partitioning (EP) and Boundary Value Analysis (BVA) applied to screen boundaries, touch target distributions, and multi-field data forms.
* **State Transition Testing:** Validating user pathways from cold launch, through active content navigation, background idle states, and shutdown sequences.

### 5.3 Test Automation Approach
* Completely manual execution. No automation framework is used for this cycle.

---

## 6. Entry, Exit & Suspension Criteria
### 6.1 Entry Criteria
1. **[FAILED]** The Educational Kids App UAT beta testing environment package (v1.1.4.a) is stabilized, signed, and compiled into an accessible, working distribution build link. *(Status on 2026-05-29: Failed — provided link is broken/unreachable.)*
2. Core usage instructions, target interface parameters, and scope guidelines are verified for beta distribution channels.
3. **[MET]** Accessible feedback mechanisms, bug reporting pathways, and beta community portals are live and monitored.

### 6.2 Exit Criteria (Acceptance Criteria)
1. 100% of the key user journey workflows (navigation sequences, core content load points, and interaction mechanics) are thoroughly executed.
2. All reported system failures, background crashes, and severe UI freezes are successfully triaged, categorized, and documented.
3. The specified chronological test delivery window closes on 2026-06-02.

### 6.3 Suspension and Resumption Criteria
* **Suspension Criteria:** Testing execution halts immediately if a critical Entry Criterion (Section 6.1) is violated and no viable workaround exists.
* **Suspension Triggered (2026-05-29):** Entry Criterion 6.1.1 was violated — the application download link fails to resolve, no build is installable on the physical Samsung S21 FE 5G, and development engineering channels were unresponsive to escalation. Testing execution was formally and immediately suspended.
* **Resumption Criteria:** Testing resumes once a functional, verified, installable application package (`.apk`) or updated distribution endpoint is delivered by development, and its accessibility is confirmed by the UAT test lead.

### 6.4 Test Monitoring & Control
#### 6.4.1 Metrics Collected
* Test case execution progress: % of planned test cases executed to date.
* Entry/Exit Criteria status: tracked against the thresholds in Sections 6.1–6.2.
* Defect metrics: open defect count by severity, logged against `BUG-MOB-03-01` onward.
* Requirements coverage: % of in-scope requirements (`REQ-NAV-01` to `REQ-INT-02`) with at least one executed test condition, tracked via the RTM (`RTM-MOB-03`).

#### 6.4.2 Reporting Cadence
* Progress is reviewed at each milestone defined in Section 7.4.
* The Execution Log (`EL-MOB-03`) is updated on each test session, including blocked sessions, providing a continuous record.

#### 6.4.3 Control Actions
* **Applied on 2026-05-29:** Upon Entry Criterion 6.1.1 failing, remaining execution was halted in full per Section 6.3, a blocking defect (`BUG-MOB-03-01`) was logged, and escalation was raised to the development and project management channels. No partial execution was attempted, since every planned test case depends on the application being installable.
* Any further deviation from the schedule in Section 7.4 is documented in the Test Report (`TSR-MOB-03`) along with the root cause.

---

## 7. Logistics, Resources & Schedule
### 7.1 Test Environment and Tools Requirements
* Target physical device (Samsung Galaxy S21 FE 5G) with stable Wi-Fi/cellular connectivity.
* Google Play Beta channel access for pulling the target build.

### 7.2 Roles, Responsibilities, and Staffing
* **UAT Project Lead & Execution Specialist:** Annalie Prinsloo
  * *Responsibilities:* Environment setup and verification, manual test execution, defect logging, escalation management, and delivery of the test report.

### 7.3 Work Breakdown and Estimates
| Task Item | Target Resource | Estimated Effort |
| :--- | :--- | :--- |
| Environment Setup & Build Verification | Annalie Prinsloo | 0.5 Hours |
| `REQ-NAV-01` to `REQ-NAV-02`: Navigation Testing | Annalie Prinsloo | 1.0 Hour |
| `REQ-CON-01` to `REQ-CON-02`: Content Delivery Testing | Annalie Prinsloo | 1.0 Hour |
| `REQ-UI-01` to `REQ-UI-02`: UI Interaction Testing | Annalie Prinsloo | 1.0 Hour |
| `REQ-PERF-01`: Performance Testing | Annalie Prinsloo | 0.5 Hours |
| `REQ-ACC-01`: Accessibility Testing | Annalie Prinsloo | 0.5 Hours |
| `REQ-INT-01` to `REQ-INT-02`: Interruption Resilience Testing | Annalie Prinsloo | 1.0 Hour |
| Defect Logging & Test Report | Annalie Prinsloo | 1.0 Hour |

### 7.4 Milestones and Schedule
* **Milestone 1:** Environment Setup & Build Verification — Planned 2026-05-29. **Status: Failed** — build installation blocked; see Section 6.3.
* **Milestone 2:** Full Test Case Execution Complete (10 Test Cases) — Planned by 2026-06-01. **Status: Not Started** — blocked pending resumption.
* **Milestone 3:** Test Report Issued & Signed Off — Planned 2026-06-02. **Status: Issued early (2026-05-29)** as a suspension/blocker report rather than a completed-cycle report, per Section 6.4.3.

---

## 8. Communication & Risk Management
### 8.1 Communication Protocols and Status Reporting
* Testing results, defect logs, and blocker escalations are captured in Markdown and delivered immediately upon discovery of a critical issue, rather than waiting for a scheduled milestone.

### 8.2 Product Risks (Quality Risks)
| Risk ID | Risk Description | Impact Level | Mitigation Action |
| :--- | :--- | :--- | :--- |
| **PR-01** | Unexpected application crashes, frozen screens, sudden UI flickering, or erratic text reflows occur during navigation, causing increased frustration or operational friction for caregivers managing high-stress situations. | High | Ensure navigation pathways fail gracefully with clear fallback text notices or simple alerts rather than abruptly closing the application. |
| **PR-02** | Minimizing the app, answering a phone call, or experiencing low-battery notifications clears unsaved notes, input configurations, or reading positions, causing data loss. | High | Explicitly verify application state retention across all form factors. Force background minimization during active note-taking scenarios and ensure session data remains fully intact upon resuming. |

### 8.3 Project Risks (Management Risks)
| Risk ID | Risk Description | Impact Level | Mitigation Action |
| :--- | :--- | :--- | :--- |
| **MR-01** | A broken or delayed build distribution link from development blocks the entire UAT cycle, as realized in this cycle (`BUG-MOB-03-01`). | High | Require development to internally verify distribution link accessibility before handoff to UAT; establish a defined escalation SLA for blocker acknowledgment (see `TSR-MOB-03` recommendations). |

---

## 9. Deliverables
* **Test Plan:** This document (TP-MOB-03 v1.3)
* **Requirements Traceability Matrix (RTM):** RTM-MOB-03
* **Test Conditions:** TCOND-MOB-03
* **Test Cases Suite:** TC-MOB-03
* **Test Procedures:** TPROC-MOB-03
* **Execution Log:** EL-MOB-03 (repurposed as a Blocked Activity Record for this cycle)
* **Defect Reports:** BUG-MOB-03-01
* **Test Report:** TSR-MOB-03
