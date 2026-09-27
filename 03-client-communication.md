# Exercise 3 — Client Communication

**Status:** Complete draft for Charles's review  
**Uses:** `01-diagnosis.md` and `02-engagement-design.md`

---

# 3a — Two-page proposal for Diane

**To:** Chief Executive Officer, Meridian Health Services  
**From:** Diane Okafor, Chief Operating Officer  
**Subject:** A 90-day plan to reduce provider credentialing delays

## What we found

Provider credentialing averages 34 calendar days against a contractual commitment of 30 days. About 40% of cases miss the commitment, and P90 is 41 days. These misses create penalties and increase the risk that providers join competing networks while they wait.

The amount of work is not the main problem. A case receives about 770 minutes, or 12.8 hours, of active work. That is only 1.57% of 34 calendar days. In ordinary terms, more than 98% of the elapsed time is waiting, queueing, crossing a team boundary, or sitting in time Meridian cannot yet explain reliably.

The largest visible waits are 11 days for references, seven days for a committee decision that averages 15 minutes, and five days before primary-source verification begins. Reference outreach is the largest observed delay. Committee cadence is the largest delay Meridian can directly influence, subject to physician governance and regulatory review.

Meridian also lacks one consistently used record of the work. Verification relies heavily on a shared spreadsheet, while ServiceNow is used inconsistently. Policy and evidence are spread across SharePoint, Oracle, the mainframe, and the experience of 11 verification specialists whose average tenure is nine years.

## Why previous AI initiatives did not change business outcomes

The prior projects delivered tools or local speed without changing the part of the system that limited the business result.

The policy chatbot had about 4% weekly usage and no demonstrated operating outcome. Engineering copilots may have helped individuals write code faster, but release cadence remained every two weeks. If review, testing, integration, deployment, ownership, or technical debt sets the pace, faster coding creates more work for the next queue. The VP Engineering's concern is therefore legitimate.

The claims classifier reached 91% test accuracy, but Compliance could not reconstruct what happened to misclassified documents or how errors would be reviewed and corrected. Three teams also built separate policy-retrieval systems without knowing about one another, duplicating cost and creating competing sources.

The common gap was a defined operational result, an authoritative source, clear authority and exception handling, and evidence connecting an automated action to the outcome.

## What we propose

Run a bounded 90-day engagement on one provider-credentialing slice, selected after reviewing volume and risk. The work will:

1. establish one minimum case record with a reliable clock, owner, next action, wait reason, evidence, exception, and decision history;
2. start eligible references and verification work earlier, with independent checks performed in parallel;
3. replace passive reference waiting with measured attempts, approved reminders, escalation thresholds, and human takeover; and
4. prepare cited committee packets continuously, then test a faster decision path only if committee leadership, Compliance, and applicable rules allow it.

We will not clean all 400,000 SharePoint files, replace the mainframe, rebuild ServiceNow, solve enterprise governance, eliminate technical debt, or automate credentialing decisions. We will use existing systems and a small document set containing only current credentialing rules, procedures, templates, and guidance.

Software may gather, normalize, compare, and flag primary-source evidence. A qualified person will resolve ambiguity and make any compliance-significant determination. Committee decisions, contract authority, and consequential enablement remain human responsibilities.

## What ships first

Within two weeks, the selected cohort will use a structured minimum case record and append-only event history. It will show when the case and each queue started, who owns the next action, why the case is waiting, when references were contacted, and when evidence and decisions arrived. It will calculate case age and the 30-day deadline automatically.

This first shipment is intentionally plain. It is reversible, has low regulatory consequence, and makes the actual delays observable. It also tests whether Meridian can use one minimum record instead of reconstructing status from ServiceNow, a spreadsheet, email, and memory.

## 90-day shape

**Days 1–14:** verify the baseline and contractual clock, select the cohort, deploy the minimum record, and map exceptions with verification specialists. Stop or narrow the pilot if the record creates duplicate work or cannot be enforced safely.

**Days 15–30:** curate the pilot's credentialing documents, test cited evidence preparation in review-only mode, establish the quality baseline, and approve reference templates, channels, and escalation rules.

**Days 31–60:** start references earlier, run eligible checks in parallel, use timed follow-up with human takeover, and assemble committee packets as evidence arrives. Stop any intervention that reduces quality or response rates.

**Days 61–90:** if governance permits, test a bounded faster committee path. Complete the outcome and quality review, audit replay, operating runbooks, ownership, and recommendation to scale, extend, retain only measurement, or stop.

## What it will take

The visible automation is the smaller part. The unglamorous 80% is agreeing on the case record, cleaning a small authoritative document set, defining exceptions, assigning owners, setting permissions, recording decisions, testing failure paths, and making the formal workflow easier than the spreadsheet workaround.

Verification specialists must help design and own the rules. Their role should move from repetitive searching, copying, chasing, and packet reconstruction toward exception resolution, quality review, coaching, and rule stewardship. Leadership must address the reasonable fear that documenting expertise precedes headcount reduction; training alone will not answer it.

Engineering must be able to reject fragile integrations and address the limited technical debt that blocks observability, security, or support. Security must approve processing location, retention, access, and audit controls before any model receives provider information. We will not leave behind another broad platform or unowned service.

## How success is measured

The primary measure is the percentage of eligible pilot cases completed within 30 days. The scenario implies that approximately 60% currently meet it. The proposed engagement target is at least 75% for applications received during Days 31–60. This is a proposed target, not a forecast or contractual promise; the baseline, clock definition, volume, and case mix must be validated first.

Average elapsed time and the 41-day P90 remain diagnostic measures. The quality guardrail is material verification defects per 100 completed cases. Meridian has no verified numeric baseline for that measure, so Compliance will establish it during discovery. Faster processing does not count as success if verification defects, rework, audit exceptions, or incorrectly approved cases rise beyond the agreed boundary.

