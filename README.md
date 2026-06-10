# UnitisDefectMgt

This repository houses the formalized defect management records for Project Unitis. It serves as a central hub for identifying, documenting, tracking, and prioritizing software bugs discovered during active test delivery cycles

---

## 👥 Project Stakeholders & Alignment

Based on the course's testing cross-assignment matrices
* **Development Team Counterpart:** [Añora, Lelis, Araneta]
* **Testing Team (Author):** [Cabras,Sala,Oreiro]
* **Course Instructor:** Rodney Maniego Jr.

---

## 🗂 Repository Structure

Defects are categorized systematically inside feature-based or test-suite directories to preserve clean traceability and searchability

```text
CodeNameDefectMgt/
├── README.md                          # Repository documentation
└──  Candidate_Applications/            # Bugs relating to application submissions
       ├── BUG-001_broken_student_id_validation.md
       └── ...
```
---

## 🏷️ Title Formatting Standard

To ensure all bugs are scannable and easy to filter across teams, every bug report file name and issue tracking title must strictly follow the course convention:

### **The Standard Format:**
```text
[PROJECT_CODE] [VERSION] [PHASE] [FEATURE]: Concise bug description
```
### **Component Definitions:**
* **`[PROJECT_CODE]`**: The 2-letter or short identifier code for the software project (e.g., `AG` for Agora, `TF` for Task Force, `SS` for Silent System).
* **`[VERSION]`**: The specific release tag or build version string where the defect was observed (e.g., `v1.0`, `v1.1`, `v2.0`).
* **`[PHASE]`**: The current test pass strategy tier (e.g., `EarlyLook`, `FirstPass`, `SecondPass`, `Regression`).
* **`[FEATURE]`**: The isolated feature module name wrapped in square brackets (e.g., `[Candidate Applications]`, `[Settings]`, `[Auth]`).
* **`Concise bug description`**: A short, precise title summarizing the failure behavior.

---

## 📊 Risk Priority Calculation (RPN)

We prioritize defects objectively utilizing a numeric **Risk Priority Number (RPN)** scoring mechanism outlined in **"CSci 136 - 05.1 Test Engineering.pdf"**:

$$RPN = \text{Severity} \times \text{Likelihood} \times \text{Repeatability}$$

* **Severity (1–10)**: Measures direct customer or workflow disruption.
* **Likelihood (1–10)**: Measures how frequently users encounter the impacted feature.
* **Repeatability (1–10)**: Measures how reliably the bug can be reproduced on demand.

Defects yielding a higher cumulative RPN value receive engineering priority during the active development sprint.
