# Outbound Call Flows

Six flows, distinguished by **purpose and audience state**, not by channel. Each is a stage machine with gates. A flow is a control system, not a script — it decides *when* to speak, not just *what* to say.

## Contents

- [The six stages](#the-six-stages)
- [Flow A — Cold outreach](#flow-a--cold-outreach-never-heard-of-us)
- [Flow B — Lead qualification](#flow-b--lead-qualification-inbound-supplied)
- [Flow C — Revival/win-back](#flow-c--revival--win-back)
- [Flow D — Enrichment](#flow-d--enrichment-filling-missing-data)
- [Flow E — Survey/inquiry/investigation](#flow-e--survey--inquiry--investigation)
- [Flow F — Callback/reschedule](#flow-f--callback--reschedule)
- [Stage gates](#stage-gates)
- [Per-call budget](#per-call-budget)

---

## The six stages

Every flow shares these. What differs is which stage can be skipped.

| # | Stage | Purpose | Skippable? |
|---|-------|---------|------------|
| 1 | **Open** | Identify, state reason, cost to them, get permission | Never |
| 2 | **Qualify** | Confirm relevance before spending their time | Only in Flow C/D |
| 3 | **Discover** | 2–4 questions surfacing the real situation | Yes, if already known |
| 4 | **Quantify** | Pain math, in their currency | No, if selling |
| 5 | **Present** | One relevant offer, matched to what they said | Yes, if not selling |
| 6 | **Close** | One explicit ask, then stop | Never |

**Why the gates matter:** an agent that skips stage 1 and 2 spends a stranger's time before establishing relevance, which is both rude and the main reason people hang up. An agent that never reaches stage 6 wastes a call it didn't pay for.

---

## Flow A — Cold outreach (never heard of us)

**Load:** `technique-01-research-survey.md` · **Typical length:** 2–5 min
**Target:** a real conversation that qualifies itself out or in.

```
1 Open      "Hi, this is [Name] from [Entity]. Bit of an unexpected call —
             I'm running a short survey about how [their kind of business]
             handles calls. Two minutes — is now okay?"
                    │
                    ├── NO ──────────────→ polite close + referral ask → END
                    │
                   YES
                    ↓
2 Qualify   "Quick one first — is [Company] still [what they do]?"
                    │
                    ├── WRONG NUMBER ──→ apologize, ask how to reach them → END
                    ├── NOT THE DECISION MAKER
                    │                   → "Are you the right person for this,
                    │                      or is there someone better?"
                    │                        ├── yes → continue
                    │                        └── referral ask → END
                    ↓
3 Discover  2–4 questions. Listen for the pain, don't pitch yet.
            Budget: 4 questions max before they lose interest.
                    ↓
4 Quantify  Do the math out loud with *their* numbers.
                    │
                    ├── NO PAIN/NOT A FIT ──→ "Sounds like you're covered."
                                            → referral ask → END
                    ↓
5 Present   ONE offer, matched to the pain they just described.
                    │
                    ├── INTERESTED ──→ ask for a specific callback time → 6
                    └── PITCH DEFLECTED ──→ "Totally fair" + referral → END
                    ↓
6 Close     "So I put you down for [day, time] — is that right?"
            Confirm, thank, hang up. Do not re-open.
```

**Key mechanic:** the agent should be talking less than half the call. If you're at stage 5 and haven't had two substantive answers from them, you're pitching to someone you don't understand.

---

## Flow B — Lead qualification (inbound-supplied)

**Difference from A:** they expressed interest, so stage 2 is mostly about budget and timeline rather than relevance.

```
1 Open      "Hi [Name], you asked about [thing] — this is [Name] from [Entity].
             Did I catch you with a minute?"
                    ↓
2 Qualify   Budget bracket · Decision authority · Timeline · Current solution
            ("Are you already using something for this?")
                    │
                    ├── OUT OF SCOPE ──→ honest "not a fit", referral → END
                    ↓
3 Discover  What they've already tried. What broke.
                    ↓
4 Quantify  Cost of the status quo, in their terms.
                    ↓
5 Present   The specific offer that matches the gap they described.
                    ↓
6 Close     Next step: demo/proposal/call back. One ask, with a time on it.
```

**Gatekeeper handling:** an assistant answering first is normal. Don't push past them — get the decision-maker's name and a time. Being polite to a gatekeeper is how you get referred.

---

## Flow C — Revival/win-back

**Load:** `technique-03-revive-and-enrichment.md`
**Difference:** they know you. History is the opening, not something to discover.

```
1 Open      Reference the real prior connection.
            "Hi [Name], it's [Name] from [Entity] — we spoke about [specific
             thing] back in [month]. Did I catch you at a decent time?"
                    │
                    ├── NO REMEMBER/WRONG PERSON ──→ apologize → END
                    ├── HOSTILE ──→ one-line close, suppress → END
                    ↓
2 Qualify   Has anything changed? (usually yes — that's why you're calling)
                    ↓
3 Discover  What's different now. What broke or what's the new priority.
                    │
                    ├── NO CHANGE + NO INTEREST ──→ "Totally fair" → END
                    │                              offer long-term suppression
                    ↓
4 Quantify  Cost of the gap since you last spoke.
                    ↓
5 Present   What is different since last time — this is the whole call.
                    │
                    └── INTERESTED ──→ propose a concrete re-start
```

**Critical:** never reference prior history you don't actually have. Saying "following up on our chat about your Q3 goals" when no such chat occurred is a fast, permanent loss of trust.

---

## Flow D — Enrichment (filling missing data)

**Purpose:** capture structured fields (budget, decision maker, timeline) to improve routing or a later sales call. Not a pitch.

**Load:** `technique-03-revive-and-enrichment.md`

```
1 Open      "Hi [Name], [Entity] here. Quick data check — we're updating our
             records and you're missing [field]. Takes 30 seconds, okay?"
                    │
                    ├── NO ──→ "No problem, thanks anyway." → END
                    ↓
2 Qualify   Skip — they already know you
                    ↓
3 Discover  3–5 short, specific questions. One at a time.
                    │
                    ├── "Why do you need this?" ──→ answer in one sentence, move on
                    ↓
5 Present   Skip — no pitch
                    ↓
6 Close     "That's everything, thanks — really appreciate it."
```

**The temptation to avoid:** enrichment calls are an easy place to slide into a pitch because you now have the recipient's attention. Don't. An enrichment call that pitches is a cold call with a false introduction and the recipient notices the shift. Bank the data; sell on the next call, when you actually know something.

---

## Flow E — Survey/inquiry/investigation

**Load:** `technique-04-survey-and-inquiry.md`

```
1 Open      State: who, what, how long, that responses are confidential/anonymous
                    │
                    ├── NO ──→ polite exit, no referral ask (not a sales call)
                    ↓
3 Discover  The survey instrument. Neutral questions. No steering.
                    │
                    ├── Recipient volunteers info beyond the survey
                    │   → note it, don't exploit it
                    ↓
5 Present   Skip unless the survey explicitly invited it at the end
                    ↓
6 Close     Thank them, offer results if promised, end.
```

**The rule that makes this work:** a pitch inside a survey destroys the value of the survey *and* the reputation. If an offer is genuinely appropriate, it is appended at the end, clearly separated after the last question and takes one sentence. No technique in this skill permits more.

---

## Flow F — Callback/reschedule

Reached someone who said "call me later". This is a **win**, not an obstacle.

```
1 Open      "Hi [Name], this is [Name] from [Entity]. You asked me to call
             back — is now still a good time?"
                    │
                    ├── NOT NOW ──→ agree a specific time, confirm, END
                    ├── BAD TIME ─→ agree a specific time, confirm, END
                    └── NOW ─────→ transfer to Flow A/B/C at current stage
```

Never "circle back". Convert every reschedule into a **specific day and time**, read it back and confirm. An unconfirmed reschedule converts to a lost lead.

---

## Stage gates

Gates are conditions that change what the agent may do next. They are what stops a flow from running off its rails.

| Gate | Condition | Action |
|------|-----------|--------|
| Consent | DNC/permission unknown or negative | Do not dial |
| Hours | Outside recipient's local permitted hours | Defer to permitted window |
| Identity | "Are you a bot?" | Disclose truthfully, then honor reaction |
| Opt-out | Clear refusal or suppression signal | One-line close, suppress, end |
| Wrong number | Not the intended recipient | Apologize, do not pitch, ask for correct contact |
| Gatekeeper | Assistant, not decision maker | Get name + time or referral |
| Off-script | Utterance matches nothing | Confirm understanding, don't improvise an offer |
| Unavailable | LLM or tooling down | Apologize, offer callback, hang up cleanly |

**On off-script input:** the correct behavior is to ask "just to check — did you mean X?" rather than to fill the silence with a guess. Fabricating continuity is how an agent ends up promising something it can't deliver.

---

## Per-call budget

Rough ceilings that keep calls inside human conversational limits:

| Parameter | Value | Rationale |
|-----------|-------|-----------|
| Target duration | 90–300s | Longer than 5 min and you're not qualifying |
| Agent talk share | ≤ 40% | They must outnumber you for discovery to work |
| Questions before pitch | ≤ 4 | Beyond that, interest drops sharply |
| Discovery questions | 2–4 | Each should be answerable in one sentence |
| Offers presented | 1 | Two offers means neither is chosen |
| Explicit asks | 1 per call | Two asks means one is ignored |
| Max turns to bail | 2 consecutive silences after a close | Politely exit |

**On maximum call length:** a long call isn't automatically a good call. The agent that knows when to stop is the one people answer to twice.