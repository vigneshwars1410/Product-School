# Roadmap, PRD & Prototype (Module 4)

## Your strategic anchors
- **Persona (M2), who are you solving for?:** A dispatcher (day or night shift) responsible for coordinating drivers in real time across an active fleet.
- **Primary success metric (M3), your leading indicator:** Coordinator Scheduling CSAT rises above 3.5 and workflow completion rate for shift handoff climbs above 60%. These are leading indicators that the trust gap is closing.
- **Moment of misery (M2), the specific friction blocking the goal:** Dispatch reassignments take 8–15 minutes to propagate to drivers with no push notification, and driver status updates lag 20–60 minutes on the dashboard — so a stop can show "in progress" long after it's delivered. The dispatcher's Moment of Misery is captured directly in the research: they've stopped trusting the board and now run a parallel WhatsApp group as "the real system," meaning they're managing two systems instead of one.
- **Guardrail metric (M3), what must not drop or break:** Driver adoption of core features (Dispatch Board, Route Optimizer) must not drop below 85%. Protects the existing base while fixing coordinator pain.

## Scan the backlog & set a human baseline
- **My instinctive “quick wins” before touching the AI (2 to 3 feature IDs + why):** B1, B2, B3

## Audit, override & decide
- **Where did you override the AI? (feature + old vs. new score + why):** B1 One‑Click Compliance Checklist.

Old score- Effort = 3, Value = 2 (AI put it in “Time Sinker”).
New Score- Effort=2, Value=4

Mismatch with persona pain: Dispatcher persona’s biggest inefficiency was the 14.6‑minute compliance step vs. 3‑minute benchmark, with CSAT at 2.2 -the lowest score in the heatmap. That’s not a minor admin nuisance; it’s a critical trust‑erosion loop. Coordinators abandon the workflow because compliance feels unreliable and slow.

Override rationale: AI’s cut assumes compliance is secondary. But the data shows it’s a primary abandonment driver (69% drop‑off after route assignment). By underrating B1’s value, AI misses how compliance inefficiency compounds the trust breakdown.
- **Did the AI over-value a Sales/Eng request your M2 interviews don’t support?:** No
- **Did it underweight something your M3 cohort/funnel data strongly supports?:** Yes, B1 One‑Click Compliance Checklist

## Generate your interactive roadmap
- **My “Now” lane (this sprint), the 2 to 3 quick wins I’ll build first:** B6 Driver Alert Notifications
B1 One-Click Compliance Checklist
B3 Shift Handoff Wizard
- **What I cut, and the “no” I’m protecting the scope from:** B2	Smart Daily Report Auto-Fill
B7	Contextual AI ETA Display
B7	Contextual AI ETA Display
I’m protecting the scope from feature creep into non‑persona needs — specifically executive dashboards, legal audit exports, or Sales‑requested analytics. These dilute focus away from the dispatcher persona’s critical pain points validated in M2/M3 (scheduling trust gap, compliance inefficiency, handoff delays).
- **Prototype/roadmap screenshot link (paste into your deliverables):** https://github.com/vigneshwars1410/Product-School/blob/7e71ed6e564479aa506db7d50dc05f0dde4b3a3d/04-roadmap/Roadmap.jpg
