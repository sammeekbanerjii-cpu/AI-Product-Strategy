# My AI Product Strategy

> A living strategy built across 6 sessions. Each module adds one component. By Module 6, this repo IS your strategy — version-controlled, board-ready, portable.

# Offer Service

> -> If we surface 18 months of Salesforce.com offer performance signal at the point of authoring, marketing managers will ship better-converting offers faster — closing the data loop that currently sits dormant in Data Cloud.

---

## Strategy at a Glance

| Component | Module | Status | Key Artifact |
|-----------|--------|--------|-------------|
| **The Bet** | M1 | [x] | `01-the-bet/` |
| **The Moat** | M2 | [x] | `02-the-moat/` |
| **The Margin** | M3 | [x] | `03-the-margin/` |
| **The Contract** | M4 | [x] | `04-the-contract/` |
| **The Guardrails** | M5 | [x] | `05-the-guardrails/` |
| **The Pitch** | M6 | [x] | `06-the-pitch/` |

---

## The Bet (M1)

**What we're building, for whom, why now.**

- **Product:** Offer Service — Salesforce's internal digital marketing platform. Three pillars: Offer Catalog (centralized authoring across all Salesforce web properties) · OFX (offer experience rendering layer) · OGS (offer generation signal — behavioral data routed into Data Cloud).
- **AI Value Archetype:**  Copilot — AI surfaces recommendations and drafts at the point of authoring. Marketer reviews and publishes. Human in the loop on every output until trust is established and HITL% declines to target.
- **Vulnerability Scores:** Contextual Moat 2/5 · Data Advantage 3/5 · Platform Exposure 2/5. Workflow depth is real but not yet fully habituated — a determined team could migrate in a quarter if Offer Catalog hasn't achieved write-once-reuse-everywhere adoption. Data advantage is real but latent — OGS feeds Data Cloud, the return path to intelligent decisioning does not yet exist. Platform Exposure risk is internal, not external — Agentforce and Marketing Cloud consolidation are the live vectors.
- **Top Risk:** -> The data advantage is latent, not active — if Offer Intelligence doesn't close the loop between OGS behavioral signals and intelligent offer decisioning before Agentforce matures, it risks being absorbed into the AI platform layer rather than expanded as a standalone product.
- **Confidence:** M — workflow moat and Data Cloud integration are real today. Data moat is a bet, not a fact. Confidence upgrades to H when correction loop is live and HITL% is declining QoQ.
- **Prototype:** https://preview--offer-muse-56.lovable.app/
- **Kill Criteria:** -> Marketers default to manual authoring and ignore AI recommendations after 60 days of availability · AI-generated drafts show no statistically significant conversion lift vs. manually authored offers after two campaign cycles · HITL% rises for two consecutive quarters — correction loop is not compounding · Agentforce ships native offer orchestration with Data Cloud integration before Offer Intelligence closes the data loop · Data Cloud signal quality degrades and conversion scoring accuracy falls below 88% on the golden dataset for two consecutive months.

→ Details: [`01-the-bet/`](01-the-bet/)

---

## The Moat (M2)

**Why this won't get copied in 6 months.**

- **Data Flywheel Score:**  6/20 — Correction 1/5 · Preference 2/5 · Domain Context 2/5 · Network 1/5. Not compounding.
- **Weakest Loop:** Correction (1/5) — no correction capture pipeline exists. Marketer edits to AI-generated drafts are discarded. Every override is a signal miss.
- **Top Encroachment Threat:** Mutiny — ships a native Data Cloud connector in 6–9 months. If correction capture is not live before that, Mutiny starts the compounding loop on Salesforce's own proprietary signal. The workflow moat does not protect against a competitor that compounds faster.
- **Encroachment Defense:** Close the correction loop before Mutiny ships. Instrument field-level delta logging between AI output and final published offer in the AI Copilot authoring workflow — tagged by segment, offer type, and product line — routed into the model layer. Mutiny can replicate the connector. It cannot replicate 18 months of B2B offer performance signal plus a correction loop that has been compounding since launch. The defense is sequencing: correction capture ships in H1 so the data moat is building before the competitive window closes.
- **Vendor Portability:** Locked - single OpenAI provider, direct API calls, no abstraction layer, no eval harness. Current estimated swap time: 3–6 weeks vs. 48-hour target. Three actions to reach 48-hour readiness: abstraction wrapper this week · eval harness this month · multi-model routing with live fallback this quarter.

→ Details: [`02-the-moat/`](02-the-moat/)

---

## The Margin (M3)

