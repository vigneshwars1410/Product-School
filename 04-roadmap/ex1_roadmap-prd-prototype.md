# Feature Roadmap, Module 4 · RouteLogic Velocity

**Team:** 2 engineers + 1 designer + 1 CS lead

## Strategic anchors
- **Persona:** A dispatcher (day or night shift) responsible for coordinating drivers in real time across an active fleet.
- **Primary metric:** Coordinator Scheduling CSAT rises above 3.5 and workflow completion rate for shift handoff climbs above 60%. These are leading indicators that the trust gap is closing.
- **Moment of misery:** Dispatch reassignments take 8–15 minutes to propagate to drivers with no push notification, and driver status updates lag 20–60 minutes on the dashboard — so a stop can show "in progress" long after it's delivered. The dispatcher's Moment of Misery is captured directly in the research: they've stopped trusting the board and now run a parallel WhatsApp group as "the real system," meaning they're managing two systems instead of one.
- **Guardrail:** Driver adoption of core features (Dispatch Board, Route Optimizer) must not drop below 85%. Protects the existing base while fixing coordinator pain.

## Scoring
| Feature | Value | Effort | Quadrant | Decision | Rationale |
|---|---|---|---|---|---|
| B1 One-Click Compliance Checklist | 4 | 2 | Quick Win | Now | The compliance inefficiency is a critical abandonment driver in funnel data |
| B2 Smart Daily Report Auto-Fill | 2 | 4 | Time Sinker | Cut | AI-auto-fill effort is disproportionate to a task that isn't in the Moment of Misery; admin convenience, not trust repair. |
| B3 Shift Handoff Wizard | 5 | 2 | Quick Win | Now | Maps 1:1 to the Primary Metric (handoff completion >60%); scoped, buildable within the pilot team and timeline. |
| B4 Mobile-First Coordinator Dashboard | 5 | 5 | Major Project | Next | Would structurally fix the "two systems" problem by unifying dispatch/compliance/handoff, but a full surface redesign exceeds a 4-week, 2-engineer pilot — sequence for post-pilot. |
| B5 Step Progress Indicator | 1 | 1 | Fill-In | Later | Cosmetic wayfinding; cheap but doesn't reduce lag or rebuild trust — only worth it as pilot-team downtime filler. |
| B6 Driver Alert Notifications | 5 | 2 | Quick Win | Now | Directly attacks the Moment of Misery — this is the fix for the 8–15 min propagation gap that created the WhatsApp shadow system. Highest-leverage feature in the list. |
| B7 Contextual AI ETA Display | 1 | 4 | Time Sinker | Cut | 11% adoption is a signal, not a fluke — sunk investment already isn't landing with users; don't compound it before the trust problem is fixed. |
| B8 Fleet Analytics Manager View | 2 | 4 | Time Sinker | Cut | Serves the enterprise decision-maker/manager persona, not the dispatcher — classic Sales-driven ask that doesn't touch this initiative's anchors. |
| B9 Compliance Audit Trail Export | 2 | 2 | Fill-In | Later | Useful for CS/regulatory asks, low cost, but orthogonal to the dispatcher trust gap — nice-to-have, not core. |
| B10 In-App Coordinator Training | 2 | 2 | Fill-In | Later | Marginally helps CSAT via smoother onboarding, but doesn't address the cause of low trust — treat as support collateral, not a pilot feature. |

## Roadmap
### NOW, Pilot (4 weeks, 3 accounts)
- **B1 One-Click Compliance Checklist**, The compliance inefficiency is a critical abandonment driver in funnel data
- **B3 Shift Handoff Wizard**, Maps 1:1 to the Primary Metric (handoff completion >60%); scoped, buildable within the pilot team and timeline.
- **B6 Driver Alert Notifications**, Directly attacks the Moment of Misery — this is the fix for the 8–15 min propagation gap that created the WhatsApp shadow system. Highest-leverage feature in the list.

### NEXT, GA Release (weeks 5-8)
- **B4 Mobile-First Coordinator Dashboard**, Would structurally fix the "two systems" problem by unifying dispatch/compliance/handoff, but a full surface redesign exceeds a 4-week, 2-engineer pilot — sequence for post-pilot.

### LATER, backlog
- **B5 Step Progress Indicator**, Cosmetic wayfinding; cheap but doesn't reduce lag or rebuild trust — only worth it as pilot-team downtime filler.
- **B9 Compliance Audit Trail Export**, Useful for CS/regulatory asks, low cost, but orthogonal to the dispatcher trust gap — nice-to-have, not core.
- **B10 In-App Coordinator Training**, Marginally helps CSAT via smoother onboarding, but doesn't address the cause of low trust — treat as support collateral, not a pilot feature.

### ✂ Cut List
- **B2 Smart Daily Report Auto-Fill**, AI-auto-fill effort is disproportionate to a task that isn't in the Moment of Misery; admin convenience, not trust repair.
- **B7 Contextual AI ETA Display**, 11% adoption is a signal, not a fluke — sunk investment already isn't landing with users; don't compound it before the trust problem is fixed.
- **B8 Fleet Analytics Manager View**, Serves the enterprise decision-maker/manager persona, not the dispatcher — classic Sales-driven ask that doesn't touch this initiative's anchors.
