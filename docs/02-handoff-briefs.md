# 02 · Handoff briefs

Every seat has one brief, `HANDOFF-<seat>.md`, in the repo root. It is the first thing the
session opens, every time, on the words "read your handoff document." It answers one
question: **what am I, here, today.**

Template: [`templates/HANDOFF-seat.md`](../templates/HANDOFF-seat.md)

## What goes in one

| Section | What it holds | Why |
|---|---|---|
| **Pickup point** | A dated snapshot of where the seat's work stands right now | A fresh session picks up mid-stride instead of re-reading history |
| **Scope** | The lane, in one paragraph, plus the edges shared with other seats | The edges are where collisions happen |
| **Inputs** | Every file this seat reads, and which seat owns it | A seat reads the source. It never asks for something a file already holds |
| **Outputs** | Every file this seat writes, and who reads it | Other seats build on these. Accuracy matters as much as for code |
| **Gates** | Which gates this seat runs, and what closes each one | So nothing reaches the lead half-finished |
| **Must never** | The short list of things this seat is not allowed to do | The list that prevents the expensive mistakes |
| **Rituals** | The checks the seat runs before reporting anything | Verification is a habit, so it gets written down |

## Rules for writing one

**Short.** A brief that takes ten minutes to read gets skimmed. Depth goes in a separate,
longer document that the brief links to.

**Every rule carries its why.** A seat that understands the reason applies the rule
correctly in situations the brief did not anticipate. A seat that only knows the rule
applies it literally and misses.

**The must-never list is specific.** "Be careful with the API" teaches nothing. "Never change
a response shape without bumping the contract version first" prevents a real failure.

**Dates are absolute.** Never "yesterday" or "last sprint". The brief will be read by a
session that has no idea when "yesterday" was.

## No seat exists until its brief exists

A seat described only by a row in a charter table cannot start itself. The opening line
only works if the document it points at is there, and that hole stays invisible until a
session opens and finds nothing addressed to it.

**Day-one check:** count the briefs, count the seats in the charter. The numbers match, or
the team has a hole in it.

## Two documents per seat

| Document | Is | Travels |
|---|---|---|
| `HANDOFF-<seat>.md` | Short and local. This project, this seat, today | Stays with the project |
| `manifestos/<seat>.md` | Long and portable. How this seat works anywhere, including its mistakes | Moves to the next project |

A new project copies the manifestos and writes fresh handoffs.
