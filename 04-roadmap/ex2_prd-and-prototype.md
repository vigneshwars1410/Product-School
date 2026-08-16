# B1 · One-Click Compliance Checklist Collapse the 14.6-min compliance step into a smart pre-filled form, Simplified PRD (RouteLogic)

**Author:** Me · **Status:** Draft · **Target:** High-Fidelity Prototype · **Persona:** A dispatcher (day or night shift) responsible for coordinating drivers in real time across an active fleet.

## 1. The Big Picture
- **Vision:** The dispatcher's compliance step goes from a 14.6-minute manual slog to a single-screen, pre-filled confirmation.
- **Press release:** RouteLogic today shipped One-Click Compliance for dispatchers, cutting the daily compliance checklist from a 14.6-minute manual form to a single pre-filled screen the dispatcher reviews and submits. Instead of hunting down driver, vehicle, and route details by hand mid-shift, dispatchers now see that information already populated from data RouteLogic already has - they just confirm it's right and move on.
For a dispatcher juggling live reassignments and status checks across a fleet, every minute lost to manual paperwork is a minute they don't have for the problems that actually put deliveries at risk. One-Click Compliance claws back that time - turning a 14.6-minute task into a single-screen confirmation -so dispatchers spend their shift managing the fleet, not managing forms.
- **Success metric:** Median compliance-step completion time, from form-open to submit — target: reduce from 14.6 min to under 3 min across the 3 pilot accounts.
- **Guardrail:** Compliance record error/correction rate post-submission must not increase versus the current manual process — the pre-fill can't trade speed for data accuracy, since these records feed regulatory audits.

## 2. The Details
### User stories
- As a dispatcher, I want the compliance form to arrive pre-filled with data RouteLogic already has, so that I don't manually re-enter information I've already logged elsewhere.
- As a dispatcher, I want to review and correct any pre-filled field before submitting, so that I stay accountable for what goes into the compliance record.
- As a dispatcher, I want to submit the checklist in one screen, so that I can get back to managing my fleet instead of managing a form.
- As a dispatcher, I want to see how long the compliance step took, so that I trust the tool is actually saving me time, not just changing its shape.
### Screens to build
- Entry point- dispatcher's task list/dashboard with the compliance item surfaced, showing it's ready for one-click review (not a blank form to fill from scratch).
- Feature core- the pre-filled compliance form: populated fields, clear affordance to edit any field, single "Review & submit" action.
- Success/confirmation -submission confirmation showing the record was saved, plus the time taken for this instance (reinforces the "minutes back" value prop).
### Functional requirements
- Form fields (driver ID, vehicle, route, timestamp) must be pre-populated from existing system data on screen load -no field starts blank if the data is available.
- Every pre-filled field must be directly editable by the dispatcher before submission.
- Submission must be completable in a single screen — no multi-step or multi-page flow.
- The system must record start time (form open) and end time (submit) for every completion.
- Submission must write to the same compliance record structure used today — no new data schema.
- A submitted record must be uneditable after submission (preserves audit integrity).
- Any field left blank by the system (no source data available) must be visually flagged as needing manual entry, not silently skipped.
### Smart behaviors (Situation → Outcome)
- If all required fields are pre-filled and unedited, then the "Review & submit" action is enabled immediately — no forced review delay.
- If a dispatcher edits a pre-filled field, then the field is visually marked as manually changed, so the record shows what was auto-filled vs. corrected.
- If a required field has no source data to pre-fill, then it's shown empty and flagged, and submission is blocked until it's completed.
- If submission succeeds, then the confirmation screen shows the elapsed time for that completion.
- If a dispatcher navigates away before submitting, then their edits are not saved (draft persistence is a Should-Have, not in this prototype).
### Technical constraints
- No backend or database - all "existing system data" is mocked as static local data.
- No real API calls or network requests.
- No authentication or account/session handling.
- No audit-trail export or compliance-record history view (that's B9's scope).
- No AI/ML inference on field values - mocked data stands in for pre-fill, nothing is predicted.
- No mobile-specific layout - single responsive screen is enough for the prototype.

