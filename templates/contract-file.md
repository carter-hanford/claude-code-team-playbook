# {{FILE_TITLE}} · contract file

<!-- A contract file is the single source of truth for one lane's state. Other seats read it
     instead of asking. Example values in comments are for Potluck's screen spec for the
     RSVP page, owned by Design. -->

> **STATUS · {{YYYY-MM-DD}}**
> Owner: {{SEAT}} · Read by: {{SEATS}}
> State: {{ONE_LINE_CURRENT_STATE}}
> Version: `ver={{vX.Y}} status={{iterating|ready}}`
> Waiting on the lead: {{N}} · Waiting on a seat: {{N}}

<!-- e.g. 2026-03-04 · Owner: Design · Read by: Backend, Web + copy
     State: Gate 3 passed, Gate 4 motion in review
     Version: ver=v0.9 status=iterating
     Waiting on the lead: 1 · Waiting on a seat: 0
     When this block and the body disagree, the block wins. Update it in the same edit. -->

## Open items

Every item carries exactly one state.

### {{ITEM_TITLE}}
`WAITING ON LEAD`

{{The question, with the options and this seat's recommendation.}}

<!-- e.g. Does a declined RSVP free the seat instantly, or after the host confirms?
     Recommendation: instantly, with an undo for 10 seconds. -->

### {{ITEM_TITLE}}
`ANSWERED · do not re-raise` · {{YYYY-MM-DD}} · D{{N}}

> "{{The lead's words, verbatim.}}"

Why: {{the reasoning, so nobody re-litigates it}}.

### {{ITEM_TITLE}}
`DEFERRED BY LEAD · do not resurface` · {{YYYY-MM-DD}}

> "{{The lead's words.}}"

### {{ITEM_TITLE}}
`WAITING ON A SEAT` · blocked on {{SEAT}}

{{The action needed, and from whom. The lead cannot unblock this, so it never goes on his
brief.}}

## Standing constraints

Tripwires that must survive even if the question they came from is deferred.

| Fires when | Why it matters | What to do |
|---|---|---|
| {{TRIGGER}} | {{WHY}} | {{ACTION}} |

<!-- e.g. Fires when any line mentions allergies · The product cannot guarantee a dish is
     safe · Route the line to Web + copy for the lead to cut. -->

## Change log

| Date | Change | By |
|---|---|---|
| {{YYYY-MM-DD}} | {{CHANGE}} | {{SEAT_OR_LEAD}} |
