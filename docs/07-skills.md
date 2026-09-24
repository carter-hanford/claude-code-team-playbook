# 07 · Skills

A skill is a folder of instructions a Claude Code session loads when a task matches it. The
team uses two kinds: a public set installed for every seat, and two house skills written for
our own product.

Anthropic's reference for the format: [anthropics/skills](https://github.com/anthropics/skills)

## One install covers every seat

Skills installed in the project's `.claude/skills/` folder are read by every session opened
in that project. One install reached all five seats. Nothing had to be configured per seat.

## The public set

Source: [mattpocock/skills](https://github.com/mattpocock/skills) · MIT. None of its files are
copied here. Install from the source.

| Skill | What it is for on this team |
|---|---|
| `grilling` | Stress-testing a plan with hard questions before anyone builds it |
| `tdd` | Test-first work on anything with logic in it |
| `diagnosing-bugs` | A disciplined loop for bugs that do not fall over on the first look |
| `code-review` | Reviewing a branch against the repo's standards and the spec it came from |
| `domain-modeling` | Keeping the product's vocabulary consistent across seats |
| `codebase-design` | Deciding where a module boundary goes |
| `prototype` | A throwaway build that answers one design question fast |
| `research` | Primary-source research written up as a file in the repo |
| `writing-for-agents` | Writing briefs and skills that another session will follow |
| `resolving-merge-conflicts` | Two seats touching the same file |
| `setup-pre-commit` | Formatting, type checks and tests before every commit |
| `wizard` | Walking the lead through steps only a human can do, such as a vendor dashboard |
| `git-guardrails-claude-code` | Installed, deliberately not invoked. See below |

## Vet a skill like code

A skill is instructions your agents will follow, so it gets the same review as any outside
dependency before it is installed. The checklist used:

| Check | Why |
|---|---|
| Licence | No copyleft surprise in a private repo |
| Does it edit config or permissions? | A skill that changes settings changes every seat at once |
| Does it commit or push on its own? | Nothing leaves the team without the lead |
| Does it fetch instructions from the network? | Instructions that can change after review were never reviewed |
| Any authority-claiming or override language? | A skill should never tell a session to ignore its rules |

Every file in the public set passed. One skill edits settings: `git-guardrails-claude-code`
installs a hook that blocks destructive git commands. It is a good implementation. It would
also block the routine pushes this team makes, and that failure would look like a
permissions problem rather than a hook the team installed on itself. So it sits installed
and unused until the lead decides otherwise.

**Watch for name collisions.** Four skills in the set share names with built-in commands
(`code-review`, `implement`, `research`, `triage`). Know which one answers when a seat types
the name.

## The two house skills

Written in-house for our own product and kept private. Their shape, for anyone building the
same thing:

**A copy-law skill.** Triggers on any customer-facing words, including "just change this
line." Every line carries a state, `PENDING` until the lead cuts it. It holds the list of
phrasings the team never writes and the claims that need a measurement first.

**A ship-check skill.** The verification sequence a seat runs before it says any web work is
done: build, render the real pages, check the console, check the claims against the source.
It exists because every failure it prevents was a small change that looked fine.
