# Exercise 1 — Diagnosis

## 1a. Flow analysis

### Facts and calculation basis

**FACT FROM SCENARIO**

- Average elapsed time: **34 days**.
- P90 elapsed time: **41 days**.
- Total working time: **770 minutes**, stated as approximately **12.8 hours**.
- Contractual target: **30 days**.
- Approximately **40%** of cases miss the target.

The primary calculation treats the 34 days as **calendar elapsed time**, as instructed.

### Primary flow-efficiency calculation

```text
Elapsed time = 34 calendar days × 24 hours/day × 60 minutes/hour
             = 48,960 calendar minutes

Working time = 770 minutes
             = 12.833 hours
             = 0.5347 calendar days

Flow efficiency = working time ÷ elapsed time
                = 770 minutes ÷ 48,960 minutes
                = 0.015727
                = 1.5727%
                ≈ 1.57%

Non-working/wait share = 100% − 1.5727%
                       ≈ 98.43%
```

**Result:** only about **1.57%** of average calendar elapsed time is active work; about **98.43%** is waiting, queueing, off-hours, handoffs, or otherwise unaccounted elapsed time.

### Reconciliation check

The listed waits sum to:

```text
0 + 1.5 + 5 + 2 + 11 + 3 + 7 + 2 + 1 = 32.5 days

32.5 listed wait days + (770 ÷ 1,440) working calendar days
= 32.5 + 0.5347
= 33.0347 calendar days
```

That is **0.9653 day** below the supplied 34-day average. This is not silently corrected. Possible explanations include rounding, off-hours embedded inconsistently in the table, unlisted handoff delay, or different source populations. It requires validation against case-level timestamps.

### Business-day ambiguity

If, contrary to the stated primary interpretation, “34 days” meant 34 eight-hour business days, the denominator would be `34 × 8 × 60 = 16,320` working-calendar minutes and the ratio would be **4.72%**. That is a sensitivity check only, not the primary answer. The contractual target and system timestamps must establish whether elapsed days are calendar days or business days.

### Three longest waits, ordered

| Rank | Wait | Duration | Work that follows |
|---:|---|---:|---|
| 1 | Reference outreach/follow-up | **11 calendar days** | 2 hours active verification work |
| 2 | Committee decision queue | **7 calendar days** | 15-minute decision |
| 3 | Primary source verification queue | **5 calendar days** | 3.5 hours active verification work |

### True system constraint

The working diagnosis is that Meridian's constraint is **not the speed of credentialing labor; it is the queue-and-decision operating model that serializes work around external reference responses and batched committee decisions without one consistently used workflow record**. The 11-day reference cycle is the largest current delay, while the 7-day queue for a 15-minute committee decision is the clearest internally controllable manifestation. This is a system constraint rather than a single slow employee or team; discovery must determine whether reference waiting, committee governance, or upstream incompleteness is the dominant causal constraint by case segment.

### CEO-ready explanation for Diane

A credentialing case receives only about 12.8 hours of active work but takes 34 calendar days to finish, so roughly 98% of the elapsed time is spent waiting rather than being processed. The largest delays are 11 days for references, seven days for a short committee decision, and five days before primary-source verification; speeding up individual tasks alone will not reliably bring Meridian below its 30-day commitment.

---

## 1b. Why the previous initiatives failed

The diagnosis below uses the course mechanisms—shared context, identity, and accountable execution—without claiming facts not present in the scenario.

### 1. Internal policy chatbot — deployed, about 4% weekly usage

**Mechanism of failure**

- The project appears to have optimized deployment rather than a specific workflow outcome. Four-percent weekly usage shows weak adoption, but the more important absence is a defined operational problem and an outcome measure tied to use.
- **Shared context:** a chat interface does not by itself resolve inconsistent taxonomy, unclear source authority, stale policy content, or fragmented work. If users cannot tell whether an answer is current and authoritative, they rationally return to known channels.
- **Identity:** the case provides no evidence that the chatbot acted under a bounded identity or needed to act at all. If it only answered questions, identity may not have been the primary failure; the key unanswered questions are who owned its corpus and who was accountable for an answer.
- **Accountable execution:** usage was measured, but no operational KPI was attributed to the chatbot. A usage statistic cannot show reduced handling time, fewer errors, or faster decisions.

**Diagnosis:** an optional destination was launched without being embedded in a high-value workflow, with no demonstrated trusted context or outcome accountability.

### 2. Copilot licenses for 140 engineers — perceived speed, unchanged release cadence

**Mechanism of failure**

