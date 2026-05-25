# Three-Horizon Roadmap & Board Pitch

## Roadmap

### Horizon 1 — Now (0-3 months)
*Quick wins. Ship with existing capabilities.*




| Initiative | Metric | Confidence |
|-----------|--------|-----------|
|Correction capture pipeline — instrument field-level delta logging between AI output and final published offer, tagged by segment, offer type, and product line, routed into model layer | Correction signal flowing into model layer by end of sprint 2 · HITL% baseline established | M |
|Kill switch abstraction wrapper — decouple direct OpenAI API calls behind a provider abstraction layer | Provider swap time reduced from 3–6 weeks to 48-hour target | H | 
|New product line low-confidence UX — generate drafts labelled as thin-signal starting points, human review mandatory, correction signal captured from day one | 100% of new product line offers trigger human review flag · zero thin-signal offers published without review | H | 
|Golden dataset expanded to 50 cases — PM-led, no engineering dependency, priority on new adversarial patterns identified in shadow audit | Weekly pass rate measurable against defensible baseline · judge calibration stable | H |

### Horizon 2 — Next (3-9 months)
*Bets. Requires new capabilities or integrations.*

| Initiative | Metric | Confidence |
|-----------|--------|-----------|
| Analytics dashboard — native OGS conversion visibility replacing manual Excel tracker workflows| $8K/month Excel overhead eliminated · offer conversion data accessible without OGS bulk export | M |
| Approval workflow — native approval routing replacing Slack and email chains, with full audit trail | % of offers published via native approval path vs. Slack chains · unapproved publish incidents = 0 | H | 
| Grammarly partner integration — inline copy refinement surfaced after AI draft generation, accepted changes logged as correction signal| Override rate on headline and CTA fields declining MoM · integration live within 1 sprint of enterprise agreement confirmation | H | 
| HITL% trajectory confirmed declining QoQ — first proof point that H1 correction capture is compounding| HITL% at or below 35% by end of H2 · if rising, retraining decision documented within 5 business days | M |

### Horizon 3 — Bet (9-18 months)
*Moonshots. High uncertainty, high potential.*

| Initiative | Metric | Confidence |
|-----------|--------|-----------|
|Cross-Domain Transfer loop activated — high-converting patterns in one offer category surface as recommendations in adjacent categories | Pattern learned in Offer Type A improves conversion score accuracy in Offer Type B by ≥3 points on golden dataset | L |
|A/B Experimentation theme — native variant testing replacing Optimizely and external tools, conversion signal returned to the recommendation layer|$3–5K/month external tool spend eliminated · variant conversion signal feeding recommendation layer, not siloed externally | M |
|Autonomous Offer Sequencer — sequences offer types based on visitor behaviour, personalises CTA from progressive profile, enterprise gate active | HITL% for sequenced offers ≤20% · zero enterprise account publishes without human gate · Recursive Learning and Cross-Domain Transfer loops declared Active before sequencer goes live | L |

## Board Pitch

**Thesis (1 sentence):**
- Offer Intelligence turns 18 months of Salesforce's proprietary B2B offer performance signal into a compounding data moat — closing the loop between OGS behavioral data and intelligent offer decisioning before Agentforce makes the question irrelevant.

**The case:**
1. Why now: Mutiny ships a native Data Cloud connector in 6–9 months — if correction capture is not live before that, Mutiny starts the compounding loop on Salesforce's own proprietary signal. Agentforce absorbs offer orchestration in 12–18 months if Offer Intelligence doesn't establish workflow depth first. The window to start compounding before a competitor does closes this quarter — not next roadmap cycle.
2. What's defensible: The workflow moat is real today — PLG provisioning is synchronous and acquisition-critical, OGS is the write path for web activity into Data Cloud, and the Offer Catalog's centralized configuration creates switching friction measured in quarters. The data moat is the FY27 bet: 18 months of first-party B2B intent signal no external vendor can replicate, plus a correction loop that compounds quality with every published offer. Mutiny can replicate the Data Cloud connector. It cannot replicate the signal history plus a correction loop that has been running since launch.
3. The economics: 950x inference ROI ($133 revenue per user vs. $0.14 AI COGS). Gross profit grows 67% under hybrid pricing. AI COGS are fully covered at 1 published offer per user per month. A 3× provider price spike moves gross margin by 0.2 points. The unit economics are structurally immune to cost volatility at this ratio.

