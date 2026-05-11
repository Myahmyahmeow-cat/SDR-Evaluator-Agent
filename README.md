# SDR-Evaluator-Agent
This was built during a case study for a job interview process. It needed to be delivered in 72 hrs.


# SDR Call Evaluation Agent — LLM-as-Judge with Evidence-Grounded Scoring

A single-call evaluator that scores SDR cold-call transcripts against a literature-anchored rubric. Built as an exploration of LLM-as-judge design patterns: structured-output schema enforcement, disposition-conditioned scoring, evidence-grounded justification, and deterministic client-side aggregation.

## What it does

Takes a call transcript + disposition tag and returns a structured evaluation:

- **Per-axis scores** (1-5) across 7 axes, each with cited transcript turn indices and an anchor-match band
- **Coaching priority** — the single highest-leverage behavior change for this rep on this call (skill / moment / what happened / what to try / why this one)
- **Compliance flags** — binary alerts for recording disclosure, TCPA, misrepresentation, pressure tactics
- **Diagnostic metrics** — talk-listen ratio, interruptions, duration appropriateness (descriptive, not scored)
- **Weighted total + tier band** — computed client-side from axis scores against percentage thresholds

## Design choices worth flagging

- **Single API call per transcript** rather than a multi-agent pipeline. At realistic scale, simplicity beats orchestration; failure modes are easier to debug and the cost/latency profile is predictable.
- **Output enforced via Pydantic schema** through Anthropic's `output_format` parameter. The model cannot return JSON that violates the schema — schema rejection happens at the API layer, not in post-processing.
- **Disposition gates which axes apply.** Voicemails get no axis scores (diagnostics only); gatekeeper-blocks score only Contextual Responsiveness + Call Control; quick-nos score the three cognitive axes only; full conversations score all seven.
- **Every score must cite evidence turns.** Applies the rubric's inter-rater-reliability principle to the model itself — justifications must be grounded in specific transcript indices, not generic prose.
- **Async concurrency, semaphore-bounded.** Up to 3 in-flight API calls at a time, parallelizing the batch while keeping output legible.
- **Client-side aggregation.** The model emits per-axis scores; Python computes the weighted total, percentage of max, and tier band. Math is deterministic and auditable; the model doesn't do arithmetic.

## The rubric

The rubric scores 7 axes split across two categories:

- **Cognitive (4)** — Merchant-Economic Modeling, Contextual Responsiveness, Risk Acknowledgment, Strategic Framing
- **Execution (3)** — Discovery Discipline, Call Control, Next-Step Specificity

Each cognitive axis is anchored in a measurement instrument from sales-effectiveness research (ADAPTS scale, SOCO scale, SPIN, MEDDIC, Challenger Sale). Three principles gate every axis:

1. **Vertical-swap test** — could the anchor language be lifted into a different sales context unchanged? If yes, it's too generic.
2. **Inter-rater reliability** — three coaches scoring the same call should land within 1 point.
3. **Outcome attribution** — does this axis trace to a measurable downstream outcome (merchant retention, launch rate, pipeline conversion)?

Paralinguistic metrics (talk-listen ratio, pacing, interruptions) are reported as descriptive diagnostics rather than scored axes — they correlate with skill rather than constitute it. This mirrors production-system architecture (e.g., Gong's customer-defined scorecards sit on top of automatic conversation metrics, not within them).

See `sdr_coaching_rubric.md` for full anchor language, academic citations, and the diagnostic principles in detail.

## Getting started

### Colab (recommended)

1. Upload `notebook.ipynb` and `call_transcripts.json` to Colab
2. Add `ANTHROPIC_API_KEY` to Colab Secrets (left sidebar, 🔑 icon)
3. Run the bootstrap cell — it handles deps and key loading
4. Run remaining cells top to bottom

### Local

```
pip install anthropic pydantic
export ANTHROPIC_API_KEY="sk-ant-..."
jupyter notebook notebook.ipynb
```

The notebook contains 21 cells. Roughly:

- Cells 1-2: bootstrap (Colab install + key handling)
- Cells 3-4: imports, config, rubric loading
- Cells 5-10: constants, Pydantic schema, system prompt construction
- Cells 11-14: evaluator function + report renderer + demo
- Cells 15-16: batch run across all transcripts with bounded concurrency
- Cells 17-20: system-level checks (tier calibration + inter-run consistency)

## Plugging in your own rubric

Replace `RUBRIC_TEXT` in cell 4 with your own markdown. Update the `AXIS_INFO` dict in cell 14 to match your axis labels and anchor descriptions. The schema, evaluator, and aggregation logic adapt automatically — only the prompt content changes.

## Calibration check

The notebook includes a built-in calibration check that compares the agent's tier band against the synthetic `rep_tier` ground truth in the included dataset. On the bundled 16 transcripts, 87% of scorable calls land within ±1 band (13/15; voicemail and gatekeeper-block dispositions excluded). Errors went in both directions — over-charity and under-charity were both observed.

This is a sanity check, not external validation. Real evaluation requires real call data scored against measurable downstream outcomes.

## Known limitations

This is a starter framework, not a production system:

- **No vertical-specific anchors.** Rubric scores generically across SMB verticals. A restaurant call and a spa call are scored against identical anchor language.
- **Text-only.** No audio input; paralinguistic signal (tone, pace, pause behavior) is unavailable.
- **Evidence-turn validation isn't enforced.** The agent cites turn indices; nothing in the system checks that the cited turns actually contain what the justification claims.
- **Weights are hypothesized, not validated.** The 1.5 / 1.25 / 1.0 axis weights are informed priors, not empirically calibrated against downstream outcomes.
- **No multi-call rep rollups.** Each call is evaluated in isolation; longitudinal patterns across a rep's call history are out of scope.
- **LLM-as-judge artifacts.** Occasional cross-lingual token leaks (a stray Chinese character mid-English-sentence was observed in one of 16 calls) and a mild charity bias toward middle tier bands.

## What would close the gap

If extended into production, the main moves would be:

- **Behavior-adoption tracking** — re-score subsequent calls and look for axis-score flips on the specific axis the agent flagged
- **Manager-in-the-loop integration** — coaching priorities feed into 1:1 prep, not just a rep dashboard
- **Rehearsal mode** — a paired practice layer where the rep tries the suggested behavior change before their next real call
- **Disposition classifier upstream** — production wouldn't trust metadata; the agent should classify the call's disposition itself
- **Critic pass** — a second LLM auditing evidence-grounding before reports are surfaced

## Original context

Adapted from a take-home exercise for an AI enablement role. Company-specific content has been generalized for public release; the design philosophy, code, academic anchoring, and rubric structure are mine.
