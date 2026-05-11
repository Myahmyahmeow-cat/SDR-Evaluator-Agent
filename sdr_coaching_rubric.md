# DealDrop SDR Cold Call Coaching Rubric — v1.2 (Lit-Grounded)

**Note on this version.** This document merges the rubric design (v1.1) with the academic literature that grounds it. Sections marked **"Academic grounding"** explicitly identify which research informs each design choice. The rubric structure is unchanged from v1.1; the literature is added so connections are visible without flipping between documents.

A few citations are flagged as **[verify]** where the conference-internet conditions limited my ability to confirm exact authorship/year. These are still useful as direction-pointers but should be confirmed before quoting verbatim in the writeup.

---

## Design Philosophy

This rubric measures cognitive and execution behaviors that are causally linked to DealDrop-specific merchant outcomes (deal-fit, campaign performance, merchant retention) — not generic sales affect.

- **Four axes** measure the rep's *cognitive engagement* with the merchant's economic reality
- **Three axes** measure *execution* of the call as a structured interaction
- **Diagnostic outputs** capture paralinguistic signal as descriptive metrics, not scored skills
- **Disposition metadata** conditions which axes apply per call

**Three diagnostic principles every axis must pass:**
1. *Vertical-swap test* — could not be lifted unchanged into a different sales context
2. *Inter-rater reliability* — three coaches scoring the same call should land within 1 point
3. *Outcome attribution* — traceable line from skill to a measurable downstream outcome

---

### Academic foundations of the overall framework

The rubric draws on three converging research traditions. Naming them upfront because they shape every axis below.

**1. Adaptive Selling (Weitz lineage).** The dominant academic framework for what makes salespeople effective. Origin: **Weitz (1981), "Effectiveness in Sales Interactions: A Contingency Framework,"** *Journal of Marketing* 45(1). Key extension: **Weitz, Sujan & Sujan (1986), "Knowledge, Motivation, and Adaptive Behavior: A Framework for Improving Selling Effectiveness,"** *Journal of Marketing* 50(4) — defines adaptive selling as altering sales behaviors during or across customer interactions based on perceived information about the selling situation. Validated measurement instrument: **Spiro & Weitz (1990), "Adaptive Selling: Conceptualization, Measurement, and Nomological Validity,"** *Journal of Marketing Research* 27(1) — develops the **ADAPTS scale** (16 items, five facets). Synthesis: a 2025 systematic literature review in *Journal of the Academy of Marketing Science* identifies four mediating mechanisms (job/self × confidence/proficiency) **[verify exact authorship]**.

**2. Customer-Oriented Selling (Saxe & Weitz).** Distinct from adaptive selling. **Saxe & Weitz (1982), "The SOCO Scale: A Measure of the Customer Orientation of Salespeople,"** *Journal of Marketing Research* 19(3) — develops the SOCO scale measuring whether the rep acts in the customer's interest vs. the firm's short-term interest. A 2022 paper in *Sustainability* (PMC9774540) sharpens the distinction: adaptive selling can be opportunistic; customer-oriented selling is fundamentally other-regarding.

**3. ML/NLP on sales conversations (recent).** Three reference points. **Nandakishor (2025), "SalesRLAgent,"** arXiv:2503.23303 — RL framework trained on GPT-4o-generated synthetic data, reports 96.7% conversion-prediction accuracy. **"Sell More, Play Less: Benchmarking LLM Realistic Selling Skill,"** arXiv:2604.07054 — develops the SalesLLM benchmark, achieves Pearson r = 0.98 correlation with expert human ratings. **"Learning When to Quit in Sales Conversations,"** arXiv:2511.01181 — imitation learning on 11,627 real outbound sales calls, reports 36% time savings while retaining 130/132 sales.

**Why this combination.** Adaptive selling research grounds the *cognitive* axes (the rep's ability to read and respond to context). Customer-oriented selling research grounds the *risk-acknowledgment* axis (acting in the merchant's interest). Recent ML literature grounds the *methodology* (synthetic data, expert-correlation evaluation) and the *system architecture* (sequential decision modeling, real-time scoring).

---

## Quick Reference

