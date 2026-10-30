# Artifact 6: Lessons Learned and Executive Recommendations

Status: Proposed recommendations based on a fictional scenario; no production deployment or executed control validation is represented.

## Executive decision

Continue suspension of the affected financial-analysis workflow. The README describes a simulated case where approved inputs enabled inference of restricted acquisition information. Input authorization alone therefore does not justify disclosure of generated conclusions.

A limited pilot may be considered only after the evidence and independent approvals in [Artifact 5](05-control-validation-plan.md) are complete. No approval is recorded by this document.

## Lessons from the scenario

- Classification must follow derived information. An output can be more sensitive than any individual input.
- Roles and least privilege constrain retrieval and actions but do not eliminate inference risk from allowed data.
- Human review needs technical enforcement: quarantine, eligible reviewers, recipient checks and version-bound approval.
- Monitoring must support containment. Logs without a tested ability to halt retrieval and release are insufficient.
- A portfolio should distinguish a proposed design, an executed test, and a validated result.

## Prioritized recommendations

| Priority | Recommendation | Accountable role | Completion evidence |
| --- | --- | --- | --- |
| 1 | Preserve suspension; enumerate affected connectors, datasets, caches and pending outputs | Application owner with security lead | Scope inventory and demonstrated containment under T10 |
| 1 | Approve minimum financial views, derived-output classifications and eligible audiences | Financial data owner | Versioned source/output handling rules; T04–T05 evidence |
| 1 | Implement workload identity, user authorization and default-deny source/action scopes | IAM and application owners | Access matrix, configuration review and T01–T03 / T08 results |
| 1 | Enforce quarantine, independent review and bound release approvals | Application owner | T06 evidence and reviewer access review |
| 2 | Validate prompt injection defenses, outbound restrictions and audit failure handling | Security lead | T07 / T09 evidence with recorded failures and retests |
| 2 | Establish time-bounded exceptions, review cadence and configuration change gates | Governance lead | T11–T12 results and approved operating procedure |
| 3 | Run an independently reviewed, narrowly scoped synthetic pilot before considering broader use | Business risk owner | Completed validation record, residual-risk decision and signed restoration gate |

Role titles indicate proposed accountability; named owners and dates remain to be assigned.

## Measures for a future pilot

Report executed/passed/failed/blocked tests by ID, unauthorized disclosures observed, approval bypasses observed, revocation and containment timing, and evidence completeness. Define target timings before testing. Do not report invented results or treat zero observed failures in a small sample as proof of safety.

## Residual risks and limits

Finite tests may miss inference strategies and indirect leakage. Output inspection can miss context-dependent sensitivity or overblock useful answers. Reviewers can make mistakes. Data, permissions and model behavior can change. Address these through constrained sources and actions, evidence review, change-triggered retesting and a tested containment path. Risk acceptance must identify a named decision-maker, scope, evidence, expiry and review trigger.

## Review before adoption

These additions derive from the README. Reconcile them with the original decision-register workbook, classification workbook and architecture image before adoption; resolve discrepancies through an explicit governance decision. Populate executed evidence and named approvals separately. Current status remains design and planning.