**The risks:**
1. Trust / failure modes: The core conversion lift hypothesis — that AI-generated offers outperform manually authored offers — has not been validated by a controlled test. One controlled A/B test closes this gap in H1. The golden dataset has 12 cases at launch; 50 is the H1 target. Both are gaps today and both are closable before the board reconvenes.
2. Scale / governance: Correction capture does not exist. Zero of three compounding loops are active. The freeze test currently passes — the product does not get smarter when frozen. HITL% declining QoQ is the proof the loops are working; that trajectory has not yet been established. The Data Cloud bridge requires joint ownership between two engineering teams with no committed workstream today.
3. Competitive: Agentforce ships native offer orchestration with Data Cloud integration before Offer Intelligence closes the data loop. This is the kill criterion that cannot be defended by engineering alone — it requires an explicit organizational decision that Offer Intelligence is the AI layer for offer decisioning, not a capability to be absorbed by the platform team. That decision needs to be made in this room.

**The ask:**
- Three FY27 roadmap commitments with named owners and hard timelines: (1) Correction capture pipeline — 2 sprints from today, owned by Offer Catalog PM and Offer Service Engineering lead, correction validation gate included as prerequisite; (2) Data Cloud bridge — joint workstream between Offer Service Engineering and Data Cloud integration team scoped and owned before Q2, neither team can build this unilaterally; (3) Kill switch abstraction wrapper — this week, eval harness this month, multi-model routing this quarter.

## M1 Baseline vs. Now
*Your 3-sentence AI strategy from Module 1 vs. what you'd say now:*

**M1 baseline:**: Offer Service is an internal marketing platform with AI potential. The product bet is to surface historical offer performance data at the point of authoring so marketing managers can publish better-converting offers faster — closing a data loop that currently sits dormant in Data Cloud.

**Now:**: Offer Intelligence is a compounding intelligence engine — Workflow moat today, Data moat FY27, 950x inference ROI, 67% gross profit growth. Vulnerability scores unchanged (Contextual Moat 2/5 · Data Advantage 3/5 · Platform Exposure 2/5) — what changed is the plan to move them. Specific, sequenced, owned, with kill criteria that force an honest decision if the bet isn't working. The strategy is a bet on sequencing, not potential.


**AI Evaluation section:**

Bet Validation — Score: 3/5

Strengths: Kill criteria are specific and falsifiable — marketers ignoring AI after 60 days, no conversion lift after two campaign cycles, HITL% rising for two consecutive quarters. These are measurable, not narrative. The shadow AI audit provides genuine demand signal — $18–20K/month in workarounds is user evidence, not intuition. The urgency case (Mutiny in 6–9 months, Agentforce in 12–18) is named and time-bounded.
Gaps: The core hypothesis — AI-generated offer drafts produce statistically significant conversion lift over manually authored offers — has not been validated by a single controlled test. The bet is built on platform logic and signal availability, not on demonstrated output quality. There is no user interview data cited, no early adopter cohort, no A/B result. The prototype exists but there is no evidence of it being tested with real marketers on real offers.
Recommendation: Run one controlled test before H2 ends — two identical campaign briefs, one AI-assisted, one manual, same segment, same channel, same week. A single positive result changes the confidence rating from M to H and removes the biggest board objection. Without this, every downstream claim about conversion lift is an assumption.


Capability Assessment — Score: 3/5

Strengths: The infrastructure foundation is real — OGS data pipeline, Data Cloud integration, Offer Catalog as centralized authoring layer, and PLG provisioning are all in production. The cascade architecture is designed. The abstraction layer, eval harness, and multi-model routing have a sequenced build plan with this-week/this-month/this-quarter timelines.
Gaps: The correction capture pipeline — the root dependency for every compounding loop — does not exist. The kill switch is locked at 3–6 weeks swap time. The Data Cloud bridge (the return path from signal storage to intelligent decisioning) has no committed workstream and requires joint ownership between two teams who have not yet been formally tasked. MLOps maturity is not assessed — there is no mention of model versioning, rollback capability, or training infrastructure.
Recommendation: Before committing to H2 and H3 timelines, get a formal joint scoping session between Offer Service Engineering and the Data Cloud integration team on the calendar this sprint. The Data Cloud bridge cannot be built unilaterally and currently has no owner. That is an execution blocker disguised as a roadmap item.