## 3. The Logistics
### Features out
- No new compliance categories or checklist items beyond what exists today.
- No changes to the audit-trail export flow (B9's scope, not this prototype's).
- No rollout beyond the 3 pilot accounts.
- No AI/ML-driven inference or prediction of compliance answers.
- No mobile-specific redesign.
### Edge cases & safety guard
- No source data available for a field - field renders empty and flagged, submission blocked until manually completed. Must never silently submit a blank required field as if it were filled.
- Dispatcher edits a pre-filled value - the change is visibly marked as manual. Must never let an edited value look identical to an auto-filled one - that erases accountability for who changed what.
- Dispatcher tries to resubmit an already-submitted record - action is blocked, record shown as read-only. Must never allow a second submission to overwrite an existing compliance record.
- Dispatcher navigates away mid-review - in-progress edits are discarded, nothing is auto-submitted on exit. Must never submit a record the dispatcher didn't explicitly confirm.
- Pre-filled data is stale or looks wrong - dispatcher can still edit and submit; the prototype does not attempt to detect or block "wrong-looking" data (that's the anomaly-flagging Should-Have, out of scope here). Must never present pre-filled data with false confidence - no visual styling implying the system has verified it.
### Decision log
- Instrumentation over polish - completion-time tracking was pulled into Must-Have (ahead of draft auto-save and anomaly flagging) because without it, there's no evidence the 14.6-min claim actually moved. Protects against shipping a feature with no way to prove it worked.
- No AI inference on field values - pre-fill is limited strictly to data RouteLogic already holds, with no predictive fill-in. Protects scope from ballooning into B2/B7 territory (both scored Time Sinker) and keeps the audit-trail risk contained to "wrong data source," not "wrong model output."
### Evals
- % accuracy - of pre-filled fields, the percentage that match ground-truth source data without requiring dispatcher correction. Target: >95%, so most fields require confirmation only, not repair.
- Time-on-task - median time from form-open to submit, replacing the current 14.6-min baseline. Target: under 3 minutes across the 3 pilot accounts (matches the primary success metric already set).
- Safety - rate of submitted records later flagged as inaccurate during a compliance review or audit. Target: 0% increase versus the current manual process - the pre-fill must not trade speed for record accuracy, since these records feed regulatory audits.

## MoSCoW scope
- **Must:** Auto-populate the compliance form from existing system data (driver ID, vehicle, route, timestamp) — the core mechanism the whole feature rests on.; Single-screen review-and-submit, replacing the current multi-step flow.; Manual edit of any pre-filled field before submission — dispatchers must be able to correct data before it hits compliance records.; Submission writes to the existing backend compliance record/audit trail — no new data model this sprint.; Inline field validation before submit — with compliance as the flagship deliverable, bad data reaching the record is a launch-blocking risk, not a nice-to-have.; Completion-time instrumentation (start-to-submit timing)
- **Should:** Draft auto-save on interruption, given how frequently dispatchers get pulled away mid-task.; Anomaly flagging when auto-filled data looks inconsistent with recent history — supports trust in the pre-fill itself.; A lightweight before/after view for CS to show pilot accounts the time saved.
- **Could:** Bulk-apply for recurring compliance items across multiple stops in a shift.; Per-account configurable field defaults.; Exportable summary of time saved, for use in renewal/expansion conversations.
- **Won't (now):** New compliance categories or checklist items beyond what exists today.; Changes to the audit-trail export flow (B9's scope).; Rollout beyond the 3 pilot accounts.; AI/ML-driven inference of compliance answers — pre-fill from known data only, no prediction.; Mobile-specific redesign — ships on the existing surface.

---
**Builder hook:** Build a working prototype based on this PRD. Use the User Story as the core flow, Functional Requirements as build constraints, and prioritize speed and clarity over visual complexity.
