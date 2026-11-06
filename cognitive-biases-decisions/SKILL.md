---
name: cognitive-biases-decisions
description: "Kahneman & Tversky prospect theory + human biases diagnostic skill: heuristics, framing, loss aversion, anchoring, availability, overconfidence. Use to identify biases in decisions, debias plans and red-team pricing, messaging and strategies. Triggers: bias, heuristic, framing, loss aversion, anchoring, availability, overconfidence, prospect theory, debias, decision."
---

# Cognitive Biases & Decision-Making (Kahneman & Tversky)

## Core Philosophy
Biases are not bugs to eliminate; they are **predictable distortions** to detect and compensate for. The skill's value is not listing biases (the agent knows them) but **diagnosing which bias is operating in a specific decision and prescribing the debiasing move**.

## Core Formula
> **Debiasing Value = (bias identified) + (mechanism named) + (mitigation applied)**
A bias name without a mitigation is trivia, not a tool.

## Thinking Patterns (Mindset)
- **Before trusting a number, ask: "What was the anchor and would I have chosen this without it?"**
- **Before evaluating a loss, ask: "What is the reference point and is it arbitrary?"**
- **Before accepting a vivid example, ask: "Am I overweighting availability over base rates?"**
- **Before confirming a belief, ask: "What evidence would change my mind?"**
- **Before escalating, ask: "Am I chasing sunk cost?"**

## Decision Tree
```
Is the decision framed as gain or loss?
├── Loss - expect risk-seeking; reframe to test stability
└── Gain - expect risk-aversion; widen reference point

Is a number/price involved?
├── Yes - anchoring scan; generate independent anchor
└── No - proceed

Is the evidence vivid/recent/salient?
├── Yes - availability check; seek base rates
└── No - proceed

Is the decision confirming a prior belief?
├── Yes - confirmation bias; seek disconfirming evidence
└── No - proceed
```

## Procedures (Domain-Specific)
1. Step 1: Identify the decision and its reference point.
2. Step 2: Run the bias scan (loss aversion, anchoring, availability, confirmation, sunk cost, framing).
3. Step 3: Name the bias and its mechanism.
4. Step 4: Apply the mitigation (reframe, seek disconfirming, widen reference, pre-mortem).
5. Step 5: Re-evaluate the decision with the bias compensated.
Workflow: scan -> name -> mitigate -> re-evaluate.

## Core Mental Models
1. **Prospect theory.** Outcomes evaluated relative to a reference point (gains/losses), not final wealth. Losses loom ~2x gains (loss aversion). Risk-averse for gains, risk-seeking for losses.
2. **Heuristics.** Availability (ease of recall), representativeness (prototype similarity), anchoring (first number sticks). Fast, systematically biased.
3. **Framing.** Equivalent info presented differently changes choices ("90% survival" vs "10% mortality").
4. **Overconfidence.** Systematic overestimation of knowledge/ability; illusion of control; hindsight bias.
5. **Confirmation & availability.** Seek confirming evidence; overweight vivid/recent/salient events; ignore long-term trends.
6. **Sunk cost & status quo.** Past investments and current state overweight future decisions.
7. **Social biases.** Stereotyping, attribution error, in-group favoritism.

## MANDATORY Triggers
- **MANDATORY - READ** `cheatsheet.md` when running a bias scan.
- **MANDATORY - READ** `chapters/ch01-prospect-theory.md` when loss aversion or framing is involved.
- **Do NOT load** all chapters for a simple term lookup; use glossary only.

## Edge Cases & Failure Modes
- **Heuristics are adaptive, not always harmful:** know when they fail (high stakes, novel situations) vs. when they're efficient (routine, familiar).
- **Overcorrection risk:** debiasing can cause analysis paralysis; time-box the debiasing process.
- **Reference dependence:** loss aversion is reference-dependent; changing the reference changes the bias. Always identify the reference first.
- **Bias stacking:** multiple biases can compound; scan for all, not just the first found.
- **Cultural variation:** some biases vary by culture (e.g. self-serving bias is weaker in collectivist cultures).

## Anti-Patterns (NEVER)
- **NEVER treat heuristics as always harmful** because they are adaptive shortcuts; debias only when stakes are high or the situation is novel; otherwise you waste tokens and time.
- **NEVER overcorrect into analysis paralysis** because debiasing has diminishing returns; time-box it and decide.
- **NEVER ignore the reference point** because loss aversion is reference-dependent; without identifying the reference, the diagnosis is wrong.
- **NEVER confuse significance with importance** because a statistically significant bias may be practically trivial; report effect size.
- **NEVER debias without a mitigation** because naming a bias without prescribing a fix is trivia, not a tool.
- **NEVER assume a single bias** because biases stack and interact; scan comprehensively.

## Output Format
```
BIAS DIAGNOSIS
Decision: <one line>
Bias operating: <name>
Mechanism: <how it distorts>
Mitigation: <concrete debiasing move>
Reframed decision: <what changes>
```

## Voice Calibration
Empirical, precise, debiasing-oriented. Names the mechanism; offers concrete mitigation. No moralizing.
---

See `glossary.md`, `patterns.md`, `cheatsheet.md`, `chapters/`.
