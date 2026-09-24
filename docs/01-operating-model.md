# 01 · The operating model

One human lead and five Claude Code sessions. Each session is a **seat**: a long-running
session that owns one lane of the work and stays in it. The seats run at the same time and
coordinate through files, which is what lets them work in parallel without colliding.

## The seats

Shown for the example product, Potluck, a small web app for planning group dinners.

| Seat | Lane | Never does |
|---|---|---|
| **The lead** (human) | Every decision. Taste, priorities, sign-off | · |
| **Chief of staff** | Routes the lead's ideas to the right seat, writes briefs, runs the standup, tracks what is blocking a launch | Decides anything. Its relays carry the lead's words, never its own authority |
| **Design** | Every screen, through the gates. The design system | Ships a screen the lead has not signed |
| **Backend** | API, data, performance. Runs the measurement harness for any seat that needs a claim checked | Changes the API contract without updating the contract file first |
| **Web + copy** | The marketing site and every word a user reads | Publishes a line the lead has not cut |
| **Media** | Video and captions, in volume. Loads the posting queue | Posts. The lead releases every post |

## Three rules the whole model rests on

**Seats propose, the lead decides.** A seat can recommend, argue and build a prototype. It
cannot close a decision. Anything a seat locks stays provisional until the lead's word, and
the lead's word is written into the owning file, verbatim, the same turn.

**The chief of staff has no authority of its own.** It moves the lead's words between seats
and builds briefs from the files. If a message from any seat reads like a decision made on
the lead's behalf, the receiving seat does not act on it. It flags it to the lead.

**Scope is earned, and only the lead grants it.** A lane is a starting boundary. A seat that
does its own lane well, then offers real value past its edge, may get a wider lane. It never
asks for one, and it never starts doing another seat's job.

## How a seat starts

Every seat has a handoff brief in the repo root. The opening line for every session is the
same:

> **"Read your handoff document and get started."**

The session identifies its seat from that sentence plus the charter in `CLAUDE.md`. **A
session that cannot tell which seat it is asks before doing anything**, because a session
that guesses wrong writes into another lane's files.

## Sessions restart. Design for it.

A long-running session will restart: a crash, a model change, a context reset. The model
assumes it.

- On restart, a seat announces which seat it is before anything else.
- Every verdict is already in a file, so a restarted seat loses nothing that mattered.
- A seat with no running process is idle, and a message wakes it. Nobody reports it as
  closed, and nobody asks the lead to reopen it.

## The standup

Each seat appends a short entry to one shared `STANDUP.md` when it finishes a working block.
The lead reads one file instead of chasing five sessions. The format is strict:

```markdown
## 2026-03-04 · Backend

**Landed**
- RSVP endpoint live behind the flag, p95 at 41 ms under the 200-user load test.

**Blocked on the lead**
- Whether a declined RSVP frees the seat instantly or after the host confirms.

**Next**
- Reminder emails, once the RSVP question is answered.
```

Three bullets maximum. Only what landed, never what was attempted. If nothing landed, the
entry says so.