- The engineers' report that they are faster can be true while organizational throughput remains unchanged.
- **Bottleneck argument:** individual coding speed is not system throughput. If code review, test environments, integration, release approvals, deployment windows, architecture coupling, or remediation of technical debt constrains releases, producing code faster merely moves work into the next queue. The scenario proves only that release cadence remained every two weeks; discovery must identify which downstream constraint is binding rather than assume one.
- **Shared context:** coding assistance cannot compensate for missing architecture decisions, unclear ownership, duplicated components, or hard-to-reconstruct system knowledge.
- **Identity:** personal copilots typically assist authenticated engineers; this is less an autonomous-actor identity problem than a boundary and attribution question for generated changes.
- **Accountable execution:** perceived speed was measured informally, but lead time, review time, defect escape, deployment frequency, and change failure were not connected to license usage.

**Where technical debt fits:** the VP Engineering's concern is rational. Technical debt can be the delivery-system constraint that absorbs any local coding gain. AI can also worsen it by increasing change volume, duplicating patterns, or generating code faster than teams can review and operate. The engagement should pair any AI-enabled work with clearer ownership, observability, consolidation, and reduction of fragile workflow glue—not ask Engineering to ignore the debt.

### 3. Claims document classification — 91% test accuracy, never shipped

**Mechanism of failure**

- A 91% aggregate test score does not define what happens to the remaining 9%, whether errors are concentrated in high-risk classes, or whether an individual classification can be reconstructed.
- **Shared context:** compliance lacked a case-level evidence trail showing the document, applicable rule/context, classification, confidence, and exception path.
- **Identity:** the automated classifier's authority was not defined. It was unclear, from the evidence given, what actor made the classification, what it was allowed to change, and who accepted residual risk.
- **Accountable execution:** misclassifications could not be traced, routed, reviewed, corrected, and tied to downstream impact. Compliance's refusal was therefore a rational control response, not resistance to innovation.

**Diagnosis:** the pilot optimized model accuracy but did not design the operating controls needed to handle errors safely.

### 4. Three teams independently built retrieval systems

**Mechanism of failure**

- **Shared context:** the teams lacked a common inventory, authoritative corpus, reusable retrieval service/pattern, and visibility into parallel work. Their systems may also encode different source sets and freshness rules.
- **Identity:** separate systems create separate access paths and potentially inconsistent permissions. Even if each team's access was valid, there was no evident common identity model or separation of read/write boundaries.
- **Accountable execution:** no owner could attribute duplicated spend, retrieval quality, source freshness, or business outcomes across the three implementations.

**Diagnosis:** this is an operating-model and ownership failure made visible through technology duplication. Consolidation should not mean blindly keeping one implementation; Meridian should first compare corpus authority, controls, usage, and maintainability.

### Cross-initiative pattern

Meridian repeatedly funded a tool or local capability before specifying the constrained workflow, the authoritative context, the actor's authority, the exception path, and the outcome measure. The result was adoption without impact, local speed without throughput, accuracy without deployability, and duplicated infrastructure without shared ownership.

---

## 1c. The three conditions

### Shared context

#### What is fragmented

- **SharePoint:** approximately 400,000 documents with inconsistent taxonomy. Search scope, authority, currency, duplication, and ownership are therefore uncertain.
- **Verification spreadsheet:** the verification team conducts much of the live work in a shared spreadsheet, creating an operational record outside the intended workflow platform.
- **ServiceNow:** workflow tracking exists but is inconsistently used, so status and timestamps are incomplete or reconstructed later.
- **Oracle and mainframe:** provider/claims data and eligibility reside in separate systems. The case does not establish stable cross-system identifiers or a unified view.
- **Tacit knowledge:** 11 verification specialists, averaging nine years of tenure, hold substantial decision and exception knowledge that is not fully represented in systems.
- **Three retrieval systems:** separate teams duplicated discovery and likely created competing representations of policy context.

#### Where knowledge is trapped

Knowledge is trapped in document libraries with weak taxonomy, spreadsheet cells and comments, inconsistent ServiceNow records, system-specific schemas, and the experienced verification team's judgment about exceptions, evidence quality, escalation, and sequencing.

#### Who pays the reconstruction cost

- Intake and verification staff reconstruct case completeness and history.
- Credentialing analysts reconstruct evidence for committee packets.
- Committee members spend scarce attention resolving missing or inconsistent context.
- Operations and contracting reconcile decisions across four enablement systems.
- Engineering recreates retrieval and integration capabilities.
- Compliance and Security reconstruct what automated systems did after the fact.
- Providers and Meridian ultimately pay through delay, rework, penalties, and possible provider loss.