**Will this make money or bleed it?** Yes

- **Gross Margin (current):** ~50–55% — no cascade architecture, frontier model on all requests, fixed infrastructure cost regardless of usage volume.
- **Gross Margin (AI-adjusted):** ~65–70% post-cascade routing · ~72–75% with semantic caching added · ~75–80% at full optimization. Cascade routing alone recovers 10–15 margin points by routing 80% of requests to small/mid-tier models. Target: return to SaaS-equivalent margins (80%+) through architecture, not price increases.
- **Pricing Model:** Hybrid — $50/seat/month base + $25 per AI-assisted offer published. Aligns revenue to the value event — a published offer — rather than seat access. NRR scales with offer volume, not headcount. $25 captures 10–15% of labor savings per offer ($150–250 saved) — well below giveaway territory.
- **Pricing Today → Tomorrow:** Today: $75/seat/month flat SaaS. Revenue capped at seat count, no upside from usage growth. Tomorrow: $50/seat base + $25/AI-assisted offer published. At 10 offers/user/month → $300 revenue/user vs. $75 today. Gross profit grows +$1,800/month (+67%) while COGS shifts from ~$30/user fixed to $15.14/user variable.
- **Total AI COGS / unit:**  $0.00096/request blended · ~$0.14/user/month at 150 requests per active marketer. Inference ROI: $133 revenue per user ÷ $0.14 AI COGS = 950x. A 3× provider price spike raises COGS from $0.14 to $0.42/user/month — gross margin moves by 0.2 points. Provider cost volatility is not a material risk at this ROI ratio.
- **Cascading Strategy:** Triage: -> GPT-4o-mini / Claude Haiku — handles all simple classification, field validation, disclosure rendering, and template population. Fast, cheap, high-volume.; frontier: -> GPT-4.1 — reserved exclusively for enterprise offer draft generation and complex personalization where output quality directly impacts conversion rates.; ratio -> 80% small/mid · 20% frontier
- **Net Margin Shift:** The right headline is +67% gross profit, not −4% margin. Δ margin % −4% is the intentional cost of switching from a seat-count ceiling to an outcome model with no natural revenue cap. Gross profit grows from $2,700/month to $4,500/month at 60 users. Margin percentage compresses slightly because the hybrid model carries variable COGS per outcome — that is the correct trade.
- **Break-even at:** AI COGS fully covered at 1 AI-assisted offer published per user per month ($25 outcome fee vs. $0.14 blended AI COGS). Revenue parity with the prior $75/seat model reached at 1 published offer/month ($50 base + $25 = $75). Every offer published beyond the first is incremental gross profit at near-zero marginal cost — the margin compounds with usage, not headcount.

→ Details: [`03-the-margin/`](03-the-margin/)

---

## The Contract (M4)

**Why users will trust a probabilistic system.**

- **Reliability Target:** 92% — weekly pass rate against full golden dataset. Defensible, measurable, shippable.
- **Golden Dataset:** 12 cases · 6 adversarial · target v1: 150 cases. All expected outputs are binary testable boolean conditions — no narrative descriptions, every condition is pass/fail. Judge: Claude Sonnet as evaluator · rubric: brand tone (1–5) · factual accuracy (pass/fail) · segment-offer fit (1–5) · uncertainty signal correctness (pass/fail). Calibration: judge runs against all golden rows weekly — if judge disagrees with labeled answer on >5% of rows, judge is recalibrated before live traffic. Every model or prompt change runs the full dataset before merge.
- **Confidence UX:** Offer Intelligence surfaces confidence explicitly at every tier — marketers see the score, the signal strength, and the source count before they publish. Uncertainty is never hidden. Three tiers: >90% point-estimate score, publish active, reasoning panel collapsed · 50–90% score as range, review recommended, reasoning expanded · <50% score null, publish blocked, human review queue triggered.
- **HITL Architecture:** **Trigger:** Confidence <70% OR safety flag (brand violation / factual accuracy failure / insufficient signal) → human review queue. PLG provisioning error → immediate human queue regardless of confidence score.
- **Failure Mode Coverage:** Six adversarial cases — thin signal (score null, human review triggered) · brand compliance failure (prohibited terms flagged, publish blocked) · true duplicate detection (warning before generation) · A/B variant false positive (duplicate block bypassed on marketer flag) · PLG provisioning failure (error state within 5s, no partial offer written) · factually incorrect output (deprecated feature caught, correct replacement surfaced).

→ Details: [`04-the-contract/`](04-the-contract/)

---

## The Guardrails (M5)