Impact Analysis — Score: 3/5

Strengths: The financial impact is quantified — +67% gross profit, $18–20K/month shadow AI spend absorbed, 950x inference ROI. The compounding story is structurally sound: if the three loops activate in sequence, impact accelerates rather than plateaus. The pricing redesign creates a direct connection between offer volume and revenue, so growth compounds with adoption.
Gaps: All impact projections assume adoption — that marketers will publish AI-assisted offers at 10/month average. There is no adoption curve modeled, no baseline utilization rate cited, and no evidence from the prototype of actual usage frequency. The opportunity cost of this investment vs. alternative Offer Service priorities is not addressed. If the correction loop takes two quarters to show results, what is the strategy earning in the interim?
Recommendation: Model a conservative adoption scenario — 3 offers/user/month in the first two quarters instead of 10 — and stress-test the gross profit claim. If the case still holds at 3 offers/month, lead with that number to the board. It is more defensible than a projection built on full-utilization assumptions.


Defensibility Check — Score: 2/5

Strengths: External platform encroachment is genuinely low — OpenAI, Google, and Microsoft cannot natively replicate a platform embedded in Salesforce's internal web infrastructure and Data Cloud write path. The internal switching cost is real: PLG provisioning is synchronous and acquisition-critical, OGS is the write path for web activity, and the Offer Catalog's disclosure libraries and form configuration create migration friction measured in quarters.
Gaps: The data flywheel scores 6/20 and zero loops are compounding. This is the most important number in the strategy and it is the weakest. The freeze test currently passes — a product that doesn't get smarter when frozen is not a compounding moat. The workflow moat scores 2/5 because write-once-reuse-everywhere adoption is incomplete. The data moat scores 3/5 because the return path doesn't exist. A competitor that closes the correction loop first wins — and Mutiny is 6–9 months from the starting line.
Recommendation: The defensibility score will not improve until the flywheel moves. Treat the correction capture pipeline as a security issue, not a feature — it is the single action that determines whether the moat is real or theoretical. Reprioritize everything else in H1 below it.


Pricing Alignment — Score: 4/5

Strengths: The hybrid model aligns revenue to the value event — a published offer — not to access. The labor savings test is rigorous: $150–250 saved per offer, $25 captured, 10–15% value share. The power user economics are exceptional: at 100 offers/month, revenue is $2,550 vs. $1.25 COGS. Provider cost resilience is strong — 950x inference ROI means a 3× price spike moves margin by 0.2 points. The cascade architecture protects margin structurally, not through pricing.
Gaps: This is an internal platform — the "pricing" decision is an internal budget allocation, not a market pricing decision. The willingness-to-pay dynamic is different: the buyer is a Salesforce business unit with internal chargeback mechanics, not a paying external customer. The assumption that marketing teams will accept a per-outcome charge on top of a seat fee requires internal budget owner alignment that is not addressed. There is also no pricing model for the Killer SKU (Offer Sequencer) beyond "add-on, premium tier."
Recommendation: Identify the internal budget owner — who approves the chargeback for the $25/offer outcome fee — and validate the pricing model with that stakeholder before the board pitch. A pricing model that the board approves but the internal buyer rejects is not a pricing model.


Trust & Reliability — Score: 4/5

Strengths: The reliability contract is specific and defensible — 92% golden dataset pass rate, hallucination <1%, TTFT ≤1.5s, PLG provisioning ≤2s, drift <0.5%/4 weeks. All metrics have named owners, alert thresholds, and named consequences. The confidence UX is well-designed — three tiers, uncertainty never hidden, reasoning panel visible. The HITL architecture correctly places Senior Marketing Manager as reviewer, not rotating PM. The adversarial dataset covers the six highest-stakes failure modes with binary testable conditions.
Gaps: The golden dataset has 12 cases. For a system publishing offers to Salesforce's web properties at scale, 12 cases is a thin safety net. The path to 150 cases has no timeline or owner. The LLM-as-a-judge calibration protocol is defined but there is no stated fallback if the judge degrades — who catches judge drift?
Recommendation: Assign a named owner and a specific date to reach 50 golden dataset cases — not 150, just 50 — as the H2 gate condition. 12 cases is sufficient for launch; 12 cases at the end of H2 is a governance gap.


