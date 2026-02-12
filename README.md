# Feature Server Test Matrix v1

QA project focused on **feature/service testing** for ArcGIS-style workflows, with a practical emphasis on:
- query behavior
- edit operations (add/update/delete)
- permissions and access control
- validation and error handling
- regression comparison between baseline and upcoming update cycle

---

## Project Objective

Build a structured, recruiter-visible QA artifact that demonstrates:
1. test design quality,
2. reproducible execution logic,
3. clear defect-oriented thinking.

This repository is part of my portfolio for Product Test / QA roles in the ArcGIS ecosystem.

---

## Current Status

**Phase:** v1 foundation  
**Execution state:** baseline matrix prepared; execution ongoing in small batches  
**Last updated:** 2026-02-12

---

## Scope Strategy

Because full update scope is not always known in advance, this project uses a two-layer approach:

### Layer A — Core Regression (always applicable)
- feature queries
- edit flows
- sharing/permissions
- schema/field validation
- basic response consistency

### Layer B — Update-Specific Coverage
Added after official release/EAC notes are available for the target ArcGIS Online cycle.

---

## Repository Structure

- `README.md` — project overview and execution strategy
- `test-cases.csv` — master test matrix (test IDs, expected results, status)
- `test-summary.md` — run summary, findings, risks, next steps
- `eac-test-plan-feb-2026.md` *(optional/when used)* — EAC-cycle plan
- `eac-test-log.md` *(optional/when used)* — day-by-day test log
- `evidence/` — screenshots and supporting artifacts

---

## Test Design Principles

- Clear preconditions before every test
- Reproducible steps
- Expected result written in verifiable terms
- Priority-based execution (High → Medium → Low)
- Regression comparison against baseline behavior
- Sanitized evidence only (no sensitive credentials or private org details)

---

## How to Read the Matrix (`test-cases.csv`)

Each row represents one test case:
- **TC_ID**: unique identifier (e.g., FS-001)
- **Area**: functional domain (Query / Edit / Auth / etc.)
- **Preconditions**: required state before execution
- **Steps**: reproducible action flow
- **Expected_Result**: pass criteria
- **Priority**: execution order guidance
- **Status**: Not Run / Pass / Fail / Blocked
- **Notes**: failure details, observations, links to evidence

---

## Execution Plan (Current)

1. Validate and refine top-priority core regression cases  
2. Execute first batch (High priority)  
3. Record pass/fail + notes in matrix  
4. Add evidence files for notable outcomes  
5. Summarize findings in `test-summary.md`  
6. Extend with update-specific tests once scope details are published

---

## Definition of Done (v1)

This project reaches **v1 complete** when:
- at least 25 core test cases are documented,
- at least 10 high-priority cases are executed,
- summary report is updated with findings and risks,
- evidence folder contains supporting artifacts for key outcomes.

---

## Notes on Confidentiality

This repository contains only sanitized, portfolio-safe QA artifacts.  
No private credentials, invitation links, or internal-only environment details are published.

---

## Author

Elena Butova
