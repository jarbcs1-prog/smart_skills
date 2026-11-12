---
name: cognitive-biases-decisions
description: "Kahneman & Tversky prospect theory + human biases diagnostic skill: heuristics, framing, loss aversion, anchoring, availability, overconfidence. Use to identify biases in decisions, debias plans and red-team pricing, messaging and strategies. Triggers: bias, heuristic, framing, loss aversion, anchoring, availability, overconfidence, prospect theory, debias, decision."
---

# Cognitive Biases & Decision-Making (Kahneman & Tversky)

# Evidence & verification (prerequisite)

Before deriving any conclusion or taking any action from this skill, tag every claim with one of:

- OBSERVED - directly heard, seen or recorded
- VERIFIED - independently confirmed via an authorized source
- INFERRED - reasonable conclusion based on available evidence
- HYPOTHESIZED - possible explanation requiring investigation
- UNKNOWN - not established
- CONTRADICTED - conflicts with reliable evidence

Definitions and worked examples: `../evidence-classification.md`.
Verification hierarchy (the order in which to confirm claims): `../verification-hierarchy.md`.
No unverified claim is ever a silent fact; a hypothesis is never promoted to a fact without independent confirmation.

## Core Philosophy
Biases are not bugs to eliminate; they are **predictable distortions** to detect and compensate for. The skill's value is not listing biases (the agent knows them) but **diagnosing which bias is operating in a specific decision and prescribing the debiasing move**.

### Cognitive load exploitation (new)
A person may introduce several apparently unrelated facts, procedures, deadlines and consequences in rapid succession. One objective may be to prevent the other party from evaluating any individual claim properly. This is cognitive load exploitation: overloading the target's processing capacity so that vigilance drops and the target accepts the next claim without scrutiny.

The defensive response is to slow the interaction down, isolate each claim and verify it independently. Do not try to solve the whole situation at once; address one claim at a time.

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

Is the claimant cascading facts, deadlines and consequences in rapid succession?
├── Yes - cognitive load exploitation; SLOW DOWN: isolate each claim and verify independently
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
## Edge Cases & Failure Modes (cont.)

- **Meta-cognition:** thinking about thinking can create second-order errors; validate both levels.
- **Differential diagnosis:** multiple biases can co-occur; isolate each.
- **Task complexity:** simple decisions may benefit from rules of thumb; complex decisions require full analysis.
- **Recovery trap:** successful debiasing may create false confidence; re-scan after important decisions.
- **Process vs. outcome:** bias detection is about process, not outcome; don't judge the quality of a decision by its outcome alone.
- **Cultural variation:** some biases vary by culture (e.g. self-serving bias is weaker in collectivist cultures).


## Detailed Decision Trees

```text
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

Is the claimant cascading facts, deadlines and consequences?
├── Yes - cognitive load exploitation; SLOW DOWN
└── No - proceed
```

## Anti-Patterns (NEVER)

- **NEVER treat heuristics as always harmful** because they are adaptive shortcuts; debias only when stakes are high or the situation is novel.
- **NEVER overcorrect into analysis paralysis** because debiasing has diminishing returns; time-box it and decide.
- **NEVER ignore the reference point** because loss aversion is reference-dependent.
- **NEVER confuse significance with importance** because a statistically significant bias may be practically trivial.
- **NEVER debias without a mitigation** because naming a bias without prescribing a fix is trivia, not a tool.
- **NEVER skip the meta-cognition step** because bias detection requires checking both the decision and the thinker.
- **NEVER report a bias as the whole story** because it's a process indicator, not a complete diagnosis.
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


## Core Reasoning Models

1. **Prospect theory.** Outcomes evaluated relative to a reference point (gains/losses), not final wealth. Losses loom ~2x gains (loss aversion). Risk-averse for gains, risk-seeking for losses.
2. **Heuristics.** Availability (ease of recall), representativeness (prototype similarity), anchoring (first number sticks). Fast, systematically biased.
3. **Framing.** Equivalent info presented differently changes choices ("90% survival" vs "10% mortality").
4. **Overconfidence.** Systematic overestimation of knowledge/ability; illusion of control; hindsight bias.
5. **Confirmation & availability.** Seek confirming evidence; overweight vivid/recent/salient events; ignore long-term trends.
6. **Sunk cost & status quo.** Past investments and current state overweight future decisions.
7. **Social biases.** Stereotyping, attribution error, in-group favoritism.

## Thinking Patterns (Mindset)

- **Before deciding, ask:** "Am I being influenced by a bias?" Run the bias scan first.
- **Before acting, ask:** "What is the reference point?" Loss aversion is reference-dependent.
- **Before concluding, ask:** "Have I checked for confirmation bias?" Seek disconfirming evidence.
- **Before committing, ask:** "Is this a high-stakes or novel situation?" Debiasing is only needed when stakes are high.
- **Before explaining, ask:** "Am I confusing significance with importance?" A statistically significant bias may be practically trivial.
- **Before delegating, ask:** "Who benefits from this decision?" Sunk cost is easiest to spot from outside.
- **Before reporting, ask:** "Is this a process failure or an outcome failure?" Bias detection is about process, not outcome.

- **NEVER over-repeat a bias name without checking the evidence.** One call can be fraudulent; don't wait for a pattern.
## Voice Calibration
Empirical, precise, debiasing-oriented. Names the mechanism; offers concrete mitigation. No moralizing.
---

See `glossary.md`, `patterns.md`, `cheatsheet.md`, `chapters/`.

- **NEVER over-repeat a bias name without checking the evidence.** One call can be fraudulent; don't wait for a pattern.
