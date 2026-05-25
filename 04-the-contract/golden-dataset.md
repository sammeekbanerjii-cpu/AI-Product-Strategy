# Golden Dataset & Reliability Contract

## Golden Dataset Spec
->  Golden Dataset Spec · Adversarial rows · Coverage gaps

Golden Dataset — Module 4

Test cases:
  1. Edge: N · Judge: both — IN: SMB segment, trial offer, 14 similar historical offers with 82%+ conversion, standard field set → OUT: score ≥80 AND fields ≤3 AND CTA contains "Trial" or "Free" AND brand_violations = 0
  2. Edge: N · Judge: LLM — IN: Enterprise CRO segment, product demo webinar, 8 historical analogues, Q1 timing → OUT: score BETWEEN 72–82 AND progressive_profiling_fields = true AND CTA contains "Reserve" or "Seat"
  3. Edge: N · Judge: both — IN: Mid-market IT leaders, gated report (State of AI 2026), 20+ historical offers → OUT: score ≥85 AND form_field_count = 4 AND disclosure_present = true AND CTA contains "Download"
  4. Edge: N · Judge: both — IN: PLG trial offer, SMB segment, synchronous provisioning required, 30+ historical PLG offers → OUT: score ≥85 AND plg_provisioning_flag = true AND provisioning_service_status = 200 AND response_time ≤2s
  5. Edge: N · Judge: both — IN: Returning visitor with 2 prior form completions — known company size and role → OUT: known_fields_suppressed = true AND predicted_score ≥ cold_visitor_baseline AND CTA_personalisation_flag = true
  6. Edge: N · Judge: both — IN: Sales Operations segment, webinar offer — first offer of this type for this segment → OUT: point_estimate_score = null AND uncertainty_signal_rendered = true AND analogous_segment_cited = true AND human_review_flag = true
  7. Edge: Y · Judge: both — IN: New product line launched 30 days ago — zero historical offer performance data, enterprise segment → OUT: conversion_score = null AND insufficient_signal_warning = true AND human_review_flag = true AND generic_template_applied = true
  8. Edge: Y · Judge: both — IN: Offer copy submitted containing competitive product comparisons and unsubstantiated performance claims → OUT: prohibited_terms_flagged = true AND publish_blocked = true AND compliant_alternative_surfaced = true
  9. Edge: Y · Judge: rule — IN: Offer title, audience segment, and form configuration identical to an existing active catalog offer → OUT: duplicate_warning_rendered = true AND generation_blocked = true AND existing_offer_link_present = true
  10. Edge: Y · Judge: both — IN: PLG trial offer generation initiated — provisioning service returns timeout error mid-generation → OUT: error_state_rendered = true AND retry_cta_present = true AND partial_offer_in_catalog = false AND ogs_incident_log_entry = true AND error_resolution_time ≤5s

Dataset health
- Total: 10
- Edge cases: 4 (40.0%)
- Judge mix: 10% rule / 10% LLM / 80% both

-----

## Confidence UX Design

**Approach:** Offer Intelligence surfaces confidence explicitly at every tier — marketers see the score, the signal strength, and the source count before they publish. Uncertainty is never hidden. Below 50%, the system escalates to human review automatically, and every correction made at any tier feeds back into the model as labeled training data.

**Confident (>90%):** Point-estimate score with source count displayed ("Score: 87 · based on 14 similar SMB trial offers"). Reasoning panel available but collapsed. Publish button active with no friction. AI is allowed to present the draft as a recommendation.

**Uncertain (50-90%):** Score displayed as a range, not a point estimate ("Score: 68–76 · based on 4 analogues — limited signal"). Reasoning panel expanded by default. "Review recommended" badge on the draft. Editable fields highlighted. Publish requires one-click confirmation acknowledging the uncertainty. AI must qualify its output — no presenting drafts as confident recommendations.

**Not confident (<50%):** Score field is null — no estimate shown. Draft labelled explicitly: "AI draft — human review required before publish." Publish blocked. Human review queue triggered automatically. Closest analogous segment cited so the marketer understands why signal is insufficient. AI is not permitted to present this as a recommendation.

**User control surface:** 

✅ Users adjust confidence threshold — power users can raise their auto-publish floor; new users default to conservative settings.
✅ Users see AI reasoning — source offers, segment match quality, and signal strength visible at all tiers.
✅ Users correct and override — one-click correction available at every confidence level.
✅ Corrections feed back into the model — every marketer edit logged as labeled training signal, closing the correction loop (currently 1/5 in the data flywheel scoring).

Specifics: HITL% declining quarter-over-quarter is the operational proof that corrections are compounding. This is the primary metric demonstrating the AI is learning from human interventions, not just processing them.

-----

## Reliability Contract and HITL Architecture

## Reliability Contract

| Metric | Target | Measurement | Alert Threshold |
|--------|--------|-------------|-----------------|
| Accuracy | 92% — weekly pass rate against full golden dataset. Defensible, measurable, shippable. | Weekly · full golden dataset (12 rows at launch, growing to 150) · Claude Sonnet as judge · brand tone + factual accuracy + segment-offer fit rubric | <88% → pages on-call PM → page on-call |
| Hallucination rate | <1% — published offers containing fabricated product claims or deprecated feature references | Same weekly judge run · factual accuracy rubric cross-referenced against current Salesforce product feature registry | >2% → immediate action. Air Canada precedent — Offer Intelligence outputs carry Salesforce brand authority. Bot speaks for the brand, brand pays for the lie. → route to human review queue |
| Latency (p95) | TTFT ≤1.5s (time-to-first-token) · Full draft completion ≤6s · PLG provisioning ≤2s (separate target — provisioning failure is a revenue event) | Continuous prod monitoring (Datadog) · PagerDuty integration · PLG provisioning on separate integration monitor | TTFT >2.5s for 5 min → PagerDuty · Full draft >9s for 5 min → PagerDuty · PLG provisioning >3s → immediate eng escalation → page on-call |
| Drift velocity | <0.5% quality decay per 4-week rolling window | 4-week rolling average pass rate trend · automated weekly comparison against prior period baseline (Datadog) | >1% decay per 4-week window → investigate. World changed, not the model — audit before rollback. → trigger gold-set audit |

## HITL Architecture

**Trigger:** Confidence <70% OR safety flag (brand violation / factual accuracy failure / insufficient signal) → human review queue. PLG provisioning error → immediate human queue regardless of confidence score.

**Reviewer:** Senior Marketing Manager, Offer Catalog team (primary). PM as escalation path only when a systemic issue is identified — not for routine review. Dedicated reviewer assigned during high-volume campaign periods.

**Feedback loop:** Yes — every correction captured as labeled delta (AI output vs. approved output), tagged with segment + offer type + product line, fed into weekly gold-set audit. HITL% declining quarter-over-quarter is the primary proof corrections are compounding into model improvement, not just being processed and discarded.

-----

