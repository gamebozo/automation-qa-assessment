# Automation & QA Developer Assessment

**Candidate:** Aakash Vishwakarma

This repository contains my submission for the Automation & QA Developer assessment.

## Task 1 – Manual QA Testing

Tested application: https://demo.realworld.show/

- Tested registration, login, article creation, and editing.
- Identified and documented five issues.
- Included reproduction steps, expected and actual results, severity, and suspected causes.
- Added Root Cause Analysis (RCA) for one issue.

**Deliverable:** `Task1/Task1_QA_Report_Aakash.pdf`

## Task 2 – n8n Automation Workflow

Created an n8n workflow that:

- Fetches JavaScript repositories using the GitHub Search API.
- Selects the top five repositories by star count.
- Fetches the README of the highest-ranked repository.
- Uses conditional logic to select an email notification path.
- Sends the digest through Gmail.
- Routes API errors to an email alert node.

The workflow was manually tested, including both conditional branches and the README API error path.

**Deliverables:** Workflow JSON, screenshots, and detailed documentation are available in `Task2/`.

## Tools & Technologies

- Manual QA Testing
- n8n
- GitHub REST API
- JavaScript
- Gmail Integration

---

**Submitted by:** Aakash Vishwakarma
