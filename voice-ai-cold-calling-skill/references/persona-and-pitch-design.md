# Persona, Pitch and Entity Design

Four things the agent needs configured before it can call anyone. They are
separate concerns and mixing them is the most common reason agents sound
generic or overstep.

| Component | Question it answers | Where it shows up |
|-----------|---------------------|-------------------|
| **Entity** | *On whose behalf are we calling?* | Name, domain, phone, address, compliance basis |
| **Persona** | *What kind of caller is this?* | Voice, tone, vocabulary, boundaries |
| **Pitch** | *What are we actually offering?* | Offer, proof, price, CTA |
| **Flow** | *What is this specific call for?* | See `call-flows.md` |

---

## Entity — who we represent

The entity owns the facts. Everything the agent says about "us" must trace
back here. Anything not in the entity record must not be invented.

**Minimum fields:**

```yaml
name: "Northgate Energy"
legal_name: "Northgate Energy Ltd"
trading_address: "..."
website: "https://..."
phone: "+44..."
number_status: "A2P-registered"     # or "not-registered"
consent_basis: "implied-b2b-uk"     # governs whether you may dial at all
jurisdiction: "GB"
permitted_hours: "09:00-20:00"
dpo_contact: "privacy@northgate.example"
recording_consent: "notified-at-start"
```

**Why these fields exist:**

- `consent_basis` is what the pre-dial gate reads. Without it the call cannot
  legally be placed, so it belongs with the entity, not in a config comment.
- `number_status` matters because an unregistered outbound number gets flagged
  as spam by recipients, which poisons the domain reputation for every other
  campaign you run.
- `permitted_hours` is entity-specific in some industries and jurisdiction-
  specific in others, so it's data rather than a global constant.

**Replacing an entity** must be a first-class operation. Teams switch agencies,
rename or run campaigns for clients. Support multiple concurrent entities and
make the switch atomic — an agent mid-call that changes which company it
represents is a serious failure.

---

## Persona — what kind of caller this is

Persona is about **how the agent behaves**, not what it knows. Keep them
separate; a persona is reusable across pitches and a pitch across personas.

```yaml
name: "Concise UK B2B SDR"
tone: "warm, brisk, slightly apologetic about the interruption"
vocabulary: "plain English; no jargon; no exclamation marks"
pace: "moderate; short turns; comfortable with silence"
self_disclosure: "automated assistant on behalf of {entity}"
uses_fillers: true
max_words_per_turn: 25
never: ["guarantee", "cheap", "amazing", "revolutionary", "game-changer"]
```

**The persona fields that actually change outcomes:**

- `max_words_per_turn` is the single highest-leverage setting. Long turns are
  the main reason people interrupt or hang up. 15–30 words is the useful range.
- `never` is where you encode the specific words that make your agent sound like
  every other cold call. Review it against real transcripts.
- `uses_fillers` matters more than it sounds. Perfectly articulated speech reads
  as a machine in the first three seconds; natural hesitation reads as human.
- `pace` combined with silence tolerance. An agent that panics and fills every
  pause sounds frantic.

**On personas sounding identical:** if two personas would produce the same call,
they aren't different personas. Test by reading the openings side by side — if
you can't tell which is which from the first sentence, merge them.

---

## Pitch — what we're offering

The pitch is the content. It should be data, not prose in the prompt, so it can
be edited without touching agent code and versioned per campaign.

**There is no single correct pitch shape.** The questions, journey, value
metric and close all depend on what the offer actually *is* — a missed-call
product and an EPC retrofit survey have almost nothing in common beyond "an
offer". That's why the record below carries question banks and a value metric
rather than one fixed script.

```yaml
name: "Retrofit assessment consultation"
offer_type: "trigger-event-driven"      # routes to structure — see pitch-type-routing.md
audience: "UK owner-occupied, EPC band D-F"

# Guard against wrong number/wrong person before spending their time
fit_check: "Is this the property owner? Is the certificate in your name?"

# Question bank — the agent asks 2-4, in the recipient's vocabulary
questions:
  opening:      ["fit_check", "context: when did the certificate come through?"]
  diagnosis:    ["gap: what did the report flag?", "prior attempt: have you had quotes?"]
  consequence:  ["value: what would improving it add to the property?"]
  context:      ["timing: any deadline on this?"]

# Only used when technique-02 applies
journey:
  step1_search: "When people look at improving their home, where do they start?"
  step2_criteria: "What makes them trust a company?"
  step3_volume: "Do they get more than one quote?"
  step4_silence: "And if one doesn't come back?"
  mirror_subject: "your other properties"
  lock_outcome: "deadlines being missed because the survey didn't come back"
  close: "is there a reason you wouldn't want to close that gap?"

value:
  metric: "money"                        # money | time | risk | quantity
  basis: "adds [n] to property value"    # must be evidenceable
proof: ["N local installs completed", "average payback per install"]
price: { cta: "book a 20-minute assessment call" }
never_claim: ["guaranteed grant approval", "fixed price before survey", "guaranteed resale uplift"]
```

