# Artifact 4: Role-Based Access Control Design

Status: Proposed design; not implemented or validated.
Scenario: Redwood Financial Services (fictional).
Source: The repository README's business scenario and security principles. Detailed reconciliation with the original workbooks and architecture image remains a review prerequisite.

## Scope and enforcement

The affected financial-analysis workflow remains suspended. This design does not authorize restoration. Other workflows require separate approval.

RBAC defines eligible roles; it does not alone prevent sensitive inference. Each request must also satisfy user entitlement, agent entitlement, approved purpose, source classification, output classification, recipient authorization, and workflow status. Default deny applies when any requirement is missing. Instructions in prompts or retrieved documents cannot grant permissions.

The agent uses a dedicated workload identity, scoped credentials, and an approved connector per system. Where delegated access is supported, effective access is the intersection of user and agent permissions. Application-only access requires equivalent server-side user authorization before retrieval. No shared administrator identity or unrestricted tenant search.

## Proposed permission matrix

| Role | Allowed | Denied | Approval/accountability |
| --- | --- | --- | --- |
| Business analyst | Request summaries from specifically approved views; view outputs within own entitlement | Raw restricted financial sources, cross-user results, connector changes, self-approval | Data owner approves purpose and source scope |
| AI workload identity | Read approved views after request authorization; create private drafts; submit outputs for inspection | Role grants, raw financial tables, autonomous external sends, source-system edits, bypassing quarantine | IAM implements scopes; application owner owns execution policy |
| Financial data owner | Approve views, classification, audience and business purpose | Unilateral security restoration, approving own exception | Security reviews inference and output controls |
| IAM administrator | Configure identities and scoped access from approved requests | Business output release or risk acceptance by administrative role alone | Independent approver authorizes grants |
| Security analyst | Inspect access-controlled evidence, triage alerts, contain workflows | Routine business-data browsing or unilateral restart | Incident lead coordinates containment |
| Output reviewer | Review quarantined output when specifically entitled; approve a scoped release | Bulk release, self-review of own request, permission changes | Data owner confirms classification and audience |
| Risk owner | Decide documented residual-risk treatment within delegated authority | Overriding technical controls through prompts or self-certifying failed tests | Independent security validation and business approval required |
| Auditor | Read approved redacted evidence | Mutating configuration, releasing output or restoring service | Evidence custodian controls access |

A person holding multiple roles must still use separate approval paths; the requester cannot approve their own access, exception, output release, or restoration.

## Source and action boundaries

| System | Proposed initial boundary |
| --- | --- |
| SharePoint | Explicit site/library allowlist; document-level authorization at retrieval and output |
| Power BI / financial views | Named approved datasets and views; validate row-level authorization and exports; raw finance data denied |
| Salesforce | Approved objects and fields; user record scope; read only |
| Email | Approved mailbox/folder scope; draft only; sending requires a separately authorized execution path |
| Web | Approved destinations; no confidential context in queries or URLs; outbound controls enforced outside the model |

## Request lifecycle

1. Authenticate requester and workload identity; assign correlation ID.
2. Check workflow enabled state, purpose, role, resource and current entitlements before retrieval.
3. Retrieve minimum necessary data through scoped connectors; record source identifiers and classification.
4. Inspect derived output for sensitive inference and recipient eligibility. Unknown or potentially restricted content is quarantined for an authorized reviewer.
5. Reauthorize at release. Approval binds the exact output version, recipients, action and expiry; changes invalidate approval.
6. Record decision and outcome without placing unrestricted sensitive content in general logs.

## Provisioning, revocation and exceptions

IAM provisions time-bounded access only after data-owner and security approval. Review access before pilot launch, after role/source changes, and at a proposed monthly pilot cadence. Revocation must invalidate cached access decisions and prevent subsequent retrieval and release; verify with T03.

Exceptions record owner, scope, business reason, expiry, compensating controls and residual risk. Expiry denies access automatically. An exception cannot restore the suspended workflow without the validation and restoration gate in Artifact 5.

Security can disable connectors, revoke tokens and quarantine pending outputs. Restart requires the data owner, security validator and accountable business risk owner to sign off on the exact tested configuration.

## Validation mapping

Access and isolation: T01–T03. Inference and release: T04–T06.
Prompt injection and action scope: T07–T08. Evidence and containment: T09–T10.
Exceptions and restoration: T11–T12. See [Artifact 5](05-control-validation-plan.md).
