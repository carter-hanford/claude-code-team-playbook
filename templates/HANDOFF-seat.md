# HANDOFF · {{SEAT_NAME}}

<!-- The first file this seat opens, every session, on the words
     "read your handoff document and get started."
     Keep it short. Link to depth instead of pasting it.
     Example values in comments are for Potluck's Backend seat. -->

## Pickup point · {{YYYY-MM-DD}}

{{Two or three sentences: where this seat's work stands right now, and the one thing it picks
up next.}}

<!-- e.g. 2026-03-04 · RSVP endpoint is live behind a flag, p95 41 ms under the 200-user load
     test. Next: reminder emails, blocked on the lead's answer to D17. -->

## Scope

{{One paragraph. What this seat owns, and where its edges meet other seats.}}

<!-- e.g. The API, the data model, performance, and the measurement harness any seat can use
     to check a claim before it ships. Shares an edge with Design at api-contract.json. -->

## Inputs · what this seat reads

| File | Owner | Why |
|---|---|---|
| `CLAUDE.md` | The lead | The charter and the laws |
| `DECISIONS.md` | Chief of staff | What is already decided |
| {{FILE}} | {{OWNER}} | {{WHY}} |

## Outputs · what this seat writes

| File | Read by | Holds |
|---|---|---|
| {{FILE}} | {{SEATS}} | {{WHAT}} |
| `STANDUP.md`, own section | The lead | What landed, blocked, next |

## Gates

| Gate | This seat's deliverable | What closes it |
|---|---|---|
| {{N}} | {{DELIVERABLE}} | {{CLOSE}} |

## Must never

- {{SPECIFIC_FORBIDDEN_ACTION}}
<!-- e.g. Change a response shape without bumping the contract version in api-contract.json
     first. Two seats build against that file. -->
- Decide something that belongs to the lead.
- Push anything public, or anything that reaches users, without the lead's tap.

## Rituals · before reporting anything

1. Verify the artifact exists and says what you are about to claim it says.
2. Write the lead's verdicts into the owning file, verbatim and dated, the same turn.
3. Log the why next to the what.
4. Mark first-pass work that was never validated as `UNPROVEN`, where the next reader will
   see it.
5. Commit and push as decisions land.
