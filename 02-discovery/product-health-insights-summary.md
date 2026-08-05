# Product Health & Insights Summary

## Executive Summary

The product's underlying platform capability — particularly route optimization inputs and administrative reporting — remains a genuine differentiator that continues to justify enterprise purchase decisions. However, this strength is being steadily undermined by instability and friction in the daily frontline experience, where crashes, lag, and buried core actions are pushing drivers and dispatchers toward informal, off-platform workarounds (texting, WhatsApp, paper manifests). Left unaddressed, this widening gap between back-office power and front-line usability is now materially threatening adoption and at least one enterprise renewal.

## Thematic Synthesis

### Technical Stability

Reliability issues are concentrated in exactly the moments where drivers can least afford them: mid-route, outdoors, and often without a strong connection. Route data loss on crash and unreliable proof-of-delivery uploads are forcing drivers to duplicate effort or fall back on phone calls to the office, eroding trust in the app as a system of record.

- **Critical** — App crashes mid-route once the stop list exceeds ~40 stops, wiping the remaining route and forcing a full reload from the server.
- **High** — Proof-of-delivery photo uploads fail silently on weak signal in roughly a third of cases, with no retry queue or success confirmation, leading to repeated retakes.
- **Low** — GPS pin drift of up to 200m in dense urban areas causes incorrect "arrived at stop" auto-detection.

### Discovery / UX

Frontline users describe a product that has accumulated features without corresponding effort to keep core, high-frequency actions fast and easy to find. The result is an interface where the actions performed dozens of times a day compete for attention with rarely-used functionality, extending onboarding time and slowing the core workflow drivers rely on most.

- **High** — Marking a delivery complete requires three taps across three separate screens, with no single-tap completion path; this is the most frequently cited frontline complaint and a direct driver of off-platform workarounds.
- **Medium** — Core actions such as Start Route and Mark Delivered are now buried two to three levels deep following recent feature additions, with no ability to configure or prioritize the home screen.
- **Medium** *(qualitative)* — New drivers report a steep, multi-day learning curve, with menu depth obscuring even essential functions like reporting a failed delivery; onboarding tutorials cannot be reopened after first launch and no persistent in-app help exists for this flow.

### Algorithmic Curation (Route Optimization)

Drivers describe the optimization engine as disconnected from real-world, on-the-ground constraints. Because the system has no mechanism to learn from local knowledge, drivers report routinely and manually overriding its suggestions, which limits the tool's practical value despite its sophistication.

- **Medium** — Route optimization does not account for road closures or known access constraints (e.g., loading docks, one-way streets), and offers no way to save local overrides, resulting in daily manual correction by experienced drivers.

### Platform Sync (Dispatcher ↔ Driver)

A recurring and high-impact theme is the disconnect between what dispatchers see and what is actually happening in the field. Delays in both directions — reassignments reaching drivers, and driver status updates reaching dispatch — have led both roles to independently stand up informal, manual channels (a shared messaging group) as their trusted source of truth in place of the platform.

- **Critical** — Dispatch reassignments take 8–15 minutes to propagate to the driver app, with no push notification, resulting in drivers acting on stale route information.
- **Medium** — Driver status changes lag 20–60 minutes on the dispatcher dashboard, causing completed stops to display as "in progress" and undermining dispatcher confidence in the board.

### Minor Technical Debt

Aggregated lower-severity items with limited standalone impact but contributing to overall perceived polish: GPS positioning drift affecting stop auto-detection, and onboarding/help content that cannot be revisited after initial app launch.
