# Prototype · Juno

## Prototype link

[Open the Weekly Risk Brief](https://juno-weekly-risk-brief.amusedsage512.chatgpt.site)

Built with ChatGPT/Codex and Sites. The prototype is a static interactive demo using six fictional Slack, Jira, and Notion records, grouped into three risks. It does not run an AI model or access live systems.

## What it demonstrates

A RocketShip PM preparing for Monday's prioritization meeting can review a weekly risk brief, inspect the supporting evidence, and prepare an internal handoff draft in one flow.

**Specific user:** The PM assembling the weekly risk discussion before Monday's prioritization meeting.

**Surface:** One internal review screen with summary cards, a searchable risk list, priority filters, and a detail dialog with Overview, Evidence, and Task draft tabs.

**Work removed or shortened:** Reading scattered reports, matching linked tickets to their original messages, organizing risks, and preparing the context for a PM handoff. Actual time savings have not been measured.

**Primary testable assumption:** Without a walkthrough, a PM can identify the risk needing attention first and locate its supporting source within two minutes.

**Secondary assumption:** An editable task preview helps the PM prepare a useful handoff without mistaking it for an executed assignment. This is also unvalidated.

### Candidate exercise

| Candidate | Value type | Assessment | Choice |
| --- | --- | --- | --- |
| Weekly Risk Brief | Insight and augmentation | Boring killer: fits the PM's existing weekly review and reduces manual synthesis. | Selected: directly builds on the M1 skill. |
| Feedback to Spec Draft | Augmentation | Boring killer: reduces the effort of starting a spec from a feedback thread. | Kept for later; less direct alignment with the selected M1 task. |
| Ask Juno Anything | Insight | Fake good as framed: no specific workflow, surface, or success criterion. | Rejected in its current form. |

### Working flow

1. Review six signals grouped into three findings: an urgent reported export blockage, a dated authentication dependency, and an ambiguous dark mode request.
2. Filter by review category or search by finding text and source ID.
3. Open a finding and inspect reported impact, uncertainty, and a proposed next step.
4. Read the fictional source records in the Evidence tab.
5. Open Task draft, choose a proposed owner role and date, and add PM notes.
6. Preview or copy the internal handoff, or save it in local browser storage. Nothing is assigned, created in Jira, or sent.

### Build prompt

**Role:** Act as a product designer and prototyping engineer building Juno PM's internal Weekly Risk Brief for RocketShip.

**Task:** Build one review screen for a PM preparing Monday's prioritization meeting. Show three risks from six fictional Slack, Jira, and Notion records. Let the PM filter findings, inspect evidence, and prepare a handoff draft.

**Constraints:** Clearly label all data fictional. No live integrations or AI claims. Preserve source references, uncertainty, and NEEDS CLARIFICATION. No invented revenue, root cause, or numerical severity score. Owner and date selections are proposed draft values, not assignments or delivery commitments. No Jira writes, Slack messages, customer comms, or autonomous actions. Local storage only for drafts. Route contracts, legal, and regulator issues to the human PM.

**Format:** One responsive dashboard with summary cards, a searchable/filterable risk list, and a detail dialog with Overview, Evidence, and Task draft tabs. Include an editable owner role, date, notes, task preview, local save, and copy control. Keep a clear route from every finding to its source records.

### Alignment with M1

- Role: Juno is a risk watchdog and strategic partner; the human PM decides and executes.
- Task: The core remains signal synthesis and weekly risk review. Task preview is a proposed internal next step, not a full specification or autonomous delivery workflow.
- Constraints: Source citations, clarification for ambiguity, no fabricated business evidence, no sending, and no actual assignments.
- Format: The brief is a concise structured view, with detail and task preview progressively disclosed. It is a UI representation of the skill, not a demonstration that a live model follows its Markdown response instructions.

## Debrief

**Show and Swap status:** Not conducted. I did not attend the breakout session, so there is no peer feedback or timed usability result to report. This retrospective documents the build and iteration; it does not replace validation from another person.

- **What worked:** The prototype connects a risk summary, source records, and a handoff preview in one flow. Programmatic checks passed for category filtering, source search, evidence rendering, and local draft save/reset. These checks establish interface behavior, not user value or model quality.
- **What broke / felt like a toy:** The first version was a simple three-card brief. On comparing it with another class prototype, I wanted a more cohesive dashboard and useful detail views. The revised build adds summary cards, filtering, search, evidence tabs, and editable handoff drafts. All findings remain prewritten; relevance, urgency accuracy, time savings, and real integration behavior are unproven. Visual browser QA was not performed in the build environment.
- **What I'd change next pass:** Test whether a PM can identify the urgent finding and its evidence within two minutes, and whether they understand that saved drafts do not assign tasks. Use feedback to simplify the view. Later, test synthesis on authorized sample data and evaluate source grounding separately from UI usability.

### Inspiration

[Classmate's Juno Ticket Prioritizer](https://luxury-dolphin-d21501.netlify.app/) informed the summary-card, filtering, and tabbed task/evidence patterns. This implementation uses its own content and code, keeps the Weekly Risk Brief scope, and does not adopt the reference's scoring model or ARR figures.

### Proposed follow-up test, not conducted

Give a reviewer the link without a walkthrough. Ask: “Which risk would you investigate first, and what source supports that decision?” Record time, choice, source found, and confusion. Then ask them to prepare a draft handoff and explain what saving it does. The intended outcome is identification of the reported export blockage with supporting evidence within two minutes, plus recognition that no task is assigned. No pass result is claimed.

### Async debrief

The initial build showed that displaying risks is only part of the workflow. Connecting each finding to its evidence and an editable handoff makes the intended review flow more coherent. Whether this helps another PM remains untested because I missed Show and Swap. The next step is an independent usability check, not a claim of proven impact.