**Why `offer_type` matters:** it selects the questioning structure, the pace and the close. A trigger-driven offer moves fast; a considered B2B sale qualifies hard. Getting this wrong is the most common cause of a call that was going fine until it wasn't.

**Why the question bank is per-pitch:** inherited questions are the single most
common failure. Asking a missed-calls question to someone considering a major
property improvement is instant disqualification. See `pitch-type-routing.md`.

**The `never_claim` field is not decoration.** It is the boundary that stops a
fluent model inventing a guarantee. Financial, grant, health and legal claims
carry real consequences, so enumerate the forbidden claims explicitly rather
than hoping the model is careful.

**Value metric is often not money.** Some offers are genuinely about time
saved, risk reduced or quantities handled. Forcing a monetary figure onto an
intangible makes the pain math feel like a gimmick. Pick the metric that the
recipient would actually use to justify the decision.

**Pitch-to-persona fit:** a playful persona delivering a regulated claim is a
tone mismatch that reads as untrustworthy. When these conflict, the compliance
wording wins and the persona adapts.

---

## Wiring it together

Order matters. Persona decides voice, pitch decides content, entity decides
facts and permission.

```
[Entity record]  →  consent check  →  permission to dial?
                                      ├── no  → stop
                                      └── yes
[Persona]        →  tone, pace, turn length, banned words
[Pitch]          →  offer type → structure, question bank, value metric, claims
[Flow]           →  which stages apply to this call type
[Lead context]   →  name, company, prior history (only what's actually known)
```

**Precedence when they conflict:**

1. Compliance and consent rules — never overridable by any config
2. Entity facts — the agent may not contradict them
3. Flow gates — decide whether a stage runs at all
4. Pitch content
5. Persona style — lowest priority; persona adapts to the above

A persona setting that conflicts with a compliance rule is a configuration
error, not a judgment call. Validate configs at load time so it fails loudly
rather than mid-call.

---

## Pitch Compatibility

A pitch and a persona are only compatible if **the persona can plausibly be the
entity's representative** for that pitch.

| Pitch requires | Persona must not be |
|----------------|---------------------|
| Regulated or trust-gated claims | Jokey, dismissive or flippant |
| High-ticket considered sale | Brisk to the point of sounding automated |
| Event-driven urgency | Deliberate and unhurried to the point of losing the trigger |
| Recovery or compliance | Anything cheerful or sales-forward |
| Research or survey | Anything that implies a pitch |

When they conflict, change the persona — not the claim and not the compliance.

**On mixing pitches:** one call uses one pitch. A campaign that runs different
offers to different segments should route by segment before the call starts,
not decide mid-call. Switching offers mid-call is one of the clearest ways to
sound automated, because the recipient can hear the config change.

---

## Validation checklist

Run these before any campaign goes live:

- [ ] Entity has a `consent_basis` that matches the target jurisdiction
- [ ] `offer_type` set and the question structure matches it
- [ ] Every question is meaningful for *this* offer — none inherited
- [ ] Question vocabulary matches the audience's likely words
- [ ] `fit_check` catches wrong numbers and wrong people
- [ ] `value.metric` fits the offer — not forced to money
- [ ] `journey` present if technique-02 could apply and evidenceable
- [ ] `never_claim` enumerated for regulated or high-risk offers
- [ ] Persona `max_words_per_turn` ≤ 30
- [ ] Persona `never` list reviewed against real transcripts
- [ ] Banned phrases include every guarantee/scarcity pattern
- [ ] Persona and pitch are compatible per the table above
- [ ] AI disclosure text present and truthful
- [ ] Callback offer exists with a real, staffed destination
- [ ] Gatekeeper variant defined
- [ ] Wrong-number path defined (apologize, don't pitch)
- [ ] Entity switch is atomic and mid-call switching is impossible
- [ ] No persona or pitch text claims facts absent from the entity record
- [ ] Failure path exists for LLM unavailability