| # | Axis | Type | Weight | Predicts | Primary literature anchor |
|---|------|------|--------|----------|---------------------------|
| 1 | Merchant-Economic Modeling | Cognitive | 1.5 | Merchant retention | SOCO (Saxe & Weitz 1982); SPIN Need-payoff (Rackham 1988) |
| 2 | Contextual Responsiveness | Cognitive | 1.25 | Call quality variance | ADAPTS scale (Spiro & Weitz 1990); interpersonal mentalizing (Current Psychology 2024) |
| 3 | Risk Acknowledgment | Cognitive | 1.0 | Trust / launch confidence | Customer-oriented selling (Saxe & Weitz 1982; PMC9774540 2022) |
| 4 | Strategic Framing | Cognitive | 1.0 | Campaign performance | Consultative/value-based selling literature |
| 5 | Discovery Discipline | Execution | 1.25 | Pipeline qualification quality | SPIN (Rackham 1988); MEDDIC qualification framework |
| 6 | Call Control | Execution | 1.0 | Conversion to next step | Challenger Sale "take control" (Dixon & Adamson 2011); call structure literature |
| 7 | Next-Step Specificity | Execution | 1.25 | Pipeline progression | Closing-behavior research; commitment-securing literature |

**Tier bands (weighted score, max ~41):**
- Strong: 30+
- Competent: 22–29
- Developing: 14–21
- Rookie: <14

---

## Axis 1: Merchant-Economic Modeling

**What it measures.** Whether the rep correctly identifies and responds to the merchant's actual P&L reality — margin structure, capacity profile, customer-mix concerns — and shapes the conversation around those constraints rather than around DealDrop's generic value prop.

**Why it exists.** DealDrop's commission structure puts real economic pressure on merchants (mid-30s to low-40s percent take rate on top of a discount). A rep who pitches deal depth without understanding the merchant's margin is selling a product that will burn the merchant and churn within a campaign cycle. Most predictive axis for downstream merchant retention.

| Score | Anchor |
|-------|--------|
| **1 — Absent** | No reference to merchant economics. Pitches discount depth, voucher volume, or exposure with no probe into whether the math works for this merchant. Treats merchant as a generic prospect. |
| **3 — Surface** | References economics in general terms ("I know margins are tight") but doesn't probe specifics. Acknowledges concerns reactively when raised but doesn't proactively engage with the merchant's P&L. |
| **5 — Substantive** | Proactively probes margin structure, capacity utilization, or customer mix early in the call. Adjusts deal recommendations based on what they learn ("given your food cost, a 40% deal makes more sense than 50%"). Demonstrates working knowledge of how DealDrop's economics interact with the merchant's. |

---

**Academic grounding for Axis 1**

This axis sits at the intersection of two literatures. From **Saxe & Weitz (1982) SOCO research**, customer-oriented selling involves "helping customers make decisions that satisfy their needs" — economic modeling is the operational version of that principle for the SDR-merchant relationship, since merchant economics *are* the merchant's needs in this context. From **Rackham's SPIN (1988)**, the Need-payoff question category specifically asks the prospect to articulate the value of solving their problem in their own terms; economic modeling is the cognitive substrate that lets a rep ask Need-payoff questions intelligently.

The vertical-specific operationalization (margin structure, capacity utilization, customer mix) is *not* found in the academic literature, which tends to treat economic modeling as a generic competence. **McFarland (2022), "Applying Adaptive Selling Techniques: Exploring How"** (Keller Center, Baylor) explicitly critiques the literature for being too generic to be actionable — providing academic permission for vertical-specific anchor design like this one.

---

## Axis 2: Contextual Responsiveness

**What it measures.** Whether the rep updates their approach based on signals the merchant gives during the call — adjusting pitch depth, question type, pacing, or framing in response to merchant disposition shifts, stated context, or revealed information. Operationalizes theory-of-mind / perspective-taking.

**Why it exists.** Most rep failures aren't from bad scripts — they're from running a script regardless of merchant signals. The cognitive skill of detecting and responding to context is what separates consultative from transactional selling. Most coachable behavior in the rubric — shows up in observable turn-by-turn updates.

| Score | Anchor |
|-------|--------|
| **1 — Script-locked** | Runs a fixed sequence regardless of merchant input. Merchant signals (time pressure, prior bad experience, hesitation) ignored or steamrolled. Returns to script after merchant statements rather than building on them. |
| **3 — Reactive** | Adjusts when merchant explicitly redirects ("I'm busy, get to the point") but doesn't pick up on softer signals. Some evidence of listening but limited integration of merchant context into subsequent turns. |
| **5 — Adaptive** | References prior merchant statements in later turns ("you mentioned Tuesdays are slow — that's exactly the surface this addresses"). Adjusts depth, pacing, and framing based on merchant disposition. Picks up implicit signals (hesitation, vocabulary, business sophistication) and calibrates accordingly. |

---

**Academic grounding for Axis 2**

