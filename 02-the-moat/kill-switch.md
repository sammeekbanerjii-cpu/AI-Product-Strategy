# Kill Switch Audit

## Vendor Dependency Assessment:

Kill Switch Audit:

CURRENT SETUP:

-> Primary provider: OpenAI
-> Integration depth: Direct API calls
-> Time to switch today: 3-6 weeks

STRESS TEST

-> If pricing doubles: The full cost increase absorbs directly into Offer Intelligence's operating costs with zero mitigation options. No routing fallback, no alternative provider configured, no budget lever available short of an engineering sprint. At Beta stage with Direct API calls, every offer draft generated, every conversion score computed, and every field validation run doubles in cost immediately. The business case for the AI Copilot becomes harder to defend before the flywheel has had time to prove value.

-> If ToS restricts use case: There is no plan today. Offer Intelligence processes proprietary Salesforce marketing data, OGS behavioral signals, and first-party B2B intent data. If OpenAI restricts processing of proprietary enterprise data or tightens data residency requirements, the AI layer becomes non-compliant immediately. With Direct API calls and no abstraction layer, forced migration to a compliant provider takes 3–6 weeks — meaning Offer Intelligence goes dark until the switch is complete.

-> Risk level (from integration): High risk

THREE ACTIONS

-> This week: Introduce the abstraction wrapper — route all OpenAI calls through a single model-agnostic interface. This alone compresses the switch timeline from weeks to days and is the foundation everything else builds on.
-> This month: Build the eval harness — define minimum quality criteria for offer copy and conversion score accuracy against OGS data. Validate a second provider (Anthropic or Azure OpenAI) against that bar so a swap decision can be made with confidence, not guesswork.
-> This quarter: Implement multi-model routing with at least one live fallback provider — tasks routed by cost, latency, and quality requirements. At this point, a provider shock becomes a configuration change, not an engineering emergency.


## Portability Score
-> Locked

