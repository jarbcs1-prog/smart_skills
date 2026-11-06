# Technique 04 — Survey, Inquiry & Investigation

**Best for:** genuine market research, satisfaction surveys, NPS follow-ups,
support investigations and pre-qualification questionnaires.

**When NOT to use:** selling to someone (use `technique-01`) or collecting CRM
fields for routing (use `technique-03` part 2).

---

## Core Philosophy

**A survey that pitches is not a survey.** The moment you sell inside a research
call, you lose the responses you were gathering — participants become
distrustful and the data gets biased toward whoever was willing to hear a pitch.

This is the only technique in this skill where the commercial element is
structurally subordinate. That constraint is what makes it useful: people give
honest answers when they believe the survey really is a survey.

---

## Why Surveys Get Answered

Most people refuse a call because they assume it's a sales call. Three things
change that:

1. **Say what it is, precisely.** Not "we'd love your feedback" — that reads as
   a cover. "A ten-question survey about X" is concrete and checkable.
2. **Bound the time.** "About four minutes" is a complete sentence; a question
   is not.
3. **Say who benefits.** "The results get published" or "it feeds our
   product roadmap" gives a reason to answer honestly.

---

## The Opener

```
"Hi [Name], this is [Name] from [Entity]. I'm calling with a short survey
about [specific topic] — about [n] questions, [time] minutes. Would now
suit you?"
```

Include, where the regime requires it, that it's an automated call and that the
call may be recorded.

### If They Hesitate

```
"It's genuinely just research — nothing to buy. If it's a bad time I can call
back or you can skip it entirely."
```

### If They Say No

```
"No problem at all — thanks for your time."
```

**Then stop.** No referral ask here. A referral request converts a clean exit
into a sales interaction and, in survey work, biases future participation.

---

## Asking the Questions

Neutrality is the whole discipline.

**Never lead.** "Don't you think response time matters more than price?" tells
them what you want to hear. Ask "how important is response time to you, on a
scale of one to ten?"

**Vary the scale.** Always-positive scales produce flat answers. Include scales
that run the other way or mid-point scales, to break acquiescence bias.

**Hold the instrument steady.** Don't adapt questions mid-call based on what you
want the answer to be. If the instrument is dynamic, that should be a known
design choice, not an improvisation.

**Where the answer is sensitive**, the person may not want to say it on an
outbound call. Offer to skip or offer anonymity if you can genuinely deliver it
— don't imply confidentiality you haven't arranged.

---

## Recording Answers

| Field | Purpose |
|-------|---------|
| `question_id` + `raw_answer` | The data itself |
| `answer_value` | Parsed where a scale/number was used |
| `skipped` | Explicit non-answers — these are data, not nulls |
| `free_text` | Verbatim, unedited |
| `sentiment` | Optional and only if genuinely derived |

**Don't over-parse.** An LLM summarising a free-text answer into a categorical
value loses the nuance that made the answer interesting. Keep raw and parsed
side by side.

---

## Survey Outcomes

```
ANSWERED ──────────→ thank them, confirm what happens to the data, END
PARTIAL ───────────→ "That's enough, really — thanks." Do not finish the form.
REFUSED ───────────→ "Completely fine, thanks for your time." → END
VOLUNTEERED EXTRA ──→ listen, note it, don't convert it into a pitch
VOICEMAIL ──────────→ leave the survey reason + callback or hang up cleanly
```

---

## Appending an Offer (Rarely)

If the entity genuinely has something relevant and the survey instrument
explicitly invited follow-up, it may be appended — after the final question,
clearly separated, in one or two sentences, with no follow-up pitch:

```
"That's everything — really helpful, thank you. One last thing: we're running
[offer] at the moment if it's useful. Would you like the details?"
```

**Never** do this when:
- the survey is anonymous or independent research
- the recipient showed any reluctance
- the offer wasn't mentioned in the instrument
- they asked about what happens with their answers

The consent for research participation does not extend to subsequent marketing.
That distinction is exactly why surveys that pitch become complaints.

---

## Investigation & Inquiry Calls

When the call's purpose is to investigate an issue rather than gather opinion:

- **Establish legitimacy first.** "I'm calling about the issue you reported on
  [date] — this is [Name] from [Entity]'s support team."
- **Collect facts, not opinions.** Dates, references, what was observed.
- **Don't troubleshoot on a cold outbound call.** You lack context, the person
  has no incentive to cooperate and you'll make it worse. Take the reference
  and call back from the proper channel.
- **Never request credentials.** If verification is needed, route to the normal
  verification channel and end the call.

---

## Common Failure Modes

| Failure | Cause | Fix |
|---------|-------|-----|
| "Is this a sales call?" | Opener vague about purpose | Name the topic and the question count |
| Short, useless answers | Leading questions | Ask neutral, non-loaded versions |
| Pitch slipped in mid-survey | No hard gate | Append-only, at the end, one sentence |
| Data unusable | Over-parsing | Keep raw verbatim alongside parsed values |
| Refused and annoyed | Referral ask on a refusal | Surveys get clean exits, no asks |
| Responses biased | Agent "helpfully" rephrasing | Hold the instrument fixed |