# LabFlow — Streamlining Laboratory Requests

## Task 1: Workflow Investigation and Improvement Proposal

**Project:** LabFlow  
**Assignment:** HKAiverse AI Recruitment — Round 2, Task 1  
**Institutional context:** ICFAI Foundation for Higher Education (IFHE), Hyderabad  
**Project type:** Workflow analysis and proposed process redesign  
**Status:** Prototype proposal; not an officially deployed institutional system

---

## 1. Executive Summary

LabFlow is a proposed workflow for managing laboratory-related requests, such as equipment assistance, access requests, and reporting technical issues.

The goal is to make requests easier to submit, track, review, and resolve by introducing a structured request form, clear status updates, accountability, approval boundaries, and exception handling.

The proposal focuses on reducing avoidable follow-ups, incomplete submissions, duplicate requests, and uncertainty about request ownership.

**Important:** LabFlow is an independent student project proposal. It is not an official IFHE system, and no production integration or deployment is claimed.

## 2. Problem Statement

Laboratory-related requests may involve several activities:

1. A student identifies a laboratory requirement or problem.
2. The student communicates the request to the relevant person.
3. The request is reviewed for completeness and authorization.
4. The responsible person takes action or requests additional information.
5. The outcome is communicated and the request is closed.

Potential inefficiencies include incomplete information, repeated communication, unclear ownership, duplicate requests, and limited visibility into progress.

These are the problems this proposal investigates. They must be validated against actual observations or authorized feedback before being described as confirmed problems at IFHE.

## 3. Project Objectives

- Create a consistent process for submitting laboratory requests.
- Capture the information needed to assess each request.
- Make request status and ownership visible.
- Define approval boundaries and escalation paths.
- Handle missing information, duplicates, unauthorized requests, and failed steps.
- Estimate whether the proposed process saves time after review and support effort.

## 4. Proposed Solution

LabFlow introduces a structured request-management workflow.

### Request information

Each request should contain:

- Unique request ID
- Request category
- Laboratory or facility concerned
- Description of the requirement or issue
- Date and time submitted
- Requester's institutional identity, collected only where authorized
- Priority and supporting details, if applicable
- Assigned responsible person
- Current status and resolution notes

Sensitive personal data should not be collected unless it is necessary and authorized.

### Workflow statuses

| Status | Meaning |
|---|---|
| Submitted | Request has been received |
| Needs Information | Required details are missing |
| Under Review | Request is being checked |
| Approved | Required approval has been granted |
| Rejected | Request was declined with a reason |
| In Progress | The responsible person is handling it |
| Resolved | The reported issue or request has been addressed |
| Closed | Completion has been confirmed |
| Escalated | The request requires higher-level attention |

Not every request needs every status. For example, an access request may require approval, while a routine technical issue may follow a different path.

### Proposed process

1. The requester submits a structured form.
2. The system checks required fields and creates a request ID.
3. A duplicate check identifies potentially repeated submissions.
4. The request is routed to an authorized reviewer or responsible person.
5. The reviewer approves, rejects, or requests more information.
6. Approved requests are assigned for action.
7. The responsible person records the outcome.
8. The requester is informed, and the request is closed after confirmation or according to the defined closure policy.

## 5. Roles and Responsibilities

| Role | Responsibility |
|---|---|
| Requester | Provides accurate details and confirms the outcome |
| Reviewer | Checks completeness, validity, and authorization |
| Lab in-charge or authorized staff | Approves requests within their authority and assigns work |
| Assigned technician or responsible person | Carries out the approved action and records the result |
| Escalation owner | Handles blocked, disputed, or overdue requests |

These roles are proposed and must be adapted to the institution's actual policies. LabFlow does not grant approval authority to anyone.

## 6. Exception Handling

| Scenario | Proposed response |
|---|---|
| Missing information | Set status to `Needs Information` and specify the missing fields |
| Duplicate request | Flag a possible duplicate and link it to the original for human review |
| Unauthorized request | Reject or hold the request according to policy; do not bypass approval |
| Failed processing step | Record the failure, retain the request details, and notify the responsible person |
| No response or prolonged delay | Escalate according to a defined time limit |
| Request rejected | Record the reason and communicate the decision |
| Conflicting requests | Refer the conflict to an authorized reviewer |

Duplicate detection should flag likely matches rather than automatically discard requests, because two similar requests may represent separate issues.

## 7. Test Plan

The proposed workflow is evaluated using five synthetic test cases. These are simulations, not real student requests or proof of institutional deployment.

