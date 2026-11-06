# Pitch Type Routing

Which structures and questions work for which kind of offer. Load this when you need to configure a pitch or pick an approach for an unfamiliar offer type.

The mistake this file exists to prevent: taking one offer's questions and applying them to another. A missed-calls discovery question is nonsense to someone being offered an EPC retrofit, a software license or a research survey.

---

## Identify the offer type first

| Signal | Likely type |
|--------|-------------|
| Recipient has never heard of you, single decision-maker, short call | **Cold transactional** |
| Multiple people involved, long cycle, formal evaluation | **B2B considered** |
| Repetitive low-value need, timing matters (repairs, replacements, emergencies) | **Trigger/event-driven** |
| Reconnecting with past contact or existing customer | **Revival** → `technique-03` |
| The recipient's opinion or behavior is the data | **Survey/research** → `technique-04` |
| Regulated claim, trust-gated (health, finance, legal) | **Trust-gated** |
| Internal audience, you need an internal champion | **Internal sell** |
| Owed money or a commitment already exists | **Recovery/compliance-heavy** |

Mixed is normal. A call can be event-driven *and* trust-gated. When it is, pick the structure from the **harder** constraint — trust gating usually wins, because it constrains what you can claim.

---

## Cold transactional

**Profile:** low to moderate value, short cycle, unsophisticated buyer, immediate problem.

**Structure:** SPIN, moving fast. Situation → Problem → Implication → Need-payoff.

**Question budget:** 3–4. They're busy; a long process reads as rudeness.

| Move | Example shape |
|------|---------------|
| Situation | "How many [unit] do you handle a week?" |
| Problem | "What happens when [the specific failure]?" |
| Implication | "So that costs you [X] each time it does?" |
| Need-payoff | "If that stopped happening, how would that sit?" |

**Close:** direct. Low consideration means a long consultative approach is a waste of their time.

**Avoid:** Challenger-style "let me tell you something counterintuitive" — it alienates buyers who just want to buy something ordinary.

---

## B2B considered

**Profile:** larger value, multiple stakeholders, sophisticated buyer, long cycle.

**Structure:** consultative, with Sandler-style upfront qualification.

**Qualify before investing:**

```
"So I don't waste your time — is this something you'd genuinely be looking to change this quarter?"
```

That question is abrasive and it works. It saves both sides from a long conversation nobody wanted.

**Question budget:** 5–7. Sophisticated buyers will engage with substance, but they punish padding.

| Layer | Ask |
|-------|-----|
| Situation | Current process, team, scale |
| Problem | What's actually failing |
| Implication | Cost of that failure — quantify |
| Decision | Who else, what process, what else they'd weigh |
| Timeline | Why now |

**Adapt to technicality:** a procurement officer who uses your vocabulary gets answered in it. Jargon to a sophisticated buyer reads as unprepared.

**Close:** propose a meeting with named attendees, not a purchase.

---

## Trigger/event-driven

**Profile:** something happened that made this relevant now — a failed inspection, an expiring certificate, a lost contract, a deadline.

**Structure:** lead with the trigger, confirm it's real, then move fast.

```
"Has [organization] contacted you about [event] yet?"
```

**Why "has X contacted you" rather than "did you know":** the first assumes
they're receiving the relevant notices, which is usually true and gives them
something to confirm. The second invites "no idea," which wastes a turn.

**Speed matters more here than anywhere.** Trigger-driven intent decays fast.

| Trigger | Urgency |
|---------|---------|
| Failed inspection/compliance deadline | Very high |
| Insurance renewal | High |
| Expired contract | High |
| Equipment breakdown | High |
| Vehicle due for service | Medium |

**Close:** same-day or next-day. Offering "next week" to someone with a
deadline is offering to lose the deal.

---

## Trust-gated

**Profile:** health, finance, legal, insurance, care, safety — anything where
the buyer needs to believe you're competent and safe before they can hear a
pitch.

**Structure:** credibility first and only then discovery. Lead with the
thing that establishes competence — a relevant credential, a concrete fact, a
genuine limitation.

**State a real limitation early:**

```
"I should say up front — we're not the cheapest option and if all you need is
the bare minimum, you probably don't need us."
```

Volunteering this is the strongest trust move available, precisely because
nobody else does it. It also filters bad-fit recipients early.

**Constraints:**

- Never imply regulated status, accreditation or endorsement you don't hold
- Never give medical, legal or financial advice
- Never collect clinical, financial or identity data on a cold call
- Disclose AI nature if asked — see `outbound-compliance.md`

**Close:** reassurance, not urgency. Pressure is exactly what they're braced
against.

---

## Internal sell

**Profile:** you need a champion inside someone else's organization.

**Structure:** the journey mirror reflected **inward**. Don't mirror their
customers — mirror their internal process.

```
"When this comes up internally, how does it usually start?"
"What tends to get it moving?"
"Does it usually involve more than one person?"
"What happens when it stalls?"
```

**Why this works:** the real obstacle in internal deals is almost never the
offer. It's consensus. Making them articulate the internal bottleneck gets you
useful information *and* positions you as someone who understands their
organization rather than someone trying to sell.

**Close:** a next step that helps them sell internally — a summary they can
forward, a one-pager, an introduction to someone senior.

---

## Recovery/compliance-heavy

**Profile:** the recipient already owes something or there's a prior commitment.
Legally and ethically the most constrained category.

**Hard rules, no exceptions:**

- Identify the business clearly and state the purpose in the first sentence
- Never threaten, never pressure, never use shame
- Verify identity before disclosing any detail about their account
- Never collect payment details — route to the proper channel
- Honor any request to stop, immediately and permanently

**Tone:** matter-of-fact and brief. The longer the call, the more it resembles
harassment.

**Close:** a specific, easy next step — a payment route, a callback with an
actual department or a clean exit. Not a decision under pressure.

**Verify your legal basis before running any call in this category.** This skill
provides conversation structure, not regulatory guidance.

---

## Configuring the Pitch Record

Whatever the type, the record needs:

```yaml
pitch:
  name: "..."
  offer_type: "cold-transactional"      # routes to structure
  audience: "..."
  fit_check: "..."                       # wrong-person/wrong-number guard
  questions:
    opening: ["..."]
    diagnosis: ["..."]
    consequence: ["..."]
    context: ["..."]
  journey: {...}                          # technique-02
  value:
    metric: "hours per week"              # money | time | risk | quantity
    claim: "..."                          # what we can evidence
  proof: [...]
  price: {...}
  never_claim: [...]
```

Full field reference in `persona-and-pitch-design.md`.

---

## Validation

Before a pitch runs:

- [ ] `offer_type` set and the structure matches it
- [ ] Every question is meaningful for *this* offer, not inherited from another
- [ ] Vocabulary translated into the recipient's likely words
- [ ] `fit_check` catches wrong numbers and wrong people
- [ ] For trust-gated: no regulated claims, no advice, no sensitive data
- [ ] For recovery: legal basis verified, payment collection impossible
- [ ] `never_claim` populated for anything regulated or high-risk
- [ ] Journey assertions are all evidenceable by the entity
- [ ] Close matches the urgency of the trigger, if any
- [ ] Every factual claim traces to the entity record