**What breaks when this scales — and what compounds.**

- **Compounding System:** 3 loops · 0 compounding. Recursive Learning (Missing — correction capture never built, root dependency for all loops) · Cross-Domain Transfer (Broken — OGS signal exists in Data Cloud, transfer mechanism to recommendation layer does not) · Network Intelligence (Missing — depends on loops 1 and 2). Freeze test currently passes — that is the problem. Target: freeze test fails by Q4 as HITL% declines QoQ. Correction validation gate against OGS conversion actuals is a prerequisite to Recursive Learning going live — not a follow-on.
- **Governance Posture:** Covers all AI-generated outputs — offer draft generation, conversion scoring, form recommendations, progressive profiling, disclosure summaries, and CTA suggestions. Applies to all Salesforce marketing teams authoring and publishing across Salesforce web properties. EU AI Act Limited risk tier · Einstein Trust Layer compliant · GDPR/CCPA controls active.
- **Autonomy Boundaries:**Auto: form validation · disclosure summaries · CTA suggestions on standard templates · conversion scoring ≥90% confidence · progressive profiling field suppression for returning visitors. 🟡 Human approval required: confidence <70% · new product lines (first 90 days) · pricing or legal terms · enterprise segment offers · PLG provisioning confirmation · any safety flag triggered. 🔴 Never auto: publishing to enterprise accounts (>$100K ACV) · generating or modifying pricing, discount, or legal terms · activating autonomous sequencing for new audience segments · regulatory disclosures · reactivating AI-assisted publish after hallucination breach suspension.
- **Escalation Triggers:** 8 triggers with named owners and SLAs — confidence <70% at publish (marketer, blocking) · brand compliance flag (Offer Catalog PM, 4hr) · deprecated feature reference (Engineering lead, 2hr, publish blocked) · PLG provisioning error (Engineering lead, immediate, 5min manual fallback) · new product line <10 analogues (Senior Marketing Manager, blocking) · override rate >40% on single offer type (Offer Catalog PM, 5-day audit) · golden dataset pass rate <88% (Offer Catalog PM, 15min page, 24hr audit) · hallucination rate >2% (Engineering lead + Offer Catalog PM, immediate suspension).
- **Audit Cadence:**  Real-time — latency · PLG provisioning · hallucination detection · brand compliance flags (Engineering lead). Weekly — golden dataset pass rate · HITL% · override rate by offer type (Offer Catalog PM). Monthly — conversion score accuracy vs. OGS actuals · shadow AI signal review · HITL% trajectory (Senior Manager PM). Quarterly — full governance review · model card update · Kill Switch 48-hour swap test (Senior Manager PM + Engineering lead).
- **Shadow AI Audit (user-side):**  6 workarounds · $18–20K/month fully loaded adjacent spend · dominant signal: capability gap. 4 build (new product line low-confidence UX · analytics dashboard · approval workflow · A/B experimentation) · 1 partner (Grammarly — inline copy refinement, covered under existing Salesforce enterprise agreement) · 1 change management (Google Docs/Confluence parallel template libraries — adoption problem, not a feature gap). Re-run quarterly.
- **Agent Boundaries:** - Offer Draft Generator (current Copilot) — can generate copy, score conversion, suggest fields, surface confidence signals. Cannot publish without marketer approval, access raw PII, modify published offers, or generate pricing/legal terms. Kill switch: Offer Catalog PM via feature flag. Conversion Scorer (current automated) — can score against OGS historical signal, surface confidence ranges. Cannot override marketer judgment or suppress uncertainty signals. Kill switch: Engineering lead via config, fallback to human review queue. Offer Sequencer (future FY27) — can sequence offer types, personalise CTA from progressive profile. Cannot publish to enterprise without human gate, modify pricing/legal terms, activate for new segments without PM sign-off, or operate without active Recursive Learning and Cross-Domain Transfer loops. Kill switch: Senior Manager PM via feature flag.
- **Regulatory Exposure:** GDPR/CCPA · EU AI Act Limited risk tier · Einstein Trust Layer (internal). Four controls: EU AI Act transparency — confidence scores and AI-generated labels surfaced in UI at all tiers · GDPR/CCPA data residency — OGS behavioral signals stored in Data Cloud per residency requirements, consent required for progressive profiling enrichment · GDPR/CCPA retention — offer interaction data 24 months, progressive profile data deleted within 30 days on request · Einstein Trust Layer zero retention — all model calls routed through internal abstraction layer, no customer data passed to external providers for training.
→ Details: [`05-the-guardrails/`](05-the-guardrails/)