### Identity

#### What exists today

**FACT FROM SCENARIO:** Meridian has an Azure tenancy that is moderately well governed, and Security is strict and competent.

**UNKNOWN TO VALIDATE:** the case does not establish the current Microsoft Entra ID tenant design, managed-identity availability for the proposed hosting model, service-principal inventory, Conditional Access policies, privileged access process, SharePoint permission hygiene, ServiceNow ACL model, Oracle grants, mainframe integration identity, or secrets-management pattern. It would be incorrect to claim Meridian presently has no identity model.

#### What automated actors would need

- A distinct Microsoft Entra application identity for each deployed agent or bounded service; no shared omnibus “AI” account.
- Azure Managed Identity where the compute service supports it; otherwise a narrowly scoped service principal with credentials/certificates protected in Azure Key Vault.
- Azure RBAC and resource-specific controls, plus SharePoint permissions, ServiceNow roles/ACLs, and Oracle read-only views or narrow grants.
- Separate identities and deployment boundaries for intake, evidence collection, outreach, packet preparation, and any enablement action; do not let a retrieval component inherit write authority.
- Explicit read/write boundaries, case/record scope where enforceable, least privilege, short-lived credentials, network restrictions/private endpoints where technically supported, and centralized logging.
- Human identity attached to approvals and overrides.
- A rapid revoke path: disable the Entra service principal/managed identity or role assignment, revoke ServiceNow/API access, disable integration credentials, and stop the workload.
- No autonomous mainframe or legally significant verification write is assumed until interface, control, and compliance requirements are validated.

### Accountable execution

#### What is measured today

The scenario provides average elapsed time (34 days), P90 (41 days), 770 minutes of working time, a 30-day contractual target, roughly 40% target misses, a 4% weekly chatbot usage rate, unchanged two-week release cadence, and 91% classifier test accuracy.

#### What can be attributed today

Only coarse associations are available: chatbot usage, Copilot access and reported individual speed, classifier test accuracy, and aggregate credentialing performance. None demonstrates a defensible chain from an AI action to an operational outcome.

#### What remains invisible

- Case-level queue entry/exit and reasons for waiting.
- Which source, rule, version, and evidence supported a recommendation.
- Whether a human accepted, modified, or rejected an automated recommendation.
- Exception frequency, rework, quality, and downstream harm by case type.
- Which actor changed which system and under what authority.
- Cost and usage by workflow/outcome rather than by generic license or project.
- Whether missing ServiceNow events reflect no action, spreadsheet work, or late data entry.

#### Required trace from action to outcome

A reconstructable chain should link:

```text
case/request
→ authenticated human or agent actor
→ timestamped workflow state
→ retrieved source IDs, versions, and citations
→ model/tool version and execution metadata
→ recommendation plus confidence/exception flags
→ human approval, edit, rejection, or escalation
→ system write and before/after state
→ final credentialing decision
→ elapsed time, SLA result, rework, and quality outcome
```

The workflow record should be the correlation spine. Detailed technical logs can remain in Azure logging/monitoring, while the durable business decision record, evidence references, approvals, and resulting state are linked from the ServiceNow case.

### Severity ranking

1. **Accountable execution — most severe.** Meridian has spent about $3.4M without an identifiable operational KPI improvement, and the classifier could not ship because error handling was not reconstructable. This condition directly blocks value claims and safe deployment.
2. **Shared context — second.** Fragmented records and tacit knowledge create daily reconstruction cost, duplicate retrieval systems, inconsistent handoffs, and unreliable automation inputs. It is likely a major cause of delay and rework.
3. **Identity — third, but still release-gating.** Security has already rejected a project over data residency, and any agent touching provider data requires bounded identity and permissions. It ranks third because the case shows moderate Azure governance and does not prove identity is currently broken; discovery may raise its severity quickly.

This ranking is a prioritization, not a sequence in which identity can be postponed. Identity and residency controls are prerequisites for even the first production shipment.

---

## 1d. Uncomfortable finding

### Major non-technology problem

Meridian does not appear to have one enforced, end-to-end credentialing operating model. Work is split between a shared spreadsheet and inconsistently used ServiceNow, committee decisions are batched behind a seven-day average wait for 15 minutes of work, ownership across intake/verification/committee/contracting/operations is fragmented, and critical rules live in the heads of 11 long-tenured specialists. The technology symptoms—missing traceability, duplicated retrieval, manual packet reconstruction, and poor measurement—are downstream of unclear process ownership, decision rights, adherence, and incentives.

