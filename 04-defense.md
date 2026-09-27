# Exercise 4 — The Defense

**Status:** Complete draft for Charles's review  
**Consistency basis:** `01-diagnosis.md`, `02-engagement-design.md`, and `03-client-communication.md`

These are spoken answers for a skeptical client meeting. They defend the design without turning hypotheses into facts or promising that technology will overcome unresolved governance.

---

# Diane Okafor, COO

## 1. “The last three vendors told me they would fix this. Why is this different?”

**Answer**

You should not believe us because our technology sounds better. Judge us by whether we change the credentialing result and whether we make failure visible early.

The previous work started with a tool: a chatbot, developer copilots, and a classifier. We are starting with the contractual outcome. Credentialing averages 34 days, about 40% miss the 30-day commitment, and only 12.8 hours are active work. That means faster task execution by itself cannot solve the problem. A 50% reduction in all active work would remove at most 6.42 hours and leave the process at about 33.73 days if the queues remain.

Our first shipment is not a model demonstration. In the first two weeks we put a minimum case record and event history into real use for one bounded cohort. It tells us when each queue begins, why a case is waiting, who owns the next action, what evidence was used, and when a decision occurs. That gives Meridian something useful even if every model-assisted feature is later switched off.

We are also defining failure in advance. The proposed target is at least 75% of the pilot cohort within 30 days, subject to validating the baseline and clock. We will not claim success if we change the denominator, add undocumented pauses, remove difficult cases, or allow material verification defects to worsen. Each intervention has a stop condition. If automated outreach lowers response rates, we pause it before we know the fix.

The difference is therefore not “trust this vendor.” It is a smaller claim, a predeclared measure, a quality guardrail, case-level evidence, and permission to stop what does not work.

**Source: FRAMEWORK**

This answer applies the course's outcome-first diagnosis, bottleneck argument, bounded engagement, shared context, identity, and accountable-execution principles. The numerical defense comes directly from Meridian's scenario and the approved Driveshaft calculation.

---

## 2. “You are proposing to change how the credentialing committee works. That committee has physicians on it who do not report to me. How do you expect me to make that happen?”

**Answer**

I do not expect you to order the physicians to change their process, and I would not present committee redesign as a decision already made. The seven-day queue is an observed delay; asynchronous voting, delegated approval, higher cadence, and exception-only review are hypotheses that require the committee's governance and regulatory approval.

I would ask you to sponsor a decision process, not dictate its outcome. By Day 14, we need the committee chair, participating physician representatives, Compliance, Legal if required, and the credentialing process owner in the room. We bring case-level evidence: how many cases wait for committee, how long they wait, which cases are routine versus exceptional, what information is missing at review, and how much physician time each option would require. The specialists and committee members then separate requirements imposed by law, contracts, bylaws, or quorum rules from inherited scheduling practice.

We would offer bounded choices. One may be a short additional session for complete standard cases. Another may be an asynchronous human decision with the same evidence and named accountability. Another may keep the full committee path but move pre-read and exception resolution earlier. No automated actor receives approval authority.

If the committee rejects every path change, we accept that constraint. We continue the reference, parallel-verification, packet-preparation, and measurement work, but we lower the redesign estimate from 5–10 days to the documented 3–6-day range without committee change. We do not quietly move the original success threshold after seeing the result; we report that governance limited the intervention and show the outcome achieved under that constraint.

What I need from you is access, sponsorship, and a deadline for a real decision. I do not need you to pretend that organizational authority you do not have is yours.

**Source: IMPROVISED / EXPERIENCE**

The need to change the system constraint comes from the framework. The coalition, choice architecture, physician-governance approach, and explicit response to a rejected change are stakeholder-management judgments drawn from engagement experience rather than a formula in the framework.

---

## 3. “What happens if this does not work? What do I tell my CEO in November?”

**Answer**

If fewer than 75% of the validated pilot cohort complete within 30 days, if the data is too incomplete to support the result, or if quality breaches the agreed guardrail, I will say the engagement did not establish the claimed outcome. I will not replace that conclusion with usage, model accuracy, or favorable anecdotes.

What you tell the CEO depends on the evidence:

