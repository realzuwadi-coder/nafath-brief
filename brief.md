Version: NAFATH-V2
Track: Cybersecurity

## Overview
The emergency responder 5G service depends on six IT fields working together to remain reliable under pressure. Software engineering ensures that requests behave predictably, especially when failed operations are retried. Artificial intelligence helps predict network congestion, allowing the operator to prepare resources before performance degrades. Mobile development enables responders to access essential information during connectivity loss and synchronize updates when service returns. Networking provides dedicated 5G network slices that can prioritize emergency communications. Cybersecurity prepares the operator to detect, contain, and recover from attacks while protecting critical systems. Data engineering organizes usage information so managers can report service demand by region and day. Together, these fields support informed decisions, continuity, and resilience. The cybersecurity incident response lifecycle is essential to maintaining this service during attacks.


## Software
Safe HTTP methods are GET, HEAD, OPTIONS, and TRACE; they are intended not to change server state. Idempotent methods include PUT and DELETE, as well as all safe methods: repeating the same request has the same intended effect as sending it once. POST is not generally idempotent. This distinction matters during automatic retries because repeating a POST may create duplicate actions unless the client and server use appropriate safeguards.

Resource: RFC 9110: HTTP Semantics - https://www.rfc-editor.org/rfc/rfc9110.html


## AI
Overfitting happens when a model learns noise or details specific to its training data instead of patterns that generalize to new situations. It may perform well on training data but poorly on unseen network traffic. Cross-validation divides data into multiple training and validation folds, then evaluates the model repeatedly. Comparing training and validation performance helps reveal overfitting and assess whether the model is likely to predict congestion reliably on new data.

Resource: Cross-validation: evaluating estimator performance - https://scikit-learn.org/stable/modules/cross_validation.html


## Mobile
An offline-first responder app should keep essential information available locally and allow responders to record updates without a network connection. It should clearly indicate connection status and queue changes securely with timestamps and unique identifiers. When connectivity returns, the app should synchronize pending changes, handle conflicting updates using defined rules, and avoid duplicate submissions. It should also show whether each update is pending, synchronized, or requires attention.

Resource: Build an offline-first app - https://developer.android.com/topic/architecture/data-layer/offline-first


## Networking
5G network slicing allows an operator to create multiple logical networks on shared physical infrastructure, each designed for different service requirements. A dedicated slice for emergency responders could be configured for stronger reliability, appropriate priority, and controlled access to network resources during congestion. However, slicing alone cannot guarantee uninterrupted service; the operator must also test capacity, coverage, isolation, and failure recovery.

Resource: 3GPP: Network Slicing - https://www.3gpp.org/technologies/network-slicing


## Cybersecurity
The incident response lifecycle includes preparation; detection and analysis; containment, eradication, and recovery; and post-incident lessons learned. If the 5G service is attacked, the team should first maintain response readiness, identify and assess the incident, limit its impact, remove the threat, and restore trusted service. Afterward, it should document the incident and improve controls and procedures to reduce the chance or impact of recurrence.

Resource: NIST SP 800-61 Rev. 3: Incident Response Recommendations and Considerations for Cybersecurity Risk Management - https://csrc.nist.gov/pubs/sp/800/61/r3/final


## Data
A star schema has a central fact table linked directly to dimension tables, such as date and region. A snowflake schema normalizes dimensions into additional related tables, reducing some redundancy but requiring more joins. For daily service-usage reports by region, a star schema is usually the better starting point because its simpler structure supports straightforward queries and reporting. The final design should still reflect data volume and reporting requirements.

Resource: Understand star schema and the importance for Power BI - https://learn.microsoft.com/en-us/power-bi/guidance/star-schema


## Misconception in My Track
A common misconception is that incident response begins only after an attack is detected, so preparation can be treated as a separate concern. In reality, effective cybersecurity requires ongoing readiness, coordination, and improvement before, during, and after an incident. For the 5G emergency service, the operator should prepare response procedures, assign responsibilities, and test recovery plans before an attack occurs. NIST explains this in Section 2, “Incident Response as Part of Cybersecurity Risk Management,” of SP 800-61 Rev. 3.

Supporting sentence: “Incident response is now considered a critical part of cybersecurity risk management that should be integrated across organizational operations.”


## Open Question
How can the operator test whether its dedicated emergency 5G slice remains reliable during a major outage affecting shared network infrastructure?

