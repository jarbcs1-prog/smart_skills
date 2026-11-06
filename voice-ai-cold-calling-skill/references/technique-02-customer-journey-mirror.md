# Technique 02 — Customer Journey Mirror

**Best for:** the follow-up call where the recipient has already seen a demo,
trial or sample and is deciding.

**When NOT to use:** cold calls (`technique-01` — they have no journey to
mirror), price-first callers, highly technical recipients who will argue with
the analogy or calls under 3 minutes.

**Source:** Katon Walker — post-demo close.

---

## Core Philosophy

**Don't argue them into wanting it. Get them to identify with their own
customers — or their own situation — and reach the conclusion themselves.**

The demo already demonstrated the solution on their terms. Pitching now
undercuts it. Your job is to hold up a mirror so the value becomes their
observation rather than your claim.

---

## Why This Needs Configuring

The original version of this technique walked a **local-trades narrative**:
"when you need a plumber, where do you search? … they call the first one that
answers." That is a specific buyer journey — high-consideration, low-involvement,
phone-first, winner-take-most.

**That journey does not generalise.** A procurement officer buying an ERP system
does not shop the way someone finds a plumber. Neither does a homeowner choosing
a retrofit, a practice choosing a payroll provider or an NHS trust choosing a
supplier.

So the *structure* is general and the *journey* is not. Configure the journey;
keep the structure.

---

## The Structure

Five moves. The journey content fills them; the moves are the same every time.

```
1. ESTABLISH THE SEARCH PATH      →  "how do people like you normally find X?"
2. ESTABLISH THE SELECTION CRITERIA →  "what makes you pick one over another?"
3. ESTABLISH THE VOLUME           →  "how many do you usually approach?"
4. ESTABLISH WHAT HAPPENS ON SILENCE →  "and if they don't come back?"
5. THE MIRROR + LOCK + CLOSE      →  "so would you say that applies to [their
                                       customers/team/colleagues] too?"
```

The recipient supplies the answers. You supply the structure and the reflection.

**Why volume matters:** it establishes that switching costs are real, which is
the obstacle you're actually removing. Someone evaluating one option has nothing
to decide.

**Why the silence step matters:** almost everyone loses potential buyers to
non-response. This is where you find out whether that's happening to them, and
it nearly always is — because it happens to everyone.

---

## Configured Journeys

Each pitch record supplies a journey. Four starting points:

### Local/consumer services (the original)

```
1. "When you need a [service], where do you usually start?"
2. "What makes you choose one over another?"
3. "Do you call more than one?"
4. "And if they don't answer?"
5. "So it goes to whoever gets there first?"
```

### B2B/considered purchase

```
1. "When a business like yours needs [capability], where does it usually start?"
2. "What tends to make you shortlist one over another?"
3. "How many do you normally evaluate?"
4. "And what happens when a promising one doesn't come back?"
5. "So the ones who respond properly are effectively shortlisted already?"
```

This version works because it lets *them* articulate their own procurement
criteria — and then you show the offer matches them, rather than you asserting
it does.

### Regulated/high-trust (health, finance, legal)

```
1. "When people need [service], how do they usually go about finding someone
    they trust?"
2. "What makes someone feel safe to go with?"
3. "Do they look at more than one?"
4. "And if someone doesn't get back to them?"
5. "So responsiveness is part of what makes them feel safe?"
```

Here the closing lock is on **trust and responsiveness**, not convenience. Be
especially careful not to imply any regulated status you don't hold.

### Internal/stakeholder sell

```
1. "When this kind of thing comes up internally, how does it usually start?"
2. "What tends to get it moving?"
3. "Does it involve more than one person?"
4. "What happens when it stalls?"
5. "So a clear proposal tends to be what unblocks it?"
```

For sales into a team rather than a customer, the mirror is reflected onto their
**internal process** rather than their buyers. Often the most useful version,
because the real blocker is internal consensus rather than the offer.

---

## Step 5 — The Mirror, Lock, Close

Once they've described their own journey, reflect it back:

```
"So it would be fair to say that [their customers/team] behave the same way?"
```

```
"And that where [X] isn't handled well, those opportunities tend to go to
[whoever/whoever else] instead?"
```

```
"So let me ask you — is there a reason you wouldn't want to close that gap?"
```

**Then stop.** This is the moment. Don't fill the silence, don't soften it, don't
add reassurance. Let them arrive at it.

---

## Response Handling

| They say | Do this |
|----------|---------|
| "No reason" | "That's what we thought. Let me walk you through what getting started looks like." |
| Hesitate | "What's holding you back — price, setup, timing or something else?" |
| Price before the mirror | "We will get there — one quick question first, so I can make sure this is actually right for you." |
| "Already have something" | "How's it performing? Any gaps?" |
| Go quiet | Wait. Then: "Have I lost you?" |

**On "we've already got one":** satisfied customers mentioning a gap is where
upsell lives, but don't assume there is one. Ask and mean it.

---

## When NOT to Use

| Situation | Why | Instead |
|-----------|-----|---------|
| Cold contact | No journey exists yet | `technique-01` |
| Technical buyer | Will debate the analogy | Talk about their stack |
| Already has your category | Journey is settled | Probe for the gap |
| Complex multi-stakeholder | Five moves won't survive the politics | Multi-threaded planning |
| Under 3 minutes | No room for five moves | Compress to 3 + close or defer |
| Price-first | Wants numbers | Qualify budget, then close |
| Regulated and you can't evidence the claim | Analogy implies a status you don't hold | Use `technique-01` |

---

## The Full Sequence

```
1. TECHNIQUE 01 — cold call
   research survey → name the pain → offer something concrete to see

2. BUILD — between calls
   personalise to their actual situation so the next call isn't abstract

3. TECHNIQUE 02 — follow-up
   journey mirror → they reach the conclusion → one ask

4. CLOSE
   one concrete next step, with a time on it
```

The gap between step 1 and step 2 is where these calls usually fail. Running a
mirror before anything was built or demonstrated feels like a trick and people
notice. The demonstration earns the right to run the mirror.

---

## Adding a Journey to a Pitch Record

```yaml
pitch:
  audience_type: "b2b-considered"        # maps to a journey
  journey:
    step1_search: "When a practice like yours needs {capability}, where does it start?"
    step2_criteria: "What makes you shortlist one over another?"
    step3_volume: "How many do you normally evaluate?"
    step4_silence: "And what happens when a promising one doesn't come back?"
    mirror_subject: "your patients"      # customers/team/colleagues
    lock_outcome: "responsiveness as part of feeling safe"
    close: "is there a reason you wouldn't want to close that gap?"
```

Verify every assertion the journey produces is one the entity can actually
stand behind. A mirror that ends in a claim you can't evidence is worse than no
mirror — it's the moment trust breaks. See `outbound-compliance.md`.