> “We tested a bounded redesign against a predeclared contractual measure. It did not meet the target. We stopped the parts that underperformed, did not expand the risk, and retained the parts that improved control. We can now show where the 34 days went, which delays were controllable, what quality impact occurred, and what decision is required next.”

The engagement is designed so that failure does not leave Meridian empty-handed. Meridian retains a verified baseline, a minimum case record, queue-age and wait-reason data, a curated credentialing corpus, an exception taxonomy, documented human approval boundaries, and an audit path. Those assets are valuable only if their ongoing cost is justified; the Day-90 recommendation may be to retain only measurement and controls, not the automation.

We will also distinguish types of failure. If reference automation lowers response rates, we stop that intervention. If committee governance does not change, we report that limitation separately. If ServiceNow cannot become the operational spine without a rebuild, we do not create a permanent fourth workflow system. If Security cannot approve a resident model path under existing entitlements, model access to provider data remains off while deterministic workflow changes continue.

The November answer will contain the result, quality outcome, spend and operating cost, failed hypotheses, retained capability, and a recommendation to scale, modify, or stop. “We learned a lot” is not the headline.

**Source: FRAMEWORK**

This answer follows accountable execution, predeclared falsification, reversible delivery, and honest progress communication. It preserves the course distinction between activity and business outcome.

---

## 4. “Can I do a smaller version first?”

**Answer**

Yes. The smallest responsible version is the first two-week shipment: one bounded provider cohort, one minimum case record, an event history, automatic SLA timing, reference-attempt instrumentation, and no model access to provider data. It uses real work, but it does not make credentialing decisions or send unreviewed messages. You can stop it without changing the mainframe, rebuilding ServiceNow, or buying a platform.

We can make the intervention smaller in two ways:

1. **Measurement-only start:** instrument the cohort and verify where the time goes before changing outreach or committee behavior.
2. **Human-approved workflow start:** add earlier references, timed tasks, and draft packet preparation, but keep every external message and compliance-significant output under human approval.

I would not make it smaller by removing the case record, quality guardrail, Security review, or cohort rules. A chatbot demo, ten hand-picked easy cases, or a packet summarizer with no outcome clock would be cheaper but would not answer whether Meridian can improve the 30-day commitment.

There is one trade-off: a two-week shipment can prove observability and workflow adoption, not the final SLA result. The Day-90 cohort is required to evaluate the primary outcome. If you want only the two-week version, I will describe it as a measurement and control pilot, not as evidence that credentialing performance improved.

**Source: FRAMEWORK**

This answer uses bounded scope, small-real-observable delivery, reversibility, and outcome integrity. It distinguishes a valid thin slice from a demo too small to test the business claim.

---

# VP Engineering

## 5. “We already have Copilot. What are you adding?”

**Answer**

Copilot helps an individual produce code. This engagement addresses a different constraint: a provider case spends about 98% of its 34-day elapsed time outside active work. Even eliminating every one of the 770 active minutes would leave roughly 33.47 days if nothing changed in queues and handoffs.

We are adding four things that Copilot does not provide:

- one minimum credentialing case record and reliable case identifier;
- observable queue entry, exit, wait reason, owner, and next action;
- approved, versioned evidence and decision context at each handoff; and
- a trace from an automated recommendation through human approval and system action to the SLA and quality outcome.

Some of that is ordinary engineering and process work. The workflow clock, event append, due-date calculation, approved task creation, and much of reference routing should be deterministic. They do not need a model. Where a model may help, its role is preparation: retrieve approved rules, normalize evidence, flag mismatch, or draft a cited packet. It cannot make the primary-source determination, vote, sign a contract, or enable a provider.

This should reduce technical debt in the pilot path by removing duplicate retrieval work, identifying authoritative sources, narrowing Oracle access to a read-only view, and refusing unsupported integrations. If the design requires a ServiceNow rebuild, a new platform, broad mainframe access, or another unowned service, we narrow or stop. I am not asking Copilot to solve architecture, and I am not calling more generated code an outcome.

**Source: FRAMEWORK**

This is the bottleneck argument from the course: individual task speed is not system throughput. The answer also applies the shared-context and accountable-execution conditions to distinguish this engagement from a coding assistant rollout.

---

## 6. “You want my team to write decision records. They will not do it. What is your plan for when they do not?”

**Answer**

Then the control cannot depend on them remembering to write a document after the work. We embed decision capture into the action they already have to complete.

