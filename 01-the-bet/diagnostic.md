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
Workflow Depth — Moderate, but embedded in critical paths.

Offer Service is woven into Salesforce's marketing infrastructure:
-> Offer authoring, field sets, form templates, staging, and publishing are centralized in the Offer Catalog
-> OGS handles form submissions, routes web activity to Data Cloud and downstream systems, and tracks user interactions
-> Progressive profiling, write-once-reuse, and synchronous PLG trial provisioning are embedded in live acquisition workflows

The platform is transitioning from project-based delivery to a product motion — meaning some workflows are newer and not yet fully habituated across all Salesforce properties.

Switching Cost — Medium, with meaningful exceptions.

What makes switching painful:
-> Offer data, form templates, and disclosure libraries are centralized — migration requires significant re-authoring effort
-> OGS is the write path for web activity into Data Cloud — replacing it breaks downstream analytics and personalization
-> PLG trial provisioning is a synchronous integration — disrupting it directly impacts acquisition

 What makes switching easier than you'd want:
 -> The offer content (titles, copy, CTAs) lives mostly in authoring tools — arguably portable.
 -> If a competitor showed up with better form UX and a Data Cloud connector, a determined team could migrate in weeks, not months — especially if Offer Catalog hasn't yet become the single source of truth for all offer data everywhere.

 Would users leave in a weekend?

 Probably not in a weekend — OGS's data flow integrations and the Offer Catalog's embedded configuration create real friction. But in a quarter? That's a real risk if:
 -> The Offer Catalog hasn't achieved true "write-once, reuse everywhere" adoption across all Salesforce properties
 -> Downstream Data Cloud integrations is still pending

**Named attacker (from partner challenge):**
For Contextual Moat specifically, the attacker needs to threaten workflow replaceability — someone who could show up with comparable capabilities plus a Data Cloud connector and make migration feel achievable.

Two credible options depending on your partner's framing:

Internal threat — Salesforce Marketing Cloud
-> The most politically credible attacker. Leadership already owns the license, the dog-food argument writes itself, and Marketing Cloud's form and offer management capabilities overlap meaningfully with Offer Catalog. The threat isn't technical superiority — it's executive convenience.

External threat — Mutiny
-> AI-native B2B website personalization platform purpose-built for exactly this use case. If Mutiny ships a native Data Cloud connector, the switching cost argument weakens significantly — the OGS data flow dependency, which is currently Offer Service's strongest lock-in, becomes portable.

---

### Data Advantage — _3_/5
*Proprietary signal that compounds with usage. What do you see that OpenAI doesn't?*

What Data Offer Service Actually Generates:
-> Form submission data and progressive profile enrichment across Salesforce web properties
-> Offer interaction signals — clicks, completions, abandonment — mapped to visitor segments
-> PLG trial conversion data — what offer sequences drive trial initiation
-> Web activity routed into Data Cloud, feeding downstream personalization and analytics

What Offer Service sees that OpenAI doesn't:
-> First-party B2B intent signals at scale. The combination of offer performance data, progressive profiling, and PLG conversion paths — anchored to Salesforce's own web traffic — is not replicable by any external model.

**Score rationale:**

Why 3/5 and not higher:
-> The data advantage is real but largely latent. OGS feeds Data Cloud, but the loop isn't closed — offer selection and sequencing aren't yet informed by what the data reveals. Until Offer Service actively uses its own signal to drive smarter decisions, it's a pipeline, not a compounding moat. The Analytics theme in the FY27 roadmap is the right vehicle to close this gap.

**Named attacker (from partner challenge):**

Named attacker:(Internal)
-> Salesforce Einstein / Agentforce — if the AI platform team builds offer optimization directly on top of Data Cloud, they inherit the signal without needing Offer Service as the intelligence layer.

Named attacker:(External)
-> Mutiny is an AI-native B2B personalization platform that captures first-party intent signals, builds progressive audience profiles, and optimizes offer conversion — directly overlapping with what Offer Service generates. If Mutiny ships a native Data Cloud connector, the proprietary signal argument weakens considerably.

---

### Platform Exposure — _2_/5
*Encroachment risk × pivot speed. If Apple/Google/OpenAI ships your hero feature native — then what?*

**Score rationale:**
External AI players — OpenAI, Google, Microsoft — cannot natively ship a replacement for a platform embedded in Salesforce's internal web infrastructure and Data Cloud. That limits traditional platform encroachment risk significantly.

The credible risk is internal:
-> Agentforce could absorb offer orchestration as an AI-native capability
-> A Marketing Cloud consolidation mandate remains a standing executive option

Pivot speed, however, is slow. The Data Cloud write path, PLG provisioning dependency, and three-pillar ownership mean any platform shift requires deep organizational alignment — not a unilateral product decision.

**Named attacker (from partner challenge):**

Named attacker:(Internal): 
-> Agentforce — the most credible encroachment vector. As AI-native orchestration matures, the case for a standalone offer platform weakens if Agentforce can serve offers dynamically from Data Cloud without a separate catalog layer.

Named attacker:(External)
-> Adobe Experience Cloud - Adobe's combination of AEM, Adobe Target, and Real-Time CDP replicates the Catalog + OFX + OGS stack in a single enterprise suite. The encroachment scenario: a Salesforce executive benchmarks internal platform costs against an Adobe enterprise agreement and frames consolidation as a cost efficiency play — not a product decision.

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
