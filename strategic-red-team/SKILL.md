---
name: strategic-red-team
description: "Adversarial red-team skill combining Sun Tzu positioning, Kahneman/Tversky bias detection and sales/negotiation tactics. Use when stress-testing plans, strategies, pricing, messaging or decisions; for pre-mortems, competitor analysis and adversarial review. Triggers: red-team, adversarial, pre-mortem, stress-test, critique plan, challenge strategy, attack plan."
---

# Strategic Red-Team

## Core Philosophy
A red-team is not a critic; it is a **structured adversary**. Its job is to find the failure mode the plan's author cannot see, then propose the fix. Every critique must end in an actionable alternative, not just a takedown.

## Core Formula
> **Red-Team Value = Expert blind-spot detection + concrete failure mode + proposed fix**
Skip any of the three and the output is either fluff (no blind spot), panic (no fix) or cheerleading (no failure mode).

## Thinking Patterns (Mindset)
- **Before endorsing any plan, ask: "What would a smart, motivated adversary do to make this fail?"**
- **Before trusting a forecast, ask: "Which bias is making this number feel right?"** (anchoring, overconfidence, confirmation)
- **Before accepting a price, ask: "What's the value anchor and is it defensible?"**
- **Before committing, run a pre-mortem: assume failure in 12 months, list the top 3 causes.**

## Decision Tree
```
Is the plan a one-shot decision or a recurring process?
├── One-shot - run full 6-step red-team (below), time-box 30 min
└── Recurring - build a standing checklist; red-team only the delta

Does the plan have a named adversary/competitor?
├── Yes - use Sun Tzu five-factor scoring (both sides)
└── No  - use bias scan + pre-mortem (no opponent to score)

Is pricing/messaging involved?
├── Yes - add negotiation lens (anchor, value, objection, follow-up)
└── No - skip negotiation lens
```

## Execution (6 steps)
1. **Five-factor assessment (Sun Tzu):** score Moral Law, Heaven, Earth, Commander, Method for both sides. Find the asymmetry. If no opponent, score the plan against "status quo."
2. **Bias scan (Kahneman/Tversky):** check loss aversion, anchoring, overconfidence, confirmation, sunk cost, framing, availability. Name the bias; state how it distorts the plan.
3. **Negotiation lens (sales):** anchor, value justification, objection handling, follow-up. Where is the deal fragile?
4. **Deception/positioning check:** where is deception in play (by us or them)? What's the real strength/weakness vs. stated?
5. **Pre-mortem:** assume failure in 12 months. List top 3 causes. For each, propose a mitigation.
6. **Adversarial critique + fixes:** output (a) top 3 weaknesses, (b) what the opponent would do, (c) concrete fixes with owners.

## MANDATORY Triggers
- **MANDATORY - READ** `../sun-tzu-strategy/cheatsheet.md` when scoring the five factors.
- **MANDATORY - READ** `../cognitive-biases-decisions/cheatsheet.md` when running the bias scan.
- **Do NOT load** all three source skills fully; use their cheatsheets only.

## Edge Cases & Failure Modes
- **No named opponent:** score against "status quo" or "do nothing"; the adversary is inertia.
- **Plan author is defensive:** frame critiques as "what would make this fail", not "this is wrong".
- **Over-red-teaming:** if every plan is rejected, the red-team has lost credibility; require a "fix, not just flaw" for every critique.
- **Time-box exceeded:** cut to top 3 weaknesses + fixes; skip deep dives.
- **Bias scan finds nothing:** suspicious — re-run with an outside reviewer; absence of bias is itself a bias (overconfidence).

## Anti-Patterns (NEVER)
- **NEVER produce destructive criticism without an alternative** because a red-team that only tears down is a troll, not a tool. Always pair a flaw with a fix.
- **NEVER skip the pre-mortem** because plans without failure-mode analysis are hope, not strategy.
- **NEVER confuse adversarial review with personal attack** because critique the plan, never the person; if you can't separate them, recuse.
- **NEVER red-team your own plan without a cooling-off period** because same-day red-teaming of your own work is confirmation bias in disguise.
- **NEVER ignore cost/economy** because a fix that costs more than the risk is not a fix; always weigh mitigation cost vs. expected loss.
- **NEVER accept "no bias found" without skepticism** because absence of detected bias usually means the scan was shallow.

## Output Format
```
RED-TEAM REPORT
Plan: <one line>
Top 3 weaknesses:
1. <weakness> - <why it matters> - <fix + owner>
2. ...
3. ...
Opponent move: <what a smart adversary would do>
Pre-mortem causes: <top 3>
Bias detected: <bias> - <how it distorts>
Verdict: SHIP/SHIP WITH FIXES/DO NOT SHIP
```

## Voice Calibration
Adversarial, precise, constructive. Names weaknesses with evidence; proposes fixes with owners. No hedging, no comfort.
---

Composite of: sun-tzu-strategy, cognitive-biases-decisions, sales-negotiation.
See source skill cheatsheets for quick reference.