For the pilot, a decision-producing state transition in ServiceNow requires a small set of structured fields: case ID, decision or disposition, governing rule version, evidence references, unresolved exception status, accountable human, and reason code. Existing workflow events supply timestamps, prior and resulting states, actor identity, and target action IDs automatically. The system generates a readable draft decision record from those fields and events. The approver reviews it as part of approval; there is no separate blank-page documentation task.

The gate is proportional to consequence:

- low-risk task creation and timer events log automatically;
- accepting or correcting prepared evidence requires an accept/edit/reject action and reason code;
- a compliance-significant verification determination cannot enter the “complete” state without the named human and required evidence references;
- a committee decision cannot release contracting work without the decision path, approver or voters, conditions, and packet version; and
- a clock pause, if the contract permits one, requires a human approver and supporting reason.

We keep the form short and generate as much as possible from existing events. The process owner reviews missing/low-quality case decisions weekly during the pilot. Repeated “other” reasons and manual bypasses become defects to fix in the workflow, not requests for another training session. Break-glass access is possible for operational continuity, but it records who used it, why, and what must be reconciled.

Engineering decisions use the same mechanism rather than a separate documentation campaign. A material change to an integration, permission boundary, rule source, or deployment creates a lightweight ADR-style draft from the existing change ticket and code-review/deployment metadata: problem, decision, alternatives considered, owner, affected interfaces, security consequence, rollback, and review date. The relevant service owner approves that record at the existing change or deployment gate. Engineering leadership reviews missing owners, stale review dates, and repeated exceptions; the control is the gate and generated record, not an appeal to write more documentation.

If the required fields are so burdensome that specialists return to the spreadsheet, we redesign or remove fields. If the platform cannot enforce the critical gates, we do not claim accountable execution and do not scale the automated decision path.

**Source: IMPROVISED / EXPERIENCE**

The framework requires accountable execution, but required fields, generated records, state-transition gates, reason codes, break-glass reconciliation, and workflow-owner review are implementation mechanisms drawn from operating-system and workflow experience. The answer deliberately avoids voluntary discipline as the control.

---

## 7. “Who maintains all this after you leave?”

**Answer**

No single “AI owner” should inherit it. Ownership follows the thing being maintained:

| Asset | Accountable owner after handoff |
|---|---|
| Credentialing outcome, minimum record, process states, and exception policy | Named end-to-end credentialing process owner |
| Credentialing rules, examples, and exception taxonomy | Designated verification rule stewards with Compliance approval |
| Canonical documents and review dates | Named business/content owner for each document in SharePoint |
| ServiceNow schema, ACLs, integration, and support runbook | Existing ServiceNow/platform owner accepted by VP Engineering |
| Automated workloads, deployment, monitoring, and incident runbook | Named Engineering service owner, only for components Engineering accepts |
| Workload identities, access review, data-residency conditions, logging requirements | Security, with system owners executing grants and revocation |
| Quality sampling and material-defect reporting | Credentialing QA/Compliance owner |
| Outcome and cost reporting | Process owner with Finance/data support as Meridian assigns |

We establish those names before scale, not in the final week. The Day-60 gate requires an owner, support capacity, service boundary, dependency inventory, runbook, alert path, access-review schedule, rollback procedure, data-retention rule, and retirement procedure for every production component.

The system must also be maintainable without Taller-specific products. No Echo, no Chiron, no new platform licence, and no proprietary operating console are part of the design. Canonical content stays in SharePoint; the workflow spine is ServiceNow only if Meridian can enforce it; identities remain in Entra and target-system controls; derived indexes can be rebuilt from approved source documents.

If Engineering will not accept a component, that is not a handoff problem to solve with documentation. We remove it, replace it with an already supported capability, or keep the human process. If the business will not fund rule stewardship and quality review, we retain measurement and stop the assisted recommendation path. Lack of a durable owner is a production stop condition.

**Source: FRAMEWORK**

The course's ownership and accountable-execution conditions drive the answer. The asset-by-asset RACI, Day-60 operational acceptance package, and retirement requirement are practical implementation details supporting that framework.

---

# Head of Security

## 8. “You want service accounts for AI agents with access to provider data. Walk me through the blast radius if one is compromised.”

**Answer**

