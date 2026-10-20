# Prototype · Juno

## Prototype link

[Open the Weekly Risk Brief](https://juno-weekly-risk-brief.amusedsage512.chatgpt.site)

Built with ChatGPT/Codex and Sites. The prototype is a static interactive demo using 39 fictional Slack, Jira, and Notion records, grouped into 13 risks. It does not run an AI model or access live systems.

## What it demonstrates

A RocketShip PM preparing for Monday's prioritization meeting can review a weekly risk brief, inspect the supporting evidence, and prepare an internal handoff draft in one flow.

**Specific user:** The PM assembling the weekly risk discussion before Monday's prioritization meeting.

**Surface:** One internal review screen without a sidebar, with summary cards, a searchable risk list, priority filters, and a detail dialog with Overview, Evidence, and Task draft tabs.

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

1. Review six signals grouped into 13 findings: an urgent reported export blockage, a dated authentication dependency, and an ambiguous dark mode request.
2. Filter by review category or search by finding text and source ID.
3. Open a finding and inspect reported impact, uncertainty, and a proposed next step.
4. Read the fictional source records in the Evidence tab.
5. Open Task draft, choose a proposed owner role and date, and add PM notes.
6. Preview or copy the internal handoff, or save it in local browser storage. Nothing is assigned, created in Jira, or sent.

### Build prompt

**Role:** Act as a product designer and prototyping engineer building Juno PM's internal Weekly Risk Brief for RocketShip.

**Task:** Build one review screen for a PM preparing Monday's prioritization meeting. Show 13 risks from 39 fictional Slack, Jira, and Notion records. Let the PM filter findings, inspect evidence, and prepare a handoff draft.

**Constraints:** Clearly label all data fictional. No live integrations or AI claims. Preserve source references, uncertainty, and NEEDS CLARIFICATION. No invented revenue, root cause, or numerical severity score. Owner and date selections are proposed draft values, not assignments or delivery commitments. No Jira writes, Slack messages, customer comms, or autonomous actions. Local storage only for drafts. Route contracts, legal, and regulator issues to the human PM.

**Format:** One responsive dashboard with summary cards, a searchable/filterable risk list, and a detail dialog with Overview, Evidence, and Task draft tabs. Include an editable owner role, date, notes, task preview, local save, and copy control. Keep a clear route from every finding to its source records.

### Alignment with M1

- Role: Juno is a risk watchdog and strategic partner; the human PM decides and executes.
- Task: The core remains signal synthesis and weekly risk review. Task preview is a proposed internal next step, not a full specification or autonomous delivery workflow.
- Constraints: Source citations, clarification for ambiguity, no fabricated business evidence, no sending, and no actual assignments.
- Format: The M1 skill now supports structured Markdown or interactive dashboard review, without a fixed finding or word cap. The 13-item searchable list, progressively disclosed evidence, coverage, and local task drafts match that format. No live AI instruction-following has been validated.

## Debrief

**What worked:**
- The top of the page tells the story fast: 39 messy signals became 13 risks, and 4 need a look now.
- It’s upfront that it’s fake data, nothing gets sent, and the PM makes the call. That builds trust.
  
**What broke / felt like a toy:**
- It’s a scripted demo on made-up data, so we can’t tell if it would handle our real Slack and Jira.
- Nobody has tried it yet, so the two-minute claim is just a claim.
- The handoff stops at a draft in my browser. I’d still have to copy it over myself.
  
**What I’d change next pass:**
- Watch 3–5 PMs use it cold and time them.
- Run it on one real week of our actual messages, and add one paste-ready handoff for Jira or Slack.
