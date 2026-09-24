# 04 · Gates and sign-off

Work moves through numbered gates. Each gate has one deliverable, one kind of review, and a
named way to close it. Nothing reaches the lead half-finished, and nothing leaves the team
without the lead's tap.

## The five gates, for a Potluck screen

| Gate | Deliverable | What the lead reviews | What closes it |
|---|---|---|---|
| **1 · Spec** | The written spec, before any pixels | Wrong decisions, missing decisions | Redlines in words and numbers |
| **2 · Technique** | The make-or-break element alone, at full quality, in several states | Does the core idea read? | Approve it, or name the specific failure |
| **3 · Full static** | The whole screen, every state shown | Layout, craft, every item against the spec | A pass or fail per checklist item |
| **4 · Interaction** | Motion and behaviour, live and clickable | Feel and restraint | Named timings and values |
| **5 · Handoff** | Measurements, assets and notes the next seat builds from | Nothing. This one is delivery | The receiving seat confirms it builds |

**Gate 2 exists on its own for a reason.** The one element that makes a screen work gets
proven alone, before layout surrounds it. That prevents a full rebuild when the core idea
turns out not to read.

## Redlines

A redline is specific enough to act on without a follow-up question.

| Useful | Useless |
|---|---|
| "The RSVP button is 4 px too low. Align its baseline with the guest count." | "The button feels off." |
| "The empty state needs the host's name in it." | "Can the empty state be warmer?" |

**Gates are cheap to reopen.** A screen can go through ten revisions in one sitting when each
revision is viewable and each redline is specific. A seat never defends a gate. It rebuilds.

## Status markers

Every artifact carries its version and state where the next seat will see it, for example in
the spec's status block:

```
ver=v0.4  status=iterating      (the lead is still redlining)
ver=v1.0  status=ready          (signed. The next seat may build from it)
```

A seat only builds from a `ready` artifact. That one field is what stops two seats working
from two different versions of the same screen.

## The tap nothing skips

Four things never happen without the lead:

1. **A release.** The release script runs when the lead says so.
2. **A post.** Media loads the queue. The lead releases every post, one tap each, and nothing
   is ever scheduled to fire on its own.
3. **Customer-facing words.** Every line in the copy bank is `PENDING` until the lead cuts it.
4. **Anything public.** A new public repo is built private first and flipped on the lead's
   word.

## A gate states what it covers

A gate that passes feels like proof. Write down what it actually checks, in the gate's own
words. A validator described as "the gate" that only covers one build target of two leaves
the other target checked by nothing, and nobody notices, because the gate keeps passing.