---

## The Pitch (M6)

**How you get this funded, shipped, and adopted.**

- **Horizon 1 (Now):**  Three actions, no exceptions. Kill Switch abstraction wrapper shipped — without this, the board is approving a strategy with a single point of provider failure and a 3–6 week swap time. Correction capture instrumented in the AI Copilot authoring workflow — field-level delta logging between AI output and final published offer, tagged by segment, offer type, and product line. This is the root dependency for every compounding loop; nothing else starts without it. New product line low-confidence UX live — generates drafts explicitly labelled as thin-signal starting points, captures correction signal from day one on every new product launch. Ships as a UX change, not a new feature. These three actions are not roadmap items — they are prerequisites to the strategy being real.
- **Horizon 2 (Next):** Close the highest-cost workarounds and build the first evidence base. Analytics dashboard — closes $8K/month in manual Excel tracker overhead, FY27 theme confirmed by shadow usage, every OGS bulk export replaced by native conversion visibility. Approval workflow — closes the unapproved-publish risk (Air Canada path) and eliminates $3K/month in Slack and email coordination overhead; audit trail exists without manual process. Grammarly partner integration — 1 sprint, covered under existing Salesforce enterprise agreement, inline suggestion panel in AI Copilot draft view, accepted changes logged as correction signal. HITL% trajectory confirmed declining QoQ — this is the first proof point that H1 correction capture is compounding. If HITL% is not declining by end of H2, the correction loop is not working and a retraining decision is required before H3 is funded.
- **Horizon 3 (Bet):** The compounding bets — viable only after H1 correction capture is live and H2 HITL% trajectory is confirmed. Cross-Domain Transfer loop activated — high-converting SMB trial patterns surface as recommendations in adjacent offer categories; activation criteria: pattern learned in Offer Type A improves conversion score accuracy in Offer Type B by ≥3 points on the golden dataset. A/B Experimentation theme shipped — closes $3–5K/month in external tool spend, every variant test returns conversion signal to the recommendation layer instead of siloing it in Optimizely. Autonomous Offer Sequencer governance framework scoped — FY27 Killer SKU, cannot go live until Recursive Learning and Cross-Domain Transfer are declared Active by measurable criteria. Reviewed monthly. Kill criteria defined. Living strategy updated as evidence arrives.
- **Board Narrative:** **The case:** Offer Intelligence closes the loop between 18 months of Salesforce's proprietary B2B offer performance signal and the point of authoring — turning the Offer Catalog from a workflow platform into a compounding intelligence engine. The workflow moat is real today. The data moat is the FY27 bet: every correction captured, every offer published, every OGS conversion validated compounds into recommendations no external vendor can cold-start replicate. The correction window closes in 6–9 months when Mutiny ships a native Data Cloud connector. The Agentforce absorption risk materializes in 12–18 months if Offer Intelligence doesn't establish workflow depth first. The time to close the loop is this quarter — not after the next platform cycle. The math holds at 950x inference ROI and a 67% gross profit increase. The ask is sequencing and ownership — not budget.
- **Ask:** Three FY27 roadmap commitments with named owners and hard timelines. First: Recursive Learning build — 2 sprints from roadmap commitment, correction validation gate included as prerequisite, owned by Offer Catalog PM and Offer Service Engineering lead. Second: Data Cloud bridge — joint workstream between Offer Service Engineering and Data Cloud integration team scoped and owned before Q2; neither team can build this unilaterally, the joint ownership must be assigned in FY27 planning. Third: Kill Switch abstraction wrapper — this week, not this quarter; eval harness this month; multi-model routing with live fallback this quarter. Without these three commitments, the strategy is directionally correct but not executable.
- **Key Strategic Change:** Offer Intelligence entered M1 as a workflow platform with dormant data, a static model, and vulnerability scores reflecting moderate depth and latent advantage — Contextual Moat 2/5, Data Advantage 3/5, Platform Exposure 2/5. The scores have not changed. What has changed is the plan to change them. The strategy exits M6 with a defined moat trajectory (Workflow today → Data FY27), a correction loop sequenced to close before the competitive window does, a governance framework that can scale to autonomous sequencing, and kill criteria that force an honest decision if the bet isn't working. The product bet has shifted from "ship AI features" to "close the data loop before Agentforce makes the question irrelevant." Every horizon, every action, every metric in the living strategy is sequenced to serve that single objective. The freeze test must fail by Q4.

→ Details: [`06-the-pitch/`](06-the-pitch/)






---