This is the rubric's most directly literature-grounded axis. The construct is **adaptive selling behavior** as defined in **Weitz, Sujan & Sujan (1986)**: altering sales behaviors during or across customer interactions based on perceived information about the nature of the selling situation. The validated measurement instrument is the **ADAPTS scale** from **Spiro & Weitz (1990)** — sixteen self-report items across five facets (recognition that different approaches are needed, confidence in using varied approaches, confidence in altering approaches mid-interaction, knowledge facilitating different approaches, actual use of different approaches).

The cognitive framing — that responsiveness is a theory-of-mind / mentalizing behavior — is supported by recent empirical work. A **2024 paper in *Current Psychology*** (Springer, "Don't put all the eggs in one basket") found that adaptive selling behavior **mediates the relationship between interpersonal mentalizing skills and both sales and relational performance**. This is direct empirical backing for treating responsiveness as a cognitive (rather than affective) skill.

A note on departure from the literature: the ADAPTS scale is **self-report**. This rubric measures behavior in transcripts. The constructs are aligned but the measurement modality is different — worth flagging in the writeup as a methodological extension rather than a direct application.

---

## Axis 3: Risk Acknowledgment

**What it measures.** Whether the rep proactively surfaces merchant-side risks and costs (margin compression, capacity surge, customer-mix shift, brand effect, prior-deal trauma) before the merchant raises them — or whether risk only enters the call as objection.

**Why it exists.** Reactive objection handling is table stakes; proactive risk surfacing is the move that distinguishes a trustworthy rep from a transactional one. Merchants who feel the rep understands their risk are dramatically more likely to launch and renew. Reps who only address risk when forced telegraph that they're optimizing for the close, not the merchant.

| Score | Anchor |
|-------|--------|
| **1 — Defensive** | Avoids or minimizes risk topics. When risks are raised, deflects or reassures without engagement ("don't worry, our merchants love it"). Risk acknowledgment treated as a threat to the close. |
| **3 — Reactive** | Handles raised objections competently but doesn't surface risk on their own. Acknowledgment is responsive, not anticipatory. Merchant has to do the work of articulating concerns. |
| **5 — Proactive** | Names at least one merchant-side risk before the merchant does ("one thing worth flagging — if we run a 50% deal with no cap, you could see a redemption surge that strains your kitchen"). Treats risk transparency as part of building trust, not as a concession. |

---

**Academic grounding for Axis 3**

