# Module 3 · Class Preparation
Status: working hypotheses for class, not the final AI PRD or implemented architecture.

## What I am bringing

- [Module 2 artifact](../02-prototype/prototype.md)
- [Working prototype](https://juno-weekly-risk-brief.amusedsage512.chatgpt.site)
- [Current skill](../01-prompting/skill-file.md)

Juno's Weekly Risk Brief helps the RocketShip PM preparing Monday's prioritization meeting review risks, inspect supporting evidence, and prepare an internal handoff draft. The prototype has 13 prewritten findings from 39 fictional records. It proves the interface can be built; it does not prove AI quality, usability, or time savings. Peer testing has not been conducted.

Primary hypothesis: without a walkthrough, a PM can identify the risk needing attention first and locate its supporting evidence within two minutes.

## My starting position

Choose a **tool-using copilot** with bounded retrieval and draft-only outputs. A fixed, supplied packet can use a single-shot baseline first. A supervised agent is unnecessary for the initial weekly review because Juno does not need to execute work or pursue goals independently.

The PM owns the operating boundaries. Engineering implements and enforces them. The UI supports unrestricted browsing of available findings; this does not imply unlimited retrieval, model context, or cost per request.

## What Juno needs to see

These are proposed source locations to confirm against the RocketShip Company Context Documents in class, not claims that these resources exist.

| Source | Proposed scope | Required evidence |
| --- | --- | --- |
| Slack | Authorized #escalations or equivalent support/product escalation channels; selected week, full relevant threads and replies | Message/thread ID, channel, author and role if supplied, created/edited time and timezone, excerpt, customer if explicitly identified, permalink |
| Jira | RocketShip tickets updated in the selected week, unresolved relevant risks, and records linked from the Slack threads | Key, project, summary, description, status, reporter, assignee if supplied, update time, linked issues, workaround and impact |
| Notion | Approved product wiki, current incident/triage policy, weekly planning notes, dependency decisions | Document ID, path, author/editor if supplied, updated time, version, relevant text, source link |
| Optional customer transcripts | Only authorized excerpts explicitly linked to a finding | Interview/source ID, date, stated account and relevant excerpt; minimize personal information |

Default time window: the selected reporting week, with a dated snapshot. Older linked evidence and unresolved issues may be included and labeled as older context. A weekly report must not imply live incident monitoring.

Exclude DMs, restricted channels, unrelated customer data, raw credentials, contracts, legal files, and unverified ARR figures. Do not add CRM or billing access solely to make a dashboard look complete.

Required provenance is retained when supplied. Missing metadata remains unknown. Fictional source metadata is only for the labeled demo, never a substitute for real evidence.

## What Juno may do

| Action | Initial tier | Boundary |
| --- | --- | --- |
| Read/search/fetch | Auto within authorized scope | Enforce requester access before retrieval and display; read access can still expose sensitive data if scoped incorrectly. |
| Synthesize/group/recommend | Auto | Evidence-backed drafts; preserve conflicting reports and uncertainty. |
| Prepare a task draft | Auto | Proposed owner role, date, and notes are unapproved; user edits do not establish facts. |
| Save a personal local draft/copy | User initiated | Browser storage or clipboard only, clearly labeled. Not a Jira write. |
| Change Jira, publish Notion, assign work | Blocked in this version | Human PM performs these outside Juno. Confirmation alone does not enable a missing or prohibited tool. |
| Send Slack/email/customer comms | Blocked | No sends; external customer communications belong to the human PM. |
| Contracts, legal, regulator requests | Human handoff | Flag the need without legal interpretation or promised commitments. |

## Lab 1 · Rough six-surface sketch

| Surface | Initial specification |
| --- | --- |
| 01 Context | Authorized Slack, Jira, and Notion records for the selected week plus relevant linked/older unresolved evidence; approved triage policy and source provenance. Prefer scoped fetch and metadata filtering before broad semantic retrieval. Report exclusions and stale/unreachable sources. |
| 02 Tools | Proposed read verbs: search_slack, fetch_thread, search_jira, fetch_issue, search_notion, fetch_page. Proposed draft operations: build_brief, prepare_handoff. Backend schema/evidence validation is enforced independently of model choice. No send_message, update_issue, assign_issue, or publish_page. |
| 03 Loop | Starting hypothesis: at most 3 model calls per brief, including initial synthesis, one targeted clarification/retrieval pass, and one repair attempt. At most 8 read requests total, with explicit per-request record/size caps to be defined after reviewing course data. Stop at the call, cost, time, or context limit, whichever comes first. |
| 04 Memory | Session evidence expires after 24 hours as an initial design proposal; recheck authorization and freshness before reuse. Preserve personal handoff drafts locally until the PM deletes them; expose reset/delete. No model-inferred permanent customer facts. Versioned team triage policy is human maintained. Human corrections override model inferences, but do not rewrite original evidence. |
| 05 Permissions | Auto scoped read and draft; block external write and send. No autonomous roadmap changes, assignments, or delivery promises. Permission enforcement belongs in tool access controls, not only the prompt. |
| 06 Verification | Before showing a model-produced finding: validate schema, source ID existence and access, claim support, timestamps, duplicate lineage, uncertainty, coverage, and permitted next actions. Require every factual claim to be supported or withheld/marked for clarification; forbid fabricated links, amounts, and completed-action claims. |

These ceilings and retention settings are hypotheses to discuss in class, not measured optima or RocketShip policy.

## Failure, freshness, and verification

- Source outage: identify which source failed and show partial coverage. Do not silently treat unavailable data as no risks.
- Missing evidence: mark NEEDS CLARIFICATION; do not invent account, severity, owner, date, or commercial impact.
- Potential incident: surface the reported concern for immediate human verification within the user's view. Do not claim a confirmed incident or send an alert autonomously.
- Failed verification: use at most the remaining bounded repair attempt. If still failing, show an explicit unavailable/partial result and safe accessible source references, withholding unsupported recommendations.
- Proposed freshness target: fetch a new source snapshot at generation time; display retrieval time and source update time. Do not claim connector freshness until measured. Do not reuse a cached snapshot older than 15 minutes for a newly generated brief without a visible warning and refresh option.
- Initial performance budget for discussion: p95 under 30 seconds and model usage under $0.20 per brief. These are proposed targets, not pricing facts or achieved results; revisit using the class dataset and chosen model. Connector/storage costs are separate.
- Track model calls, read requests, input/output tokens, elapsed time, source failures, and verification failures. Include retries in the same budget.

## Trade-offs I want to discuss

1. **Control over autonomy:** Juno prepares the decision; the PM executes it. This limits damage and matches M1.
2. **Bounded depth over repeated retries:** One evidence pass and one repair opportunity should be a starting point, with transparent failure rather than endless attempts.
3. **Relevant coverage over indiscriminate context:** Preserve whole relevant threads and linked contradictions; do not rely only on top matches that might omit the most serious issue.
4. **Rich provenance without false certainty:** Metadata makes claims traceable; three linked records do not equal three independent reports.
5. **Large workspace, bounded computation:** The list can contain more than five findings. Chunking, continuation, and explicit coverage are required when the corpus exceeds a run's budget.

## Ten-minute company-context review in class

Confirm the actual channel/project/document names, PM user, triage/severity rules, source permissions, incident handoff role, retention requirements, and any supplied freshness/performance constraints. Replace our guesses with those facts before finalizing the PRD.

Questions to bring:
- Must Juno cover all unresolved risks or only the selected week's new/updated signals?
- Which record is authoritative when Slack, Jira, and Notion disagree?
- What is the right failure behavior when the highest-impact source cannot be fetched?
- Does class expect writes with confirmation, or is a deliberately read-only copilot acceptable?
- What cost, latency, and retention assumptions should the class dataset support?

## In-class deliverable

Lab 1: refine the six-surface sketch above.
Lab 2: use the course Architecture Decider and PRD Builder, incorporate the live cost/trade-off lessons, and complete [prd.md](prd.md).

Final PRD must include: problem/user, all six surfaces, actual sources and exclusions, freshness/failure behavior, tool verbs and omitted tools, loop/cost/latency limits, memory/expiry/override rules, action permissions and rationale, pre-output verification and failure behavior, an eval-plan stub, and out-of-scope actions.

Do not label the PRD final until these class-dependent choices are resolved.
