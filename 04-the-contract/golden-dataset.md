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

**Adversarial rows included:** __
**Coverage gaps identified by partner:**

## Confidence UX Design

**Approach:** show uncertainty / tiered confidence / human-in-loop trigger

**High confidence (>90%):**
**Medium confidence (70-90%):**
**Low confidence (<70%):**

**User control surface:**

## Reliability Contract

| Metric | Target | Measurement | Alert Threshold |
|--------|--------|-------------|-----------------|
| Accuracy | | | |
| Hallucination rate | | | |
| Latency (p95) | | | |
| Drift velocity | | | |

## HITL Architecture
<!-- When does a human step in? What's the escalation path? -->

## Red-Team Findings
*What failure mode did your partner find that you missed?*
