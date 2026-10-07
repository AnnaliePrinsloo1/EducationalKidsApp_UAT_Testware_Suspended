<div align="center">

### Tech Stack
![Markdown](https://img.shields.io/badge/markdown-%23000000.svg?style=for-the-badge&logo=markdown&logoColor=white)
![Android](https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)

### Testing Scope
![UAT](https://img.shields.io/badge/UAT-000080?style=for-the-badge&logo)
![Functional](https://img.shields.io/badge/Functional-000080?style=for-the-badge&logo)
![Usability](https://img.shields.io/badge/Usability-000080?style=for-the-badge&logo)
![Accessibility](https://img.shields.io/badge/Accessibility-000080?style=for-the-badge&logo)

### Test Environment
![Samsung](https://img.shields.io/badge/Samsung-%231428A0.svg?style=for-the-badge&logo=samsung&logoColor=white&logoSize=auto)
![Android](https://custom-icon-badges.demolab.com/badge/Android%2016-3DDC84?style=for-the-badge&logo=android&logoColor=white)

### Documentation reviewed with
![Claude](https://img.shields.io/badge/claude-%23D97757.svg?style=for-the-badge&logo=claude&logoColor=white)

</div>

# Educational Kids App (Beta) - End-to-End User Acceptance Test (UAT) Run

*Note on confidentiality: The app name and branding used in this repository have been fictionalized. Manual testing engagements are confidential by nature and cannot be publicly disclosed; this repository demonstrates the same process, documentation standards, and physical-device testing approach applied on real client work, using a fictional app so it can be shared openly as a portfolio piece.*

This application is a specialized Android app engineered to support parents and caregivers of children with neurodevelopmental needs. The app provides structured resources, tracking tools, and interactive content to assist in daily developmental care.

> [!WARNING]
> **Project Status Notice:** This UAT cycle was formally suspended before execution could begin, due to a broken build distribution link (`BUG-MOB-03-01`). This repository showcases the full UAT documentation set as designed — Test Plan, RTM, Test Conditions, Test Cases, Procedures, Execution Log, Defect Report, and Test Summary Report — along with how the cycle was formally suspended, escalated, and reported per ISTQB Suspension Criteria when a blocking environment defect prevented any test execution.

## Contents
- [Physical Device & Environment Matrix](#physical-device--environment-matrix)
- [Test Process Documentation Structure](#test-process-documentation-structure)
- [Validation Methodologies](#validation-methodologies)
- [Active Test Cycle Insights](#active-test-cycle-insights)
- [Related Portfolio Projects](#related-portfolio-projects)
- [About the QA Professional](#about-the-qa-professional)

---

## Physical Device & Environment Matrix
Testing is conducted strictly on a physical Android device.

* **Device:** Samsung Galaxy S21 FE 5G | Model: `SM-G990E/DS` | Android 16 (One UI 8.0)

---

## Test Process Documentation Structure
The testing artifact lifecycle is divided into chronological phases to guarantee full accountability and execution traceability:

```text
├── README.md
├── 01_Test_planning/
│   └── EducationalKidsApp_Test_Plan_TP-MOB-03_v1.3.md
├── 02_Test_analysis/
│   ├── EducationalKidsApp_RTM-MOB-03_v1.3.md
│   └── EducationalKidsApp_Test_Conditions_TCOND-MOB-03_v1.0.md
├── 03_Test_design/
│   └── EducationalKidsApp_Test_Cases_Suite_TC-MOB-03_v1.3.md
├── 04_Test_implementation/
│   └── EducationalKidsApp_Test_Procedures_TPROC-MOB-03_v1.3.md
├── 05_Test_execution/
│   ├── EducationalKidsApp_Execution_Log_EL-MOB-03_v1.3.md
│   └── EducationalKidsApp_Defect_Report_BUG-MOB-03-01.md
└── 06_Test_completion/
    └── EducationalKidsApp_Test_Report_TSR-MOB-03_v1.3.md
```

**Note:** `TCOND-MOB-03` (Test Conditions) is a new addition to this project's documentation — the original set linked requirements directly to test cases with no Test Analysis artifact in between, consistent with a gap also found and fixed in the MemoMatch portfolio piece. No Test Charters document exists for this project: exploratory testing is an execution-phase activity, and this cycle never reached execution.

---

## Validation Methodologies
* **Equivalence Partitioning & BVA:** Applied to screen boundaries, touch target distributions, and standard multi-field data forms across the interface.
* **State Transition Testing:** Validation of user pathways from cold launch, through active content navigation, background idle states, and application shutdown sequences.
* **Usability & Accessibility Testing:** Confirming text rendering layouts do not collide or overflow when system-wide large fonts are active, and validating that button layouts remain accessible to non-technical demographics.
* **Interruption Testing:** Simulating background incoming voice calls, system notification pop-ups, fast network switching, device power loss threats, and automated screen locking during active use.

*All of the above are designed into the test suite and ready to execute — see `TC-MOB-03` and `TPROC-MOB-03` — but have not yet been exercised due to the environment blocker described below.*

---

## Active Test Cycle Insights
* **Total Requirements Defined (RTM):** 10
* **Total Test Cases Planned:** 10
* **Total Test Cases Executed:** 0
* **Total Passed / Failed:** 0 / 0
* **Total Blocked:** 10 (100%)
* **Test Coverage (verified):** 0.0%
* **Deployment Release Status:** **Suspended — Reject/Hold.** See `TSR-MOB-03` for the full suspension rationale and recommendation.

### Open Defects
| Defect ID | Description | Severity | Priority | Status |
| :--- | :--- | :--- | :--- | :--- |
| `BUG-MOB-03-01` | Google Play Beta build distribution link unreachable / returns 404 routing error, blocking 100% of planned testing | Critical | High | Open |

---

## Related Portfolio Projects
This is one of four UAT testware showcases built on the same ISTQB-aligned documentation template. Each targets a different platform, testing approach, and cycle outcome:

| Project | Platform | Approach | Cycle Outcome |
| :--- | :--- | :--- | :--- |
| [Corvex_Packaging_UAT_Testware_Hybrid](https://github.com/AnnaliePrinsloo1/Corvex_Packaging_UAT_Testware_Hybrid) | Web (e-commerce) | Hybrid — Selenium/pytest-bdd automation + manual UAT | Completed |
| [TrueString_Tuner_UAT_Testware](https://github.com/AnnaliePrinsloo1/TrueString_Tuner_UAT_Testware) | Android | Manual UAT | Completed |
| [MemoMatch_UAT_Testware](https://github.com/AnnaliePrinsloo1/MemoMatch_UAT_Testware) | Android | Manual UAT | Completed — Release Rejected (defects found) |
| **EducationalKidsApp_UAT_Testware_Suspended** *(this repo)* | Android | Manual UAT | **Suspended** — blocked before execution began |

This project is included deliberately alongside the three completed cycles. Most testing portfolios only show the straightforward case — plan, execute, report. This one demonstrates the other side of the ISTQB process: recognizing an Entry Criterion failure, formally invoking Suspension Criteria rather than letting the cycle drift, escalating on a defined timeline, and still producing a complete, fully-traced documentation set (10/10 requirements mapped through to test conditions and test cases) even though none of it could be executed.

---

## About the QA Professional
I am an **ISTQB® Certified Freelance Software Tester** specializing in end-to-end **User Acceptance Testing (UAT)** and digital quality assurance. I partner with businesses to validate and optimize high-impact digital products before market launch, ensuring seamless user experiences and functional reliability across multiple platforms.

### Core Areas of Expertise:
* **Mobile Application Testing:** Native Android app validation, physical device matrix testing, hardware-software interaction testing, and interruption handling.
* **E-Commerce Platforms:** End-to-end checkout flow validation, payment gateway integration testing, shopping cart state persistence, and localized user journey verification.
* **Web Application QA:** Cross-browser compatibility validation, responsive web design (RWD) testing, and functional regression testing.

### Let's Connect:
* **LinkedIn:** [Annalie Prinsloo](https://www.linkedin.com/in/annalieprinsloo001/)
* **Professional Email:** <annalieprinsloo1@gmail.com>
* **ISTQB Verification ID:** [ZA010123GK0981040](https://scr.istqb.org/?name=Annalie+Prinsloo&number=ZA010123GK0981040&orderBy=relevancy&orderDirection=&dateStart=&dateEnd=&expiryStart=&expiryEnd=&certificationBody=&examProvider=&certificationLevel=&country=)
* **Availability:** Open to contract, freelance QA opportunities.