This axis is grounded in the **customer-oriented selling** tradition rather than the adaptive selling tradition — an important distinction. **Saxe & Weitz (1982)** developed the **SOCO scale** to measure the degree to which salespeople help customers make decisions that satisfy customer needs (vs. acting in the firm's short-term interest). The SOCO construct treats other-regarding behavior as a measurable orientation, not just a personality trait.

The 2022 paper **"Investigating Salespeople's Performance and Opportunistic Behavior"** (*Sustainability*, PMC9774540) sharpens why this matters: adaptive selling is *neutral* with respect to whether it serves the customer — a rep can adaptively manipulate. Customer-oriented selling is fundamentally other-regarding. Risk acknowledgment is the behavioral signature of customer orientation in a cold-call context. A rep who proactively surfaces merchant risk is acting in the merchant's interest at potential cost to their own close rate.

This is one of the rubric's more **theoretically grounded but practically rare** axes — the academic literature establishes it as important, but it's not commonly measured in industry rubrics. That's a defensible position to take in the writeup: "this rubric scores customer-oriented behavior because the COSB literature shows it predicts long-term outcomes, even though industry rubrics underweight it."

---

## Axis 4: Strategic Framing

**What it measures.** Whether the rep positions DealDrop as fitting into the merchant's broader customer-acquisition strategy — top-of-funnel acquisition channel, customer LTV play, capacity-fill mechanism — rather than as a one-off promotional revenue event.

**Why it exists.** Merchants who understand DealDrop as a customer-acquisition channel structure their deals, fulfillment, and upsell to convert deal-redeemers into repeat customers. Merchants who understand it as a one-shot revenue grab don't, and they churn at high rates. The rep's framing on the cold call sets the merchant's mental model for the entire campaign.

| Score | Anchor |
|-------|--------|
| **1 — Transactional** | Pitches DealDrop purely as a revenue event ("you'll sell X vouchers, generate $Y"). No frame for what DealDrop is *for* in the merchant's business beyond the immediate transaction. |
| **3 — Generic value prop** | Articulates standard DealDrop positioning (exposure, new customers) but doesn't connect it to the merchant's specific acquisition strategy or customer economics. |
| **5 — Strategic fit** | Frames DealDrop as a specific kind of acquisition channel ("we bring in trial customers — your job during redemption is to convert them to repeats; here's what merchants who do that well look like"). Connects the deal structure to merchant LTV strategy. Implicitly or explicitly differentiates DealDrop from other marketing spend. |

---

**Academic grounding for Axis 4**

This axis is grounded more in **practitioner literature** than in peer-reviewed academic research. The conceptual lineage runs through **consultative selling** (origins in Hanan, *Consultative Selling*, 1970) and **value-based selling** literature, both of which emphasize positioning the offer in terms of the buyer's strategic goals rather than the seller's product.

The closest academic anchor is **The Challenger Sale (Dixon & Adamson, 2011)**, based on CEB / Gartner research, which finds that "Challenger" reps — those who *teach, tailor, and take control* — outperform other rep types in complex B2B sales. The "teach" dimension is the strategic-framing competency: reframing the buyer's understanding of their own business problem.

A weaker but relevant academic anchor: **influence tactics research** (e.g., **Kim & McFarland 2024** on matching influence tactics to customer goals to improve processing fluency). Strategic framing is a particular kind of influence tactic — reframing the offer's category in the buyer's mind.

This is the rubric's **most loosely grounded axis academically**. Worth noting honestly in the writeup. The justification is operational (it predicts merchant launch behavior at DealDrop specifically) more than empirical-academic.

---

## Axis 5: Discovery Discipline

**What it measures.** Whether the rep systematically extracts the information needed to qualify the lead and shape a fit-appropriate pitch — covering decision authority, current promotional activity, capacity profile, prior daily-deal experience, and timing — through structured questioning rather than ad-hoc probing.

**Why it exists.** Where Axis 2 captures *responsiveness* to what the merchant says, this axis captures the upstream skill of systematically *getting* the merchant to say it. A rep can be highly responsive to a thin information set and still fail to qualify the lead. Discovery discipline is what separates "a nice conversation" from "a qualified pipeline opportunity."

| Score | Anchor |
|-------|--------|
| **1 — Surface** | Minimal discovery — pitches without establishing decision authority, capacity context, or prior promotional experience. May ask 1-2 generic questions but doesn't act on the answers. Call yields almost no information about merchant fit. |
| **3 — Partial** | Covers some qualification dimensions (e.g., gets decision authority and current activity) but misses others (capacity profile, prior deal experience, timing). Question quality is mixed — some probing, some surface. Information yield moderate. |
| **5 — Systematic** | Covers all major qualification dimensions through deliberate sequencing. Probes deeper on revealing answers ("you said the last DealDrop didn't work — what specifically went wrong?"). Distinguishes situation-level facts from problem-level pain. By call's end, the rep could write a defensible qualification summary. |

**Note on objection handling.** This rubric distributes objection handling across Axes 2, 3, and 6. The decision not to make it a standalone axis is deliberate — *handling* is composed of underlying skills already measured. As a standalone construct, "objection handling" tends to collapse into platitude scoring ("handled smoothly") with poor inter-rater reliability.

---

**Academic grounding for Axis 5**

This axis is grounded in the **practitioner research tradition** more than in peer-reviewed academic literature. The two primary anchors:

**SPIN Selling (Rackham, 1988)** — based on empirical research at Huthwaite Inc. analyzing successful vs. unsuccessful B2B sales calls. The SPIN framework (Situation → Problem → Implication → Need-payoff) is essentially a sequenced discovery protocol. Rackham's central empirical finding: successful reps ask more Implication and Need-payoff questions; less-successful reps over-rely on Situation questions. The "Systematic" anchor at score 5 maps directly to the SPIN progression.

**MEDDIC / MEDDPICC** — qualification framework developed at PTC in the 1990s, widely used in enterprise B2B sales. Dimensions: **M**etrics, **E**conomic buyer, **D**ecision criteria, **D**ecision process, **I**dentify pain, **C**hampion. The qualification dimensions in the Axis 5 anchors (decision authority, current activity, capacity, prior experience, timing) translate MEDDIC concepts to SDR-cold-call appropriate scope.

The closest peer-reviewed academic connection: discovery quality is a **precondition for adaptive selling**. The Weitz et al. (1986) framework requires the rep to have information about the customer to adapt; discovery is how that information is acquired. This makes Axis 5 an *upstream* dependency for Axis 2.

---

## Axis 6: Call Control

**What it measures.** Whether the rep maintains a coherent call structure (opener → discovery → pitch → objection handling → next step) without losing the thread, getting steamrolled, or letting the call drift. Captures execution discipline as distinct from cognitive engagement.

**Why it exists.** A rep can have perfect merchant empathy and still fail to run a productive call. Call control is the executional substrate that lets the cognitive skills produce outcomes. Without it, strong cognitive performance fails to convert into booked next steps.

| Score | Anchor |
|-------|--------|
| **1 — Lost** | Loses control — pulled into tangents, can't recover from interruptions, abandons structure when challenged. Call ends without clear progression. Merchant drives; rep reacts. |
| **3 — Functional** | Maintains general structure but loses ground in difficult moments. Recovers from interruptions inconsistently. Some discovery happens but not systematically; some objections handled but pacing suffers. |
| **5 — Controlled** | Moves through call phases with clear intent. Handles interruptions, pivots, and hostile moments without losing structure. Brings call back on track when it drifts. Pacing matches merchant's signals — efficient when busy, expansive when engaged. |

---

**Academic grounding for Axis 6**

The closest academic anchor is the **"take control"** dimension in **The Challenger Sale (Dixon & Adamson, 2011)** — based on CEB/Gartner research finding that Challenger reps who actively control conversations outperform Relationship Builders and other types in complex sales. While Challenger research focuses on B2B enterprise contexts, the take-control behavioral pattern translates to SDR cold calls.

Adjacent academic grounding: **call-stage progression** is implicit in most sales process research dating back to **AIDA (Attention, Interest, Desire, Action)** and its descendants. The literature consistently treats sales calls as *staged* interactions where structural progression matters, even when the specific stage labels vary. The rubric anchors operationalize this as observable behaviors (phase transitions, recovery from interruption, pacing alignment).

This axis is also where the **Sequential Decision Problem** framing from recent ML literature applies. **Nandakishor (2025) SalesRLAgent** treats sales conversations as sequential decisions rather than content generation. Call control is the human analog — the rep is making sequential decisions about phase transitions, depth, and pacing.

---

## Axis 7: Next-Step Specificity

**What it measures.** Whether the rep secures a concrete next-step commitment — specific calendar time, channel, agenda — rather than a vague "I'll send something over" or "let me think about it."

**Why it exists.** For an SDR, the *close* is the next-step commitment. Booked meetings convert at a meaningfully different rate than vague follow-ups; specific calendar invites convert at a higher rate than "I'll email you." Most binary, observable axis in the rubric and most direct predictor of pipeline progression.

| Score | Anchor |
|-------|--------|
| **1 — None** | Call ends with no next step, or with merchant clearly fobbing off the rep ("send me an email"). No commitment captured. Rep accepts soft brush-off without attempting to convert it. |
| **3 — Soft** | Next step committed to but loosely specified — "I'll follow up next week," "let's circle back," email exchange agreed but no calendar time. Some forward motion but high drop-off risk. |
| **5 — Concrete** | Specific calendar time secured (day, time, channel), agenda referenced ("we'll walk through what a deal structure could look like for your slow Tuesdays"), confirmation captured. Merchant has explicit commitment with low ambiguity. |

---

**Academic grounding for Axis 7**

Academic backing for this axis is thinner than for the cognitive axes — most peer-reviewed sales research focuses on the conversation rather than the close mechanics. The relevant anchors:

**Cialdini's commitment-and-consistency principle** (Cialdini, *Influence: The Psychology of Persuasion*, 1984) provides theoretical grounding for why specific commitments outperform vague ones: people honor explicit, public, written commitments at higher rates than soft verbal agreements.

**Recent ML evidence** offers the most concrete support. **"Learning When to Quit in Sales Conversations"** (arXiv:2511.01181, 2025) implicitly validates the importance of next-step specificity by demonstrating that real outbound sales calls have wide variance in how decisively they end — and that decisive endings (including decisive disqualifications) are economically valuable. The paper's empirical finding that 36% of call time can be saved without losing sales suggests that prolonged inconclusive calls are common and avoidable.

Industry research consistently reports that booked-with-calendar-invite next steps convert at meaningfully higher rates than "I'll follow up" commitments. While not peer-reviewed, this is the closest thing to consensus in sales operations data.

---

## Disposition Metadata (Required Per Call)

Every call gets tagged with a disposition before scoring. Disposition conditions which axes apply — scoring all seven axes on a 30-second voicemail is meaningless and would inflate noise.

| Disposition | Description | Axes Scored |
|-------------|-------------|-------------|
| **Voicemail** | No human reached | None scored; descriptive metrics only (voicemail quality flagged separately) |
| **Gatekeeper Block** | Reached non-DM, blocked from DM | Axes 2, 6 only (responsiveness, call control) |
| **DM Reached, Quick No** | DM on phone <60s, immediate decline | Axes 1, 2, 3 only (cognitive engagement under pressure) |
| **DM Reached, Full Conversation** | Sustained discovery + pitch + close attempt | All seven axes |
| **DM Reached, Qualified Disqualification** | Full conversation that ends in clean disqualification | All seven axes; disqualification is *positive* outcome, not negative |
| **Wrong Number / Out of Business** | Bad data | Excluded from coaching; flagged for data quality |

Pipeline-quality signals to capture alongside disposition:
- **Qualification status reached:** Qualified / Disqualified / Ambiguous
- **Lead heat shift:** Increased / Maintained / Decreased / N/A

---

**Academic grounding for disposition conditioning**

Disposition-conditioned scoring is methodologically aligned with **Weitz's original Contingency Model (1981)**, which argued that ideal selling behaviors are situation-dependent. Different call dispositions are different selling situations and should be evaluated against situation-appropriate criteria. Applying a uniform rubric across all dispositions violates the contingency principle.

The **"Learning When to Quit" paper (arXiv:2511.01181)** also validates disposition-aware analysis by showing that early-call quitting decisions can be made with high accuracy from transcript features — implying that calls have detectable disposition states early enough to condition downstream evaluation on them.

This is one place where the rubric **departs from industry standard practice** (Gong, Chorus typically apply uniform scorecards across disposition types). The departure is academically defensible, not arbitrary.

---

## Diagnostic Outputs (Descriptive, Not Scored)

These metrics are reported alongside rubric scores as diagnostic context. They're proxies, not skills — a rep with strong rubric scores and weak diagnostics is still strong; a rep with weak rubric scores and clean diagnostics is still weak.

- **Talk-listen ratio.** Target benchmark: 40–50% rep talk time on full conversations. Flag if outside 30–60%.
- **Filler density.** Um, uh, like, you know per minute of rep speech. Flag elevated rates without scoring them.
- **Pace and pacing variability.** Words per minute average + variance. (Audio-dependent — flag as future work for transcript-only systems.)
- **Pause behavior.** Mean and max silence after rep questions. (Audio-dependent.)
- **Interruption frequency.** Rep-on-merchant and merchant-on-rep, with directionality.
- **Call duration relative to disposition.** A 90-second "full conversation" disposition is suspicious; an 18-minute "quick no" is suspicious.

---

**Academic/industry grounding for diagnostic outputs**

The decision to demote paralinguistic metrics from scoring axes to descriptive outputs **mirrors Gong's production architecture**: Gong's automatic conversation metrics (talk-time ratios, longest customer monologue, interactivity score, patience, filler density) sit underneath customer-defined scorecards rather than within them. This is industry-converged practice.

The academic justification: paralinguistic metrics suffer the **inter-rater reliability test** less because they're machine-measurable, but they fail the **outcome attribution test** because they're correlated with skill rather than constitutive of it. A rep with great pacing and bad cognitive engagement still fails. Reporting them as descriptive avoids conflating execution surface with skill substance.

---

## Coaching Priority Output

Beyond numerical scores, the coach produces a **highest-leverage coaching priority** — the single behavior change that would unlock the most performance improvement for this rep on this call. This is the bridge between AI feedback and rep behavior change.

Format:
- **Priority skill:** [axis name]
- **Specific moment:** [turn or phase reference from the call]
- **What happened:** [concrete description, not generic]
- **What to try instead:** [actionable alternative behavior]
- **Why this one:** [why it's higher leverage than other observed gaps]

---

**Academic grounding for coaching priority**

This output addresses a documented gap in the **adaptive selling literature**. **McFarland (2022)** explicitly critiques generic adaptive selling measurement for being **un-actionable**: "while research suggests adaptive selling is a core ingredient of sales success, the question of how salespeople should alter their behavior, in response to varying customer attributes, has remained unclear." The coaching priority output is the operational answer to McFarland's critique — instead of giving a rep a multi-axis score, the system identifies the specific behavioral change with the highest expected return.

This also connects to **Sujan, Weitz & Kumar (1994), "Learning Orientation, Working Smart, and Effective Selling"** — the empirical finding that salespeople with high learning orientation outperform those with high effort orientation. Coaching priority output is designed to support learning orientation by directing attention to a specific change rather than asking the rep to absorb a comprehensive score.

---

## Compliance Flags (Production Concern, Not Scored)

These are flagged separately from the rubric. Out of scope for the this MVP but called out in the writeup as a production-system requirement.

- **Recording disclosure** (two-party-consent state coverage)
- **TCPA awareness** (do-not-call, time-of-day restrictions)
- **Misrepresentation** (overpromising results, claims DealDrop doesn't guarantee)
- **Pressure tactics** (false urgency, fake scarcity, manipulative framing)

---

## Scoring & Aggregation

Each scored axis: 1–5. Total = weighted sum, conditioned on disposition.

- **Max raw score (full conversation):** 35 (seven axes × 5)
- **Max weighted score (full conversation):** ~41
- **Weight rationale:** Hypothesized weights pending empirical calibration. Equal weighting is the most defensible default until outcome data is available; current weights reflect *informed priors* about which axes correlate most strongly with downstream merchant outcomes (retention, campaign performance), not validated coefficients.

**A note on weight calibration.** This is the rubric's most epistemically vulnerable choice. The honest move in the writeup is to (a) explicitly flag the weights as hypotheses, (b) describe the empirical procedure that would validate or revise them (regression of axis scores against downstream outcomes), and (c) consider whether equal weighting would be more defensible until calibration is possible. The **2025 JAMS systematic review** structure suggests that adaptive selling outcome mediation operates through four mechanism categories — those mechanisms could provide theoretical guidance for weight setting, but doing it well requires more than 72 hours.

---

## What This Rubric Deliberately Excludes

| Excluded | Why | Literature support for exclusion |
|----------|-----|----------------------------------|
| Affect / energy / enthusiasm | Artifacts of rep personality, not learnable behaviors | Sujan et al. (1994) finding that learning orientation, not effort/affect, predicts effectiveness |
| Rapport / likability | Considered and rejected on measurement grounds (low inter-rater reliability), not theoretical | Captured behaviorally in Axes 2 and 3 via ADAPTS- and SOCO-aligned anchors |
| Talk-listen ratio as scored axis | Demoted to diagnostic output | Gong production architecture; outcome-attribution test |
| Objection handling as standalone axis | Distributed across Axes 2, 3, 6 | "Handling" lacks construct independence; tends to collapse into platitude scoring |
| Traditional "closing skills" | SDR cold calls don't close deals | Captured in Axis 7 with role-appropriate scope |
| Authentic warmth / perceived sincerity | Outcome-relevant in SMB sales but inter-rater unreliable | Excluded on measurement grounds, not theoretical grounds — acknowledge in writeup |

---

## Open Questions for Refinement (Pre-Lock)

1. **Weight calibration.** Current weights are hypothesized. The A/B test framework should validate them empirically by correlating axis scores with downstream merchant outcomes. **Academic alignment check:** the four mechanism categories from the JAMS 2025 SLR (job-confidence, self-confidence, job-proficiency, self-proficiency) might offer theoretical structure for weight differentiation.

2. **Adversarial cases.** Before locking the rubric, generate 2–3 deliberately hard scenarios:
   - Rep scores high on all cognitive axes but fails to advance the call
   - Rep steamrolls but books a meeting
   - Hostile merchant from word one
   - Quick-no disposition where the rep had 30 seconds

3. **Vertical-specific anchor variants.** Current anchors are vertical-agnostic. Consider whether Axis 1 needs vertical-specific anchor language for restaurant vs. spa vs. fitness vs. auto. **Academic alignment check:** McFarland (2022) explicitly endorses context-specific operationalization.

4. **Discovery–Responsiveness boundary.** Axes 2 and 5 are conceptually distinct (extraction vs. updating) but may correlate highly. **Academic alignment check:** in the Weitz framework, discovery is logically prior to adaptation (you can't adapt to information you haven't extracted). If empirical scoring shows tight correlation, the framework predicts it — but distinguishability should still be designed into anchors.

5. **Out-of-distribution test.** Score at least one real call (YouTube cold-call recording or published sales training transcript) with this rubric in the writeup. **Methodological grounding:** the SalesLLM benchmark (arXiv:2604.07054) achieved Pearson r = 0.98 between automated and expert ratings — that's the bar to be aware of, even if you can't match it in 72 hours.

6. **Coaching priority validation.** Does the coach's "highest-leverage priority" output correlate with the lowest-scoring axis on the call, or surface different gaps? Itself an interesting evaluation question.

---

## Methodological Stance for Writeup

Three framing claims to make explicitly, each with literature backing:

1. *"This rubric is designed around cognitive and execution behaviors rather than affective ones, because cognitive and execution behaviors are (a) more reliably observable, (b) more causally connected to outcomes, and (c) more coachable than affect."*
   **Backed by:** Sujan, Weitz & Kumar (1994) on learning orientation > effort orientation; the 2024 *Current Psychology* paper on mentalizing-mediated adaptive selling.

2. *"The synthetic dataset is engineered to stress-test the rubric across the scoring axes, not to approximate distributional realism. Real call data, when available, plugs into the same scoring pipeline as ground truth for axis-weight calibration."*
   **Backed by:** Nandakishor (2025) SalesRLAgent precedent for synthetic-data-trained sales prediction; SalesLLM benchmark methodology for human-correlation validation.

3. *"Scoring without prioritization is feedback-shaped noise. The coach produces a coaching priority output alongside scores precisely because behavior change requires direction, not just measurement."*
   **Backed by:** McFarland (2022) critique of un-actionable adaptive selling measurement; Sujan et al. (1994) learning orientation findings.

---

## References

### Foundational sales effectiveness research

- Saxe, R., & Weitz, B. A. (1982). "The SOCO Scale: A Measure of the Customer Orientation of Salespeople." *Journal of Marketing Research*, 19(3), 343–351.
- Weitz, B. A. (1981). "Effectiveness in Sales Interactions: A Contingency Framework." *Journal of Marketing*, 45(1), 85–103.
- Weitz, B. A., Sujan, H., & Sujan, M. (1986). "Knowledge, Motivation, and Adaptive Behavior: A Framework for Improving Selling Effectiveness." *Journal of Marketing*, 50(4), 174–191.
- Spiro, R. L., & Weitz, B. A. (1990). "Adaptive Selling: Conceptualization, Measurement, and Nomological Validity." *Journal of Marketing Research*, 27(1), 61–69.
- Sujan, H., Weitz, B. A., & Kumar, N. (1994). "Learning Orientation, Working Smart, and Effective Selling." *Journal of Marketing*, 58(3), 39–52.

### Modern adaptive selling research

- 2025 systematic literature review on adaptive selling, *Journal of the Academy of Marketing Science* (Springer). **[verify exact authorship]**
- *Current Psychology* (2024). "Don't put all the eggs in one basket: examining adaptive selling behavior in salespeople's performance." Springer.
- *Sustainability* (2022). "Investigating Salespeople's Performance and Opportunistic Behavior: Adaptive and Customer-Oriented Responses." PMC9774540.
- McFarland, R. G. (2022). "Applying Adaptive Selling Techniques: Exploring How." Keller Center for Research, Baylor University.
- Kim & McFarland (2024). Customer-perspective research on influence-tactic matching, referenced in JAMS 2025 SLR.

### ML/NLP on sales conversations

- Nandakishor, M. (2025). "SalesRLAgent: A Reinforcement Learning Approach for Real-Time Sales Conversion Prediction and Optimization." arXiv:2503.23303.
- "Sell More, Play Less: Benchmarking LLM Realistic Selling Skill." arXiv:2604.07054.
- "Learning When to Quit in Sales Conversations." arXiv:2511.01181 (2025).
- Chang, W. & Chen, Y. (2024). "Injecting Salesperson's Dialogue Strategies in Large Language Models with Chain-of-Thought Reasoning." arXiv:2404.18564.

### Practitioner frameworks

- Rackham, N. (1988). *SPIN Selling*. McGraw-Hill.
- Dixon, M., & Adamson, B. (2011). *The Challenger Sale: Taking Control of the Customer Conversation*. Portfolio.
- Cialdini, R. B. (1984). *Influence: The Psychology of Persuasion*. Harper Business.
- MEDDIC / MEDDPICC qualification framework (origin: PTC, 1990s; widely adopted in enterprise B2B sales).

### Validated measurement scales

- **ADAPTS** — Spiro & Weitz (1990). 16 items, five facets of adaptive selling behavior.
- **SOCO** — Saxe & Weitz (1982). 24 items measuring selling orientation vs. customer orientation.

---

## Glossary of Academic Terms

- **AdaptS / Adaptive Selling Behavior** — Construct from Weitz et al. 1986; altering behavior based on perceived customer cues.
- **ADAPTS Scale** — Validated 16-item instrument by Spiro & Weitz 1990.
- **SOCO** — Selling Orientation / Customer Orientation; a continuum, not binary.
- **Interpersonal Mentalizing** — Academic term for theory-of-mind applied to other people's mental states in interaction.
- **Working Smart** — Sujan et al. 1994 construct; cognitive effort applied to adapting behavior.
- **Customer-Oriented Selling Behavior (COSB)** — Acting in the customer's interest; sometimes vs. salesperson's short-term interest.
- **Influence Tactics** — Behavioral moves a salesperson uses to shape customer beliefs or decisions.
- **Sequential Decision Problem** — Framing used in SalesRLAgent; treats sales conversation as a series of decisions rather than content generation.
- **Role Inversion** — Failure mode in LLM customer-simulation where the simulated customer starts acting like a salesperson (SalesLLM benchmark term).