This is **not** a finding that the verification team is the problem. Their spreadsheet and tacit practices may be rational adaptations to a workflow system that does not fit the real work. Imposing more data entry or automating around them would likely increase hidden work and resistance.

### What Charles should say

> “The largest obstacle is not that Meridian lacks another AI tool. Credentialing is being run through two operating records—the spreadsheet people need to get the work done and ServiceNow, which is not consistently the real source of status. At the same time, cases queue for committee cadence and key exception rules live with experienced specialists. We should treat those specialists as the designers of the future workflow, establish one accountable process owner and one minimum case record, and change the decision cadence where governance permits. Otherwise, automation will make the existing fragmentation move faster without improving the 34-day outcome.”

### Who should hear it

Say it first to **Diane as executive sponsor**, privately and directly. Then bring the same evidence—not a softened alternative—to a joint working session with the credentialing process owner/leader, verification-team representatives, committee leadership, Compliance, the VP Engineering, Security, ServiceNow ownership, and Operations. Committee representatives must be present because Diane cannot unilaterally change physicians' participation or regulatory governance.

### How to say it without blame

- Start with the time data and dual-record observation, not judgments about people.
- Describe the spreadsheet as a signal that the formal workflow does not serve the work, not as noncompliance by default.
- Ask the 11 specialists to map exceptions, workarounds, and evidence thresholds; credit them as domain experts.
- Separate mandatory regulatory gates from inherited habit.
- Make leadership own decision rights, committee service expectations, workflow adherence, and trade-offs.
- Require redesigned fields/events to replace existing work rather than add documentation burden.

---

## Assumptions and decisions preserved

### Assumptions used

1. The supplied 34 days is average **calendar** elapsed time.
2. The listed waits are expressed in calendar days unless Meridian's source data proves otherwise.
3. The 770 minutes is total active touch time per average case and does not double-count parallel work.
4. “Wait before” describes average queue/wait preceding the named step, but the labels and populations require validation.
5. The exercise's reference to a twice-monthly committee cadence is treated as a case condition to validate against calendars and timestamp data.

### Decisions made for the diagnosis

1. Do not call verifier capacity the constraint based only on 3.5 hours of primary-source work.
2. Treat the dominant constraint as wait-state and decision-cadence design, with reference outreach the largest delay and committee batching the most controllable internal delay.
3. Do not claim which engineering stage constrains the two-week release cadence without value-stream data.
4. Do not treat 91% accuracy as deployability.
5. Do not assume missing identity controls; mark them for discovery.

## Ambiguities to resolve before Exercise 2

1. **SLA clock:** Is the 30-day contractual target measured in calendar days or business days? What starts and stops the clock, and do provider-caused delays pause it?
2. **Timeline reconciliation:** Why do listed waits plus active work total 33.03 days rather than 34? Are there unlisted handoffs, weekends, rework, or rounding?
3. **Wait semantics:** Are the wait figures mutually exclusive sequential averages, or do some overlap? What exactly occurs during the 11 reference days?
4. **Committee governance:** Is twice-monthly cadence fixed by bylaws/regulation or convention? Which case classes legally require synchronous committee review? Who can approve asynchronous or exception-based paths?
5. **Case volume and segmentation:** Monthly volume, backlog, provider types, jurisdictions, risk tiers, clean-case percentage, and seasonality are absent. These are needed to estimate capacity and target impact.
6. **Quality baseline:** Current rework, false-complete rate, verification defect rate, exception rate, adverse findings, post-credentialing corrections, and audit findings are not provided. A guardrail cannot receive a credible numeric target yet.
7. **Reference baseline:** Channel mix, response rate, number of attempts, time-to-first-contact, provider/reference responsibilities, and acceptance requirements are unknown.
8. **System of record:** Is ServiceNow authorized and configured to become the enforceable workflow record? Who owns its schema, integrations, roles, and adoption?
9. **Azure entitlements:** Which Azure-native search, model, integration, monitoring, and private-network capabilities are already licensed/approved? “No new platform licenses” rules out assumptions.
10. **Data residency:** Which data classes, approved Azure regions, model endpoints, retention rules, and cross-border restrictions caused the previous rejection?
11. **Decision rights and ownership:** Who is the named end-to-end credentialing process owner, who owns committee policy, and who accepts compliance risk?
12. **November timing:** The exact CEO review date and the latest measurement window needed for a defensible result are not specified.

These questions should be resolved through timestamp analysis, policy review, and working sessions—not by inventing precision in Exercise 2.
