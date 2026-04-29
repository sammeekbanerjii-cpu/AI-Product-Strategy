# Three-Axis Vulnerability Diagnostic

## Product
<Offer Service is Salesforce's internal digital marketing platform for managing, publishing, and orchestrating marketing offers across Salesforce's web properties.>

**Product:** Offer Service
**Your Role:** Senior Manager - Product Management

---

## Scores

### Contextual Moat — _2_/5
*Workflow depth × switching cost. Would users leave in a weekend if a competitor showed up?*

**Score rationale:**
 Workflow Depth — Moderate, but growing.
 
 Offer Service is getting deeper in the workflow:
 -> Offer authoring, field sets, form templates, staging, and publishing are all centralized in the Offer Catalog
 -> OGS handles form submissions, routes data to Data Cloud and downstream systems, and tracks user interactions
 -> Progressive profiling, write-once-reuse, and PLG trial provisioning are now embedded in marketing workflows

 The platform is still maturing from a project-based delivery to a product motion, which means some workflows are newer and not yet deeply habituated.

 Switching Cost — Medium, with a key asterisk

 What makes switching painful:
 -> Offer data, form templates, and disclosure libraries are centralized. Migrating these would require significant re-authoring.
 -> OGS is the write path for web activity into Data Cloud — replacing it breaks downstream analytics and personalization.
 -> PLG trial provisioning is a synchronous integration — it's hard to rip out without disrupting acquisition flows.

 What makes switching easier than you'd want:
 -> The offer content (titles, copy, CTAs) lives mostly in authoring tools — arguably portable.
 -> If a competitor showed up with better form UX and a Data Cloud connector, a determined team could migrate in weeks, not months — especially if Offer Catalog hasn't yet become the single source of truth for all offer data everywhere.

 Would users leave in a weekend?

 Probably not in a weekend — OGS's data flow integrations and the Offer Catalog's embedded configuration create real friction. But in a quarter? That's a real risk if:
 -> The Offer Catalog hasn't achieved true "write-once, reuse everywhere" adoption across all Salesforce properties
 -> Downstream Data Cloud integrations is still pending

**Named attacker (from partner challenge):**

---

### Data Advantage — _3_/5
*Proprietary signal that compounds with usage. What do you see that OpenAI doesn't?*

**Score rationale:**

What Data Offer Service Actually Generate:



**Named attacker (from partner challenge):**

---

### Platform Exposure — _2_/5
*Encroachment risk × pivot speed. If Apple/Google/OpenAI ships your hero feature native — then what?*

**Score rationale:**

**Named attacker (from partner challenge):**
-> HubSpot
---

## Killer Memo

> You run AI at **[OpenAI / Google / Apple]**. Your OKR: make this product irrelevant.
>
> **3-sentence memo:**
>
> 1. Attack:
> 2. Wedge:
> 3. Why users switch:

---

## Top Vulnerability
<!-- One line: what's the single biggest strategic risk? -->

## Confidence Level
<!-- H / M / L — how confident are you in this bet after the diagnostic? -->
