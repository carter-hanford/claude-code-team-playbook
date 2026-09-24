# 06 · The decision log

Every decision is written down, dated and attributed to whoever made it. On this team that is
almost always the lead, which is the point: a log where every line says "the lead" is a log
where no seat decided something on its own.

Template: [`templates/decision-log-entry.md`](../templates/decision-log-entry.md)

## What an entry holds

| Field | Why |
|---|---|
| **ID** (`D14`) | Other files cite it. "Per D14" is shorter and cannot drift the way a paraphrase does |
| **Date**, absolute | A session months later has no idea when "last week" was |
| **Who decided** | Almost always the lead. When a seat proposed it, that goes in too |
| **The words**, verbatim and quoted | The exact wording is the decision |
| **Why** | So nobody re-litigates it |
| **State** | One of the four states from [03](03-contract-files.md) |
| **Supersedes / superseded by** | A decision that replaces another says so in both entries |

## Examples, for Potluck

```markdown
### D14 · Guests RSVP without an account
2026-03-02 · Decided by the lead · proposed by Web + copy
ANSWERED · do not re-raise

> "Nobody makes an account to say they're coming to dinner. Link in, name, done."

Why: every extra step before the RSVP loses guests, and the host only needs a name
and a yes.

---

### D15 · Reminder channel for v1
2026-03-02 · Decided by the lead
ANSWERED · do not re-raise · supersedes D9

> "Email only for v1. SMS when someone asks for it twice."

Why: SMS brings a paid provider and a consent flow for a feature nobody has requested yet.
D9 (SMS and email) is superseded and marked so.

---

### D16 · Dietary tags on the menu
2026-03-04 · Proposed by Design
DEFERRED BY LEAD · do not resurface

> "Good idea, after launch."

Standing constraint lifted out: the copy bank must not promise allergy safety anywhere.
That holds whether or not D16 ever ships.
```

## Rules

**Superseded entries stay.** They get marked `superseded by D15` and left where they are. The
history of why a decision changed is part of the decision.

**A seat never edits the lead's quoted words.** It can add context underneath. The quote is
the record.

**The log is the first thing the chief of staff reads** before building any brief. A brief
built from messages instead of the log eventually tells the lead something he already
decided is still open.
