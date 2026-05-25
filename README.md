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

- **Product:** Offer Service
- **AI Value Archetype:** Copilot
- **Vulnerability Scores:** _(add: Moat _/5 · Data _/5 · Platform _/5)_
- **Top Risk:** -> The data advantage is latent, not active — if Offer Service doesn't close the loop between OGS behavioral signals and intelligent offer decisioning before Agentforce matures, it risks being absorbed into the AI platform layer rather than expanded as a standalone product.
- **Confidence:** M
- **Prototype:** https://preview--offer-muse-56.lovable.app/
- **Kill Criteria:** -> Marketers default to authoring offers manually and ignore AI recommendations after 60 days of availability -> AI-generated drafts show no statistically significant lift in conversion score versus manually authored offers after two campaign cycles -> Data Cloud signal quality p…

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

**Will this make money or bleed it?**

- **Gross Margin (current):**
- **Gross Margin (AI-adjusted):**
- **Pricing Model:**
- **Pricing Today → Tomorrow:**
- **Total AI COGS / unit:**
- **Cascading Strategy:** Triage: -> GPT-4o-mini / Claude Haiku — handles all simple classification, field validation, disclosure rendering, and template population. Fast, cheap, high-volume.; frontier: -> GPT-4.1 — reserved exclusively for enterprise offer draft generation and complex personalization where output quality directly impacts conversion rates.; ratio -> 80% small/mid · 20% frontier
- **Net Margin Shift:** - Δ margin %: −4%
- **Break-even at:**

→ Details: [`03-the-margin/`](03-the-margin/)

---

## The Contract (M4)

**Why users will trust a probabilistic system.**

- **Reliability Target:** 92% — weekly pass rate against full golden dataset. Defensible, measurable, shippable.
- **Golden Dataset:**
- **Confidence UX:** Offer Intelligence surfaces confidence explicitly at every tier — marketers see the score, the signal strength, and the source count before they publish. Uncertainty is never hidden.…
- **HITL Architecture:** **Trigger:** Confidence <70% OR safety flag (brand violation / factual accuracy failure / insufficient signal) → human review queue. PLG provisioning error → immediate human queue regardless of confidence score.
- **Failure Mode Coverage:**

→ Details: [`04-the-contract/`](04-the-contract/)

---

## The Guardrails (M5)

**What breaks when this scales — and what compounds.**

- **Compounding System:** | Loop | Input | Output | Compounds? | Status | |------|-------|--------|-----------|--------| | Recursive Learning | Marketer corrections to AI-generated offer drafts — delta between AI output and human-approved copy, t…
- **Governance Posture:** All AI-generated outputs from Offer Intelligence — offer draft generation, conversion score predictions, form field recommendations, progressive profiling logic, disclosure summaries, and CTA suggestions.…
- **Autonomy Boundaries:** Form field validation · disclosure summaries · CTA suggestions on standard templates · conversion scoring ≥90% confidence with no safety flags · progressive profiling field suppression for returning visitors — auto.…
- **Escalation Triggers:** 1. Confidence score <70% at publish time 2. Brand compliance flag: prohibited terms, competitive claims, unsubstantiated performance statements 3.…
- **Audit Cadence:** Real-time — timeLatency · PLG provisioning status · hallucination detection · brand compliance flags (Engineering lead, Offer Service).…
- **Shadow AI Audit (user-side):**
- **Agent Boundaries:** - Offer Draft Generator (current — Copilot) Can do: generate offer copy · predict conversion scores · suggest form fields · surface confidence signals.…
- **Regulatory Exposure:** GDPR / CCPA · EU AI Act · Salesforce Einstein Trust Layer (internal). Risk tier: limited. Controls: 1. EU AI Act (transparency) - Confidence scores and source citations surfaced in UI at all tiers · AI-generated drafts l…

→ Details: [`05-the-guardrails/`](05-the-guardrails/)

---

## The Pitch (M6)

**How you get this funded, shipped, and adopted.**

- **Horizon 1 (Now):**
- **Horizon 2 (Next):**
- **Horizon 3 (Bet):**
- **Board Narrative:** **The case:**
- **Ask:** ## M1 Baseline vs. Now
- **Key Strategic Change:**

→ Details: [`06-the-pitch/`](06-the-pitch/)






---
