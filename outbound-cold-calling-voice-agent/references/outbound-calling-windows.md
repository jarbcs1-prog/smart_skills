# Outbound Calling Windows

The point of calling-hour rules is to avoid waking people. That means the window
has to be evaluated in **the recipient's local time**, not yours.

## The Problem

An account-level time window calls a contact in Auckland at 02:00 because your
account is set to Europe/London. Most dialling platforms expose a single window
per workflow or per campaign, so a naive configuration silently violates the rule
for most of the world.

The fix is to derive the permitted window per call from the recipient's
timezone and evaluate it at dial time.

---

## Baseline Window

**09:00–20:00 local, Monday–Saturday**, excluding public holidays.

This is a widely accepted marketing baseline. Some regimes and industries are
stricter — healthcare, financial services and gambling often require narrower
windows and some jurisdictions exclude Sundays entirely. When in doubt, use the
narrower window; it's the defensible choice.

---

## Why the Narrow Window Matters

Every recipient is a person who did not ask to be called. The marginal call made
at 20:01 costs you almost nothing in revenue and costs the recipient something
real. Narrow windows are also the first thing recipients complain about, and
complaints are what escalate into regulatory attention.

---

## Implementation Pattern

**Branch on the recipient's timezone, evaluate locally at dial time.**

```
BEFORE DIAL:
    tz = recipient.timezone            # from lead record, else derive from country
    if tz is unknown:
        defer to next permissible window for the best available estimate

    local_hour = now_in(tz)
    local_day  = day_of_week_in(tz)

    permitted = (09:00 <= local_hour < 20:00)
                and (local_day is not Sunday)
                and not public_holiday(tz)

    if not permitted:
        defer; do NOT dial
```

Three properties matter here:

1. **Fail closed on unknown timezone.** If you don't know where they are, don't
   guess the window — defer. Guessing means some fraction of calls land at 3am.
2. **Evaluate at dial time, not schedule time.** A campaign queued at 08:00 may
   dial at 11:00. Check at the moment of dialing.
3. **Never "best effort" it.** If the window fails, the correct action is to
   defer. There is no partial credit.

---

## Handling the Queue

Deferring creates a queue that must drain. Practical approaches:

| Approach | Use when | Trade-off |
|----------|----------|-----------|
| **Region-based branches** | Fixed set of regions, stable lists | Simple; breaks on rare timezones |
| **Per-recipient derived window** | Mixed international lists | Correct; needs reliable tz data |
| **Batch by region** | Large volume, few regions | Efficient; requires re-bucketing |

Most lists are homogeneous enough that batching by region works well and is far
cheaper to operate. Derive the window per recipient when the list is genuinely
international.

**Re-queue rule:** if a call defers, reschedule into the next permitted window
for that recipient rather than "in 30 minutes". Otherwise the same call keeps
deferring and you burn attempts.

---

## Do-Not-Call Time Preferences

Some registries let a recipient specify preferred hours and some
jurisdictions treat violating a stated preference as a separate violation. If a
preference is recorded for a number, it outranks your campaign default.

---

## Emergency and Exemption Cases

Genuine emergencies, existing-customer service calls and explicit prior
consent to be contacted at any time may fall outside the standard window. Treat
those as documented exemptions with a recorded reason, not as an option you take
when you need the numbers.

If your workflow relies on exemptions routinely, the window design is wrong.

---

## Public Holidays

A public holiday is a strong signal not to call, even where the legal window
allows it. Treat holidays per-recipient (they differ by country and region) and
exclude them by default.

---

## Pre-Launch Checks

- [ ] Window evaluated per recipient, not per campaign
- [ ] Unknown timezone defers rather than guesses
- [ ] Checked at dial time, not schedule time
- [ ] Sundays excluded
- [ ] Public holidays excluded per region
- [ ] Defers reschedule into the next permitted window
- [ ] Recorded do-not-call time preferences outrank campaign defaults
- [ ] Any exemption is documented with a reason