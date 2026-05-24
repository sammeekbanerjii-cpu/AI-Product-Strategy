# Data Flywheel Map

Data Flywheel Score:
SCORES:
- Corrections Loop: 1/5
- Preferences Loop: 2/5
- Domain Context Loop: 2/5
- Network Loop: 1/5

Total: 6/20

Readout: No flywheel. Data goes in and gets thrown away.

Weakest loop: Corrections Loop, Network Loop (1/5)

Fix: Instrument the AI Copilot authoring workflow to capture marketer edits as labeled training signal before the layer scales. Every edit discarded today is proprietary data permanently lost. This is the highest-leverage investment to close the flywheel — and the most exposed vulnerability to an attacker who ships correction capture on day one.

Correction Loop — 1/5

-> What you capture today: Nothing. Marketer edits to AI-generated offer drafts are not captured or reused.

-> How it compounds: If captured: every editorial correction becomes proprietary training data, making the next AI-generated draft more accurate for that segment and use case. 

Preference Loop — 2/5

-> What you capture today: Segment-level offer performance data (CTR, conversion by audience) flows into Data Cloud via OGS. Individual marketer preferences and editorial patterns are not captured. 

=> How it compounds: If activated: the system builds team and segment-level taste profiles over time — surfacing messaging styles, CTA formats, and offer types that convert for specific audiences without manual configuration. 

Domain Context Loop — 2/5

-> What you capture today: 18 months of Salesforce-specific B2B offer performance signal exists in Data Cloud — trial conversion rates, webinar engagement, gated content completion by segment. Cross-offer learning is not yet active. 

-> How it compounds: If connected: high-converting patterns in one offer category (e.g. PLG trials for SMB) inform recommendations in adjacent categories (e.g. demo offers for the same segment), compounding domain intelligence across the full catalog. 

Network Loop — 1/5

-> What you capture today: Each team's usage is isolated. Write-once, reuse of offer templates provides shared infrastructure but generates no network signal. 

-> How it compounds: If built: each new marketing team onboarding enriches the collective performance model — more segments, more offer types, more conversion signal — making recommendations smarter for all teams on the platform.

---

# Encroachment Threat Assessment

1. Platform Encroachment
   -> Attacker: Agentforce / Einstein
   -> Vector: Native AI offer orchestration embedded directly on top of Data Cloud, eliminating the need for a standalone offer management platform.
   -> Time-to-threat: 12–18 months
   -> % of value at risk: 60%
2. Vertical Competitor
   -> Attacker: Mutiny
   -> Vector: Ships a native Salesforce Data Cloud connector with correction capture and preference learning built in from day one, compounding signal faster than    -> Offer Service's latent flywheel.
   -> Time-to-threat: 6–9 months
   -> % of value at risk: 40%
3. Adjacent Expansion
   -> Attacker: Adobe Experience Cloud
   -> Vector: Extends AEM's existing enterprise content and offer management capabilities with an AI authoring layer, then pitches Salesforce leadership as a cost consolidation play against an existing enterprise agreement.
   -> Time-to-threat: 18–24 months
   -> % of value at risk: 50%

---

## 90-Day Encroachment Plan

*Your partner played the Big Tech attacker. What was their plan to kill you?*

-> Attacker: Agentforce / Einstein

-> Attack vector (target the weakest loop): Use native Salesforce infrastructure and existing Data Cloud access to ship an AI offer generation layer that captures correction signal from day one — exploiting the Correction loop Offer Service hasn't yet closed.

-> Weeks 1–4 — what they ship: Launch "AI Offer Generator" natively within Salesforce's internal campaign tooling — generating offer briefs directly from Data Cloud's existing performance signal. Embedded in the marketer's existing workflow with no new platform to learn or adopt.

-> Weeks 5–8 — how they poach users: Bundle it into existing internal tooling at zero incremental cost. Run internal roadshows for the marketing org positioning it as a native Einstein capability. Critically — capture every marketer edit as labeled correction signal from day one, compounding a flywheel that Offer Service hasn't instrumented.

-> Weeks 9–12 — why users don't come back: Add automated A/B test recommendations and offer sequencing. The correction loop compounds quickly — offers generated in week 12 are materially smarter than week 1. Leadership sees a native capability with no separate platform maintenance cost. The consolidation argument becomes structurally hard to defeat.

Your defense:Move from offer authoring to workflow ownership — make Offer Service the system of record for the full offer lifecycle: create → publish → experiment → attribute → optimize. Close the correction capture loop immediately, before the AI Copilot scales. Deepen OGS's Data Cloud integration so Offer Service's write path becomes irreplaceable infrastructure — not a feature Agentforce can replicate with a single sprint.

---