| Test | Input | Expected result |
|---|---|---|
| Normal request | Complete and authorized request | Request ID created and request routed correctly |
| Missing information | Required field omitted | Submission is flagged or returned for completion |
| Duplicate request | Similar request submitted twice | Possible duplicate is flagged for review |
| Unauthorized request | Request requiring approval is submitted without authorization | Request is held or rejected according to policy |
| Failed step | Processing or notification step fails | Failure is logged, ownership is retained, and recovery or escalation is triggered |

**Test evidence:** Record the actual outcome of each simulation in `test-cases.csv`. Do not mark a test as passed until it has been performed and its result recorded.

## 8. Evidence and Assumptions

This project distinguishes observed facts from assumptions and estimates.

- **Observed facts:** Details directly confirmed through authorized observation or reliable documentation.
- **Assumptions:** Proposed process details that have not yet been verified.
- **Estimates:** Illustrative numbers used to assess potential benefits.
- **Synthetic tests:** Scenarios created to evaluate the proposed workflow without using real personal or institutional data.

The evidence log should include the date, activity, evidence or source, classification, and limitations. Do not include private student information, personal identifiers, credentials, or confidential institutional records.

See [`evidence-log.csv`](evidence-log.csv) for the evidence register.

## 9. Time-Saving Calculation

The potential benefit is estimated using the following formula:

**Net time saved per month**

= (Monthly requests × Baseline handling time)  
− (Monthly requests × Proposed handling time)  
− Additional monthly review and support effort

### Illustrative example only

| Measure | Illustrative value |
|---|---:|
| Requests per month | 40 |
| Baseline handling time per request | 12 minutes |
| Proposed handling time per request | 7 minutes |
| Additional review and support effort | 90 minutes/month |
| Baseline total effort | 480 minutes/month |
| Proposed total effort, including overhead | 370 minutes/month |
| Net time saved | 110 minutes/month |
| Estimated reduction | 22.9% |

Calculation:

- Baseline effort = 40 × 12 = 480 minutes
- Proposed effort before overhead = 40 × 7 = 280 minutes
- Proposed effort including overhead = 280 + 90 = 370 minutes
- Net saving = 480 − 370 = 110 minutes per month
- Percentage reduction = (110 ÷ 480) × 100 ≈ 22.9%

**These values are hypothetical, not measured IFHE data.** Replace them with measured baseline and pilot values if authorized data becomes available. Include the time spent on review, maintenance, support, and exception handling to avoid overstating the benefit.

## 10. Privacy, Security, and Approval Boundaries

- Use synthetic data for demonstrations and testing.
- Do not publish names, student IDs, marks, fees, credentials, private messages, or confidential laboratory records.
- Collect only information required to process a request.
- Restrict approval and administrative actions to authorized roles.
- Keep an auditable record of status changes and decisions in any future implementation.
- Do not claim that a request is approved merely because it was submitted.
- Do not connect to institutional systems without explicit authorization.

## 11. Limitations

- The workflow is a proposal, not a deployed institutional service.
- Institutional roles, policies, and actual request volumes require validation.
- The time-saving figures are illustrative until measured.
- Synthetic tests do not demonstrate production reliability or security.
- Integration with institutional accounts, notifications, or laboratory systems is outside the current scope.
- Human review remains necessary for authorization, ambiguous requests, and exceptional cases.

## 12. Future Improvements

If the workflow is validated and approved, future improvements could include:

- A simple request-submission interface
- Role-based access controls
- Searchable request history
- Notifications and overdue-request reminders
- Dashboard metrics for response and resolution times
- A controlled pilot with authorized users
- Before-and-after measurement of handling time and request completeness

## 13. Repository Contents

| File | Purpose |
|---|---|
| `README.md` | Project overview, workflow, assumptions, and results |
| `report.md` | Detailed workflow analysis and redesign |
| `evidence-log.csv` | Dated evidence, assumptions, and source register |
| `test-cases.csv` | Synthetic test scenarios and recorded outcomes |

Additional files may be included as the project develops. Update this table if the repository structure changes.

## 14. Personal Contribution and AI Use

**Personal contribution:** Update this section to describe the work you personally completed, such as selecting the workflow, researching the process, designing statuses and exception handling, preparing test cases, performing calculations, and validating the repository.

**AI assistance:** AI tools were used to help structure the report, brainstorm workflow states and exceptions, and draft test scenarios. All institutional claims, sources, calculations, and test outcomes must be checked by the author. AI-generated assumptions must not be presented as observed facts.

## 15. Conclusion

LabFlow proposes a structured, traceable approach to laboratory-related requests. Its key contribution is a clearly defined workflow with accountable ownership, approval boundaries, exception handling, and a transparent method for estimating time savings.

The next step is to validate the proposed process using authorized evidence and test the workflow before making claims about real institutional impact.
