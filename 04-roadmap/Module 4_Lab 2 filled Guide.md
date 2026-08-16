# PRD & Prototype Sprint (Module 4)

## Pick & scope with MoSCoW
- **The “Now” feature I’m scoping (name + one-line core description):** B1 · One-Click Compliance Checklist
Collapse the 14.6-min compliance step into a smart pre-filled form
- **My finalized Must-Haves (after overriding the AI):** Auto-populate the compliance form from existing system data (driver ID, vehicle, route, timestamp) - the core mechanism the whole feature rests on.

Single-screen review-and-submit, replacing the current multi-step flow.

Manual edit of any pre-filled field before submission - dispatchers must be able to correct data before it hits compliance records.

Submission writes to the existing backend compliance record/audit trail - no new data model this sprint.

Inline field validation before submit - with compliance as the flagship deliverable, bad data reaching the record is a launch-blocking risk, not a nice-to-have.

Completion-time instrumentation (start-to-submit timing)
- **What I demoted from Must → Should/Won’t, and why:** New compliance categories or checklist items beyond what exists today.

Changes to the audit-trail export flow (B9's scope).
Rollout beyond the 3 pilot accounts.

AI/ML-driven inference of compliance answers -pre-fill from known data only, no prediction.

Mobile-specific redesign -ships on the existing surface.

## Generate your Simplified PRD
- **One thing my PRD makes explicit that a vague brief would have missed:** The PRD makes the boundary between "pre-filled" and "manually edited" explicit at the data level -not just in prose, but as a functional requirement (field-level edit marking) and a safety guard (never let an edited value look identical to an auto-filled one). A vague brief would've said "let dispatchers review and submit" and stopped there. The PRD forces the build to preserve exactly who touched what, which is the difference between a compliance record that holds up in an audit and one that doesn't.

## Prompt-to-prototype sprint
- **Where did the prototype reveal a gap in my PRD logic? (what I had to update):** "Emergency Contact Override" field.
The prototype exposed that Must-Haves treated "no source data" as an edge case (rare, flagged, fill it in) rather than a designed field with its own rules. In practice it's sitting as a hard submission blocker on every single completion, which works against the Primary Metric — if every dispatcher has to type this manually every time, it eats directly into the time savings you're measuring (14.6 min → under 3 min). That's the update the PRD needs: either define Emergency Contact Override as a proper field with its own source/persistence logic, or determine it shouldn't block submission the same way a true missing-data case should.
- **My shareable prototype URL (Lovable: Share → Share Preview · Bolt: Publish → Web):** https://github.com/vigneshwars1410/Product-School/blob/30a782bd4cb11f0136992aad14585db37de2767c/04-roadmap/ex2_m4_prototype.png