First, I am not asking for one broad service account. I am asking for three separate workload identities with different permissions. A managed identity is preferred when the selected Azure hosting service supports it; otherwise we use a dedicated Entra service principal. Entra authenticates the workload. Azure RBAC, SharePoint permissions, ServiceNow ACLs, Oracle grants/views, messaging scopes, and application-level checks authorize it. Key Vault stores an unavoidable credential; it does not create authorization.

The blast radius differs by identity.

### Workflow and timeline orchestrator

A compromise could create or alter pilot tasks, timers, escalation fields, and workflow events. It could distort queue measurements or generate operational noise. It cannot read the broad SharePoint corpus or Oracle provider data, change verification evidence, approve a case, pause the SLA, sign a contract, enable a provider, delete history, or touch non-pilot records. ServiceNow field/action ACLs, a pilot-cohort predicate, append-only events, rate limits, and before/after logging bound the impact.

### Reference outreach actor

This has the most dangerous included write permission. A compromise could send Meridian-branded messages to approved pilot reference contacts, expose limited contact/provider context, lower response rates, or damage trust. It cannot invent a recipient, use free-form generated text, send non-allowlisted attachments, waive a reference, or change a credentialing decision. The sender, recipients, pilot case IDs, templates, channels, and send rate are constrained. A global “manual outreach only” flag disables sends and pending reminders immediately.

### Evidence and packet preparation actor

This has the largest confidentiality exposure. A compromise could read the controlled credentialing corpus and the permitted provider evidence for the pilot scope, call allowlisted evidence sources, and corrupt draft evidence or a draft packet. It cannot write final verification fields, clear an exception, vote, sign, enable, alter canonical SharePoint documents, or access the mainframe.

The phrase “current case only” must be enforced, not asserted. If ServiceNow or an Oracle/API connector cannot grant a token limited to one case, a mediation layer must validate the case assignment and requested resource on every call. The effective worst-case blast radius is whatever the underlying identity can actually enumerate. If the narrowest enforceable Oracle view or API scope exposes the whole provider population rather than the pilot cohort, we do not connect that source in production. We do not describe a prompt instruction as access control.

### Containment and recovery

For any identity we can stop the workload, remove its Entra role assignment or disable the service principal, revoke ServiceNow OAuth access, remove SharePoint permission, revoke the Oracle grant, disable the messaging sender, revoke model-endpoint access, invalidate queued jobs, and rotate any exposed non-managed credential. We preserve logs and case history before rebuilding the identity.

Before production, I will give you an effective-entitlement test for each identity, not just an architecture diagram: enumerate what it can read, attempt prohibited writes, test cross-case access, test bulk export/rate limits, trigger the kill switch, and confirm that the denial and revocation events appear in the audit trail.

**Source: IMPROVISED / EXPERIENCE**

The course supplies identity separation and least privilege. The compromise paths, effective-entitlement warning, mediation requirement, negative permission testing, and revocation sequence are concrete security-engineering and threat-modeling judgments.

---

## 9. “Where does the data go? We refused a project over data residency.”

**Answer**

Until you approve the data flow, provider data does not go to a model. Azure tenancy by itself is not approval, and a service being available in Azure does not prove that Meridian owns the entitlement, that processing stays in the selected region, or that the provider retains nothing.

The proposed flows are:

1. **Timers, SLA calculations, workflow events, and routing:** deterministic processing using case IDs, timestamps, and states in the approved ServiceNow/Azure boundary. No model is required.
2. **Policy retrieval for humans:** a query and chunks from the controlled credentialing corpus. We design this path without provider PII. Canonical documents stay in SharePoint; retrieval and logs stay in the approved Meridian region and tenant boundary.
3. **Evidence extraction or normalization:** selected provider evidence and limited case context. This likely contains provider PII and regulated credentialing data. It is blocked until you approve the endpoint, resource region, network route, processor terms, retention, abuse-monitoring behavior, training policy, subprocessors, backups, diagnostic logging, and failover behavior.
4. **Committee packet preparation:** verified evidence, exceptions, citations, and rule context. This also contains provider data and follows the same blocked path until approved.
5. **Reference outreach:** approved deterministic template plus the minimum merge fields through Meridian's existing approved messaging path. The initial design does not send reference content to a language model.

