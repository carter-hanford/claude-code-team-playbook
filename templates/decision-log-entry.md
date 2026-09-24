# Decision log entry

<!-- Copy one block per decision into DECISIONS.md, newest at the top.
     Never edit the lead's quoted words. Superseded entries stay, marked. -->

```markdown
### D{{N}} · {{SHORT_TITLE}}
{{YYYY-MM-DD}} · Decided by {{LEAD_NAME}} · proposed by {{SEAT_OR_LEAD}}
{{STATE}} · supersedes D{{N}} · superseded by D{{N}}

> "{{The lead's words, verbatim.}}"

Why: {{the reasoning, in one or two sentences}}.

Standing constraint (if any): {{a tripwire that must survive even if this is later deferred}}.
```

## Filled in, for Potluck

```markdown
### D15 · Reminder channel for v1
2026-03-02 · Decided by the lead · proposed by Backend
ANSWERED · do not re-raise · supersedes D9

> "Email only for v1. SMS when someone asks for it twice."

Why: SMS brings a paid provider and a consent flow for a feature nobody has requested yet.
```

## States

| State | Use when |
|---|---|
| `WAITING ON LEAD` | Only the lead can decide it |
| `ANSWERED · do not re-raise` | Decided |
| `DEFERRED BY LEAD · do not resurface` | Parked on purpose by the lead |
| `WAITING ON A SEAT` | Blocked on a teammate's action |