We will not claim success by excluding difficult cases, adding undocumented clock pauses, changing the metric after seeing the outcome, or accepting lower quality.

## What we need from Diane, from whom, and by when

- **By Day 3:** name one credentialing process owner with authority across the participating functions. Confirm the pilot-selection group and allocate time from two or three verification specialists.
- **By Day 5:** ask the ServiceNow owner and VP Engineering to confirm whether the minimum record can be supported without a rebuild or new licence. Ask Security to name the data-residency approver and required evidence.
- **By Day 10:** have Compliance and the process owner approve the SLA clock, cohort rules, defect definition, human approval boundaries, and reference controls.
- **By Day 14:** convene committee leadership and physician representatives to decide which cadence or decision-path options are lawful and worth testing.
- **Throughout:** protect specialist time, resolve ownership conflicts, and allow a poor intervention to be paused before a replacement is known.

At Day 90, Meridian will have a measured operational result, a quality result, and an evidence-based decision to scale or stop. If the target is missed, we will still be able to tell the CEO where time was lost, which interventions failed, what Meridian should retain, and what should end.

---

# 3b — VP Engineering dialogue

## Exchange 1 — Start with the legitimate constraint

**Me:** I agree with your concern that AI can distract from technical debt. The Copilot result supports it: engineers may be faster at writing code, but Meridian still releases every two weeks. I do not want your team generating more change into a system whose review, integration, deployment, or ownership bottleneck we have not identified. For this engagement, the first deliverable is a reliable credentialing event trail and one minimum case record, not another model demo.

**VP Engineering:** That still sounds like another team arriving with an AI label and asking us to integrate SharePoint, ServiceNow, Oracle, and a mainframe. We have fragile interfaces already. Every “small pilot” leaves behind another service that my team has to own.

**Me:** Then we will make “no new orphaned service” a design constraint. We will use ServiceNow as the workflow spine only if your team confirms that it can enforce the minimum record with existing capabilities. We will not replace the mainframe, build a broad platform, or add autonomous writes across the four enablement systems. At the first gate, you can reject an integration that adds brittle glue without a named owner, runbook, revoke path, and retirement plan.

## Exchange 2 — Find the overlap with technical-debt work

**Me:** The work I need from Engineering overlaps with debt reduction: identify the authoritative event sources, define stable case identifiers, expose a narrow Oracle read-only view if required, remove duplicated retrieval paths, and make ownership visible. Those changes reduce manual reconstruction even if we never use a model on provider data.

**VP Engineering:** My concern is capacity. You are describing observability, access controls, document ownership, integrations, and workflow cleanup. Those are real projects. Calling them part of an AI engagement does not create engineers to do them.

**Me:** Agreed. I will not hide the capacity cost. We should limit Engineering's commitment to the pilot's critical path and make Diane choose what it displaces. The first two weeks need a ServiceNow owner, a security engineer, and one integration engineer for bounded design and review, not a platform team. If the only safe implementation requires a ServiceNow rebuild, a new enterprise search product, or months of mainframe work, I will recommend narrowing or stopping rather than consuming the roadmap under a pilot label.

## Exchange 3 — Define what is added and who owns it

**Me:** What we are adding beyond existing copilots is case-level accountability. For any assisted recommendation, Meridian should be able to recover the case, evidence versions, rule or model version, human approval, resulting write, and eventual SLA and quality outcome. That is how we avoid another 91%-accurate pilot that Compliance cannot release.

**VP Engineering:** And after Taller leaves, who maintains the document index, access roles, prompts, integration failures, and audit records? That maintenance is technical debt from day one. I also do not want teams manually writing decision records that decay after the launch team moves on.

**Me:** I do not want voluntary documentation as a control either. Decision capture will be part of the workflow: required structured fields at approval points, automatic events from existing state changes, and generated draft records that the accountable person approves as part of completing the task. Before production, the process owner must own the business rules and corpus, Engineering must accept only the components it can support, and Security must own access and audit requirements. If those owners, support time, and exit procedures are absent by the Day-60 gate, the system does not scale. AI would make an unowned architecture worse, so lack of ownership is a stop condition.

---

# 3c — Week-6 bad-news memo

**To:** Diane Okafor  
**Subject:** Reference outreach pilot is reducing response rates

Diane,

At week six, references receiving automated outreach are responding at a rate **20% lower than references receiving manual outreach**. This is extending the largest wait in the credentialing process and puts the pilot's 30-day outcome at risk. We have stopped expanding automated sends beyond the current test group; the manual path remains available.

Our current hypothesis is that recipients treat the automated sender or message format as less credible or less urgent. We do not yet know whether the cause is the sender identity, wording, channel, timing, or recipient mix, and we do not have a confirmed fix.

We are running a bounded comparison of approved sender identities, human-sent versions of the same template, and reminder timing. We will track delivery, response, complaint, and time-to-response rather than optimize only for send volume.

I need your support to keep expansion paused and to have credentialing leadership and the messaging owner approve the controlled tests within two business days. You will receive the next written update in five business days, including results and a recommendation to modify, retain only the tracking, or end the automation.

---

# 3d — The next productivity gain

Provider enablement is the next business opportunity: after credentialing and contracting, Meridian spends about **90 minutes of active work** and another **one-day wait** enabling each provider across four systems. A single authorized enablement package, synchronized system tasks, and reconciliation of completion states could reduce duplicate entry and prevent a provider from being active in only some systems. The measure should be time from countersignature to consistent four-system enablement, with mismatched or prematurely enabled records as the quality guardrail; more AI usage is not the objective.
