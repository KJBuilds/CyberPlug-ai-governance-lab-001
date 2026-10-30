CyberPlug Portfolio Lab #001

Deploy AI Like an Enterprise: Governance, Risk & Security

Scenario: Redwood Financial Services
Focus: Enterprise AI Governance | Cybersecurity Risk Management | Data Protection | Security Architecture

Lab Status: Foundational artifacts published; proposed RBAC design, validation plan, and executive recommendations documented. Controls remain unimplemented/unvalidated; tests have not been run.

⸻

Project Overview

This portfolio lab explores the cybersecurity and governance challenges associated with introducing an artificial intelligence agent into a regulated financial-services environment.

Using a fictional organization, Redwood Financial Services, the lab demonstrates how cybersecurity professionals evaluate AI-related risks, establish governance requirements, define security boundaries, and document risk-based decisions.

The objective is to demonstrate practical cybersecurity analysis and decision-making through realistic business scenarios.

Business Scenario

Redwood Financial Services is evaluating an enterprise AI agent designed to improve productivity across business applications, including:

* SharePoint
* Power BI
* Salesforce
* Email
* Approved web resources

The proposed agent can retrieve information, analyze data, prepare summaries, and perform explicitly authorized low-risk activities.

However, connecting AI to enterprise systems introduces security and governance concerns involving data confidentiality, access permissions, autonomous actions, and sensitive information.

The organization must determine how to introduce AI capabilities while maintaining appropriate security controls and business oversight.

Critical Security Finding

During a simulated financial-analysis scenario, the AI agent inferred restricted acquisition information from otherwise authorized financial data.

This demonstrated an important governance principle:

Authorized access to individual data elements does not guarantee that AI-generated conclusions are appropriate for disclosure.

The affected workflow must remain suspended until the relevant data, inference-risk, output-handling, and approval controls are validated.

⸻

Learning Objectives

Participants completing this lab should be able to:

1. Evaluate enterprise AI deployment risks.
2. Document cybersecurity governance decisions.
3. Identify trust boundaries and access-control requirements.
4. Apply data classification principles to AI processing.
5. Evaluate sensitive-information inference risks.
6. Recommend appropriate preventive, detective, and corrective controls.
7. Communicate cybersecurity decisions to business stakeholders.

⸻

Portfolio Artifacts

Artifact #1: AI Risk & Governance Decision Register

Documents enterprise AI governance decisions, including:

* Limited-action AI deployment
* Identity and access management
* Data confidentiality
* Financial-data access exceptions
* AI inference-risk investigations
* Risk treatment and accountability

[View Governance Decision Register](CyberPlug_Lab001_AI_Risk_Governance_Decision_Register.xlsx)

Artifact #2: AI Architecture & Trust Boundaries

Illustrates the proposed enterprise AI architecture and its security requirements.

Key design considerations include:

* Dedicated AI agent identity
* Least-privilege permissions
* Approved financial-data views
* Risk-based approval controls
* Centralized audit logging
* Emergency containment
* Restoration authorization

[View Architecture Diagram](Redwood%20AI%20Architecture%20Trust%20Boundaries.png)

Artifact #3: Data Classification & AI Handling Matrix

Defines requirements for handling sensitive information during AI-assisted financial analysis.

The artifact addresses:

* Data classification
* Minimum necessary access
* Sensitive-data inference
* Sanitization and aggregation
* Derived-output classification
* Automated inspection and quarantine
* Risk acceptance and exception management
* Evidence retention

[View Data Classification Matrix](CyberPlug_Lab001_Artifact3_Data_Classification_AI_Handling_Matrix.xlsx)

⸻

Security & Governance Principles

This lab emphasizes five principles:

1. AI instructions are not security boundaries.
Security requirements must be enforced through technical controls.

2. Least privilege applies to AI identities.
AI agents should receive only the permissions necessary for approved business activities.

3. Data sensitivity extends to AI-generated outputs.
Information produced through inference may require a higher classification than its individual inputs.

4. Human accountability remains essential.
Sensitive, high-risk, or externally consequential actions require appropriate authorization.

5. Security decisions require evidence.
Control effectiveness should be demonstrated through testing, monitoring, and documented approvals.

⸻

Skills Demonstrated

Cybersecurity Governance

* Risk assessment
* Governance decision documentation
* Policy and control evaluation

Security Architecture

* Trust-boundary analysis
* Identity and access management
* Least-privilege design

AI Security

* AI deployment risk analysis
* Data inference-risk assessment
* AI output governance

Business Communication

* Risk-based recommendations
* Executive decision support
* Documentation of residual risk

⸻

Additional Design and Validation Artifacts

* [Artifact #4: Role-Based Access Control Design](docs/04-rbac-design.md)
* [Artifact #5: Control Validation and Testing Scenarios](docs/05-control-validation-plan.md)
* [Artifact #6: Lessons Learned and Executive Recommendations](docs/06-lessons-and-executive-recommendations.md)

These documents are proposed designs and a test plan, not implemented controls or executed validation results. All test cases are Not run. They derive from this README; reconciliation with the original workbooks and architecture image remains required before adoption.

Next steps: reconcile all artifacts, assign named owners, implement controls in an isolated synthetic lab, execute and independently review the test evidence, and record the required restoration decision. The affected financial-analysis workflow remains suspended.

⸻

About CyberPlug

CyberPlug is a cybersecurity workforce development initiative of BridgeForward.

Its mission is to expand access to practical cybersecurity learning, portfolio development, professional networks, and career opportunities.

CyberPlug emphasizes hands-on learning that helps aspiring cybersecurity professionals demonstrate how they analyze risk, document decisions, and communicate recommendations.

⸻

Disclaimer

Redwood Financial Services is a fictional organization created for educational purposes.

The scenarios, findings, and artifacts are simulations. They do not represent an actual security assessment, production AI deployment, or verified implementation of enterprise controls.

⸻

CyberPlug | A BridgeForward Workforce Development Initiative