Generic technical telemetry contains correlation IDs, component/model versions, source IDs, hashes, timings, errors, token/use counts, and cost. It does not contain full evidence documents, message bodies, or uncontrolled prompts. Sensitive evidence, recommendations, packets, and approvals remain in ServiceNow or another specifically approved record store under Meridian's retention policy.

Before production we need a signed data-flow inventory showing source, fields, classification, destination hostname/resource, region, encryption, network path, identity, retention, backup/failover region, log destination, subprocessor, and deletion behavior. We also need to confirm every proposed Azure entitlement. There is no silent cross-region fallback.

If the currently licensed model or logging path cannot satisfy residency and retention requirements, model access to provider data stays off. The pilot can still ship the minimum record, timing, queue instrumentation, deterministic reminders, curated corpus, and human workflow. Security refusal narrows the implementation; it does not create an exception to the control.

**Source: IMPROVISED / EXPERIENCE**

The framework makes identity and accountable execution release conditions. The field-level data-flow inventory, endpoint/failover questions, telemetry minimization, and “no compliant path, no model” decision are technical privacy and cloud-governance practice.

---

## 10. “How do I audit what an agent did six months from now?”

**Answer**

You start with the immutable credentialing case ID, not a model chat transcript. That ID resolves a chain across business and technical records:

```text
case
→ workflow event
→ evidence and exact source version
→ automated execution and recommendation
→ human decision
→ target-system action
→ resulting state
→ SLA and quality outcome
```

ServiceNow, if the Day-14 gate confirms it can be enforced, stores the case, workflow events, wait reasons, state changes, evidence references, recommendation record, human approval, and resulting business state. SharePoint or the authoritative evidence source preserves the exact document/evidence version or an immutable citation/snapshot permitted by records policy. Approved Azure logs store the execution ID, workload identity, deployed component, model/tool/rule version, prompt or template hash, source and passage IDs, connector calls, output hash/location, latency, retries, errors, token/use counts, and cost. The target system stores its action ID and before/after state.

The linking identifiers are explicit:

- `credentialing_case_id` for the business case;
- `workflow_event_id` for each state transition;
- `execution_id` for each automated run;
- `recommendation_id` for the durable output;
- `approval_id` for the named human decision;
- `target_action_id` for the message or system write; and
- a propagated `correlation_id` across ServiceNow, Azure logs, and connectors.

For a six-month reconstruction, the auditor can answer:

1. What triggered the run, and which workload identity executed it?
2. What was that identity permitted to do at the time?
3. Which evidence and policy versions were retrieved?
4. Which model, tool, rules, and templates produced the recommendation?
5. What output was shown, and did the human accept, edit, or reject it?
6. What action occurred in the target system, with what before/after state?
7. Did the case meet 30 days, reopen, fail QA, or produce a material defect?
8. What usage and cost were attributable to that case and workflow step?

Retention must exceed the six-month audit horizon, but I will not invent the exact period. Security, Compliance, Privacy, and Records Management must approve it and confirm that source versions, workflow records, technical logs, backups, and deletion schedules remain mutually resolvable. Log access and exports are themselves audited, and sensitive content is not copied into generic telemetry merely to make auditing easier.

Before launch and quarterly during the pilot, we select sample cases and replay the chain. If a source version, approval, action ID, or outcome cannot be resolved, that is a control defect. If ServiceNow cannot enforce the spine, we stop or narrow the automated path rather than claim that scattered logs equal accountability.

**Source: FRAMEWORK**

This is the accountable-execution chain applied end to end: request, context, recommendation, approval, action, state, and outcome. The specific identifiers, record locations, replay test, and retention controls implement that framework in Meridian's existing estate.

---

# Defense-induced design correction

Question 8 exposes one point that must be sharper than the earlier wording: “current case only” is not a control unless the target API, database grant, or mediation layer enforces it. The Security gate must measure each identity's **effective entitlement**. If an Oracle view, ServiceNow API role, retrieval index, or model connector can enumerate more than the pilot cohort, that larger set is the true blast radius. Production access is denied until Meridian either narrows the underlying entitlement, introduces an approved case-authorizing broker, or removes that data source from the automated path.

This correction does not change the three-actor design. It strengthens Gate 1 and the Security acceptance test without expanding scope or assuming a new platform licence.
