# Feature Server Test Matrix v1

QA practice project focused on feature service behavior and reliability in ArcGIS-style workflows.

## Goal
Build a structured test matrix for feature/service testing scenarios:
- query behavior
- edits (add/update/delete)
- permissions
- schema and field validation
- error handling
- basic performance checks

## Scope (v1)
- Manual test design and execution
- Service-level validation via defined test cases
- Defect-style findings documented in summary notes

## Status
**v1 in progress**  
Last updated: 2026-02-12

## Repository Contents
- `test-cases.csv` — core test matrix
- `test-summary.md` — execution summary and findings
- `evidence/` — screenshots or proof artifacts

## Test Environment (example)
- ArcGIS Online hosted feature layer (test dataset)
- Web map and layer query interface
- Browser: Chrome (latest)

## Key QA Focus Areas
1. Data retrieval correctness
2. Edit operation integrity
3. Permission enforcement
4. Input validation and error responses
5. Basic response consistency under repeated queries

## Planned Next Iteration (v2)
- Add negative API-style scenarios
- Expand edge cases for nulls, invalid geometry, long strings
- Add severity tagging and defect tracking format

## Author
Elena Butova
