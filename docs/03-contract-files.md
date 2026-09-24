# 03 · Contract files and the quiet protocol

**A seat that needs to know something reads a file. It does not ask.**

Every lane keeps contract files that are the single source of truth for its state. Other
seats read them on demand. This is the coordination mechanism for the whole team.

Template: [`templates/contract-file.md`](../templates/contract-file.md)

## The file map, for Potluck

| File | Owner | Read by | Holds |
|---|---|---|---|
| `CLAUDE.md` | The lead | Every seat | The charter, locked decisions, the laws |
| `DECISIONS.md` | Chief of staff | Every seat | The decision log |
| `STANDUP.md` | Every seat, own section | The lead | What landed, what is blocked, what is next |
| `api-contract.json` | Backend | Design, Web | Every endpoint and response shape |
| `screens/<screen>-spec.md` | Design | Backend, Web | Each screen's spec, with a status marker |
| `copy-bank.ts` | Web + copy | Design, Media | Every user-facing string, with its state |
| `BRIEF.md` | Chief of staff | The lead | What is waiting on the lead, in priority order |

## Conventions every contract file follows

**A status block at the top.** When the block and the body disagree, the block wins, and
whoever notices fixes the body.

**The block updates in the same edit as the change.** Never afterwards in a cleanup pass.

**The lead's words go in verbatim, quoted and dated.** A paraphrase loses what made it a
decision.

**The why sits next to the what.** A future session either inherits the reasoning or
re-litigates the decision.

**Nothing is decided until it is in the file.** A decision told to a seat in a message and
never written down is gone at the next context boundary.

## The four decision states

Every open item carries exactly one.

| State | Means | Prevents |
|---|---|---|
| `WAITING ON LEAD` | A real decision only the lead can make | · |
| `ANSWERED · do not re-raise` | Decided, and kept visible so nobody reopens it | The lead being asked to decide something twice |
| `DEFERRED BY LEAD · do not resurface` | Parked on purpose. The lead will raise it | Every seat that stumbles on it thinking it is helping |
| `WAITING ON A SEAT` | Blocked on a teammate's action, not a decision | Briefing the lead on something the lead cannot unblock |

**Standing constraints** get their own section. A constraint attached to a deferred question
gets deferred along with it and then fires unnoticed. Written separately as a tripwire (what
fires it, why it matters, what to do) it survives the deferral.

## The quiet protocol

Messages between seats are for three things only:

1. **Handoffs.** Work moving from one lane to another.
2. **The lead's verdicts.** Relayed in his words, once.
3. **Action-needed items.** Something a seat is blocked on.

Everything else lands silently in a contract file. That includes acknowledgements, agreement,
findings, progress reports and anything already committed. **The commit is the delivery.**

**Correct only what changes a decision.** A teammate's error is worth a message only when it
would change what the lead decides or what a seat builds. Wording and classification
disagreements get fixed in the file. One round, never three.

**Check whether the lead is already in the loop.** A relay of something the lead is watching
directly is noise.

## Why this works with Claude Code specifically

Each session has a finite context. Every message a seat receives costs it context, whether
it needed the message or not. Files cost nothing until they are read, and only the seat that
needs them reads them. Five sessions on a quiet protocol can run all day. Five sessions
chatting run out of room by lunch.