Governance & Scale — Score: 4/5

Strengths: The governance framework is comprehensive and unusually specific for a strategy document at this stage — 8 escalation triggers with named owners and SLAs, four-cadence audit structure, three-agent topology with kill switches, incident response with a 5-step sequence and named timelines. The shadow AI audit is properly executed — signal sources named, fully loaded spend calculated, each workaround has a sequenced decision. The autonomy boundaries are specific and named rather than circular.
Gaps: The correction capture pipeline not existing means the feedback loop — the mechanism by which governance improves over time — is entirely absent. Governance without a learning loop is static compliance, not compounding trust. At 10x scale, the Senior Marketing Manager reviewer becomes a bottleneck if HITL% does not decline as projected. There is no stated capacity plan for the review queue if adoption exceeds forecast.
Recommendation: Add a HITL capacity trigger to the governance policy — if HITL% does not decline below 35% by end of H2, a dedicated review team must be scoped. A single Senior Marketing Manager reviewer at 10x volume without a declining HITL% is an unmodeled operational risk.


Gap Identification — Score: 3/5

Strengths: The strategy correctly identifies its own weakest component — the moat — and names the correction loop as the root dependency. The freeze test framing is honest and strategically sharp. The untested assumptions are partially surfaced through the kill criteria. The vulnerability scores are self-critical rather than inflated.
Gaps: The single question a skeptical board member will ask that cannot be answered today: "Show me one offer where AI-generated copy outperformed manually authored copy in a controlled test." There is no answer. The conversion lift claim is the entire commercial case and it is entirely unvalidated. Additionally, the organizational change management question — will marketers actually adopt a Copilot workflow or route around it — is addressed only in the shadow AI audit, not as a standalone adoption risk.
Recommendation: Before the board pitch, run the controlled conversion test described in Bet Validation. One data point converts the pitch from "we believe AI will lift conversion" to "in a controlled test, AI-assisted offers outperformed manual offers by X%." That single result changes the board conversation entirely.


Overall Score: 3.3/5
A strategy with strong structural integrity and unusually honest self-assessment — the vulnerability scores, freeze test framing, and kill criteria reflect genuine analytical rigor. The governance and pricing sections are board-ready. The fatal gap is that the core commercial hypothesis is unvalidated and the compounding mechanism that justifies the entire moat story does not yet exist. This is a well-designed bet on an unproven outcome. That is not disqualifying — it is the nature of early AI product strategy. But the board will see it.

Biggest Risk: The correction loop is the root dependency for the data moat, the compounding system, and the defensibility case — and it has never been built. Every other component of the strategy assumes it will be. If correction capture ships late, is deprioritized, or produces biased signal without the validation gate, the entire moat story collapses. Mutiny does not need to be better — it only needs to start compounding before Offer Intelligence does.

Top 3 Actions:

Instrument correction capture this sprint — not this quarter, this sprint. It is a root dependency disguised as a roadmap item. Everything downstream — the data moat, the compounding loops, the HITL% trajectory, the board case — depends on this pipeline existing. Delay compounds against you daily.
Run one controlled A/B conversion test before the board pitch. AI-assisted offer vs. manually authored offer, same segment, same channel, same week. A single positive result transforms the pitch from conviction to evidence. Without it, the conversion lift claim — which is the entire commercial case — is an assumption the board will challenge and cannot be answered.
Get the Data Cloud bridge joint scoping session on the calendar this sprint with named owners from both teams. This workstream cannot be built unilaterally, has no committed owner today, and sits on the critical path between latent data advantage (3/5) and active data moat (target 4–5/5). Every week it lacks an owner is a week the FY27 roadmap window narrows.

-----
