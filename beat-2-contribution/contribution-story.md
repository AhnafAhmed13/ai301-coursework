# Contribution: Cover malformed JSON independently of text validation


Path: `beat-2-contribution/contribution-story.md`

This file is Assignment 5, and it is graded at the path above; a copy kept anywhere else in
the repository is not read. **Keep every section header below under its exact name** — the
format criteria grade exactly that. Your course repo link is the whole submission: no tool
files and no evidence uploads are part of Assignment 5.

**Contribution Number:** [1]
**Student:** TF - Ahnaf Ahmed
**GitHub Username:** AhnafAhmed13
**Issue:** [GitHub issue link](https://github.com/ashrafee-dev/scamshield-api/issues/113)
**Pull Request:** [GitHub PR link, once opened]

One repository, built across units 5 to 8, telling the whole story of your real
contribution. Fill it as you work, not at the end — the sections below ask for evidence that
is far easier to write down as it happens than to reconstruct in the last weekend.

Contribution Number stays `[1]` unless you make more than one contribution this term; it
just numbers them.

---

## Toolkit

Every story section below, from Why I Chose This Issue through Pull
Request, ends with a Toolkit block: which tool did that phase's work
and how you used it, what it produced, what difficulties or
shortcomings it presented, and what you changed or would change
because of them. Together the blocks are the thread the rubric's
Toolkit points read, and they are the raw material for your unit-9
portfolio, so keep them current as you work rather than
reconstructing them later.

A Toolkit block looks like this (copy it into each story section and
fill it there):

```text
**Toolkit**

- Tool: [which tool did this phase's work, and how you used it]
- What it produced: [described in a sentence or a short excerpt]
- Difficulties: [what fought you or fell short, or "none met"]
- What changed: [the patch, revision, or workaround, what you would
  update, or "nothing"]
```

This section also keeps one short dated entry per week of tool work,
starting below: what you built or changed that week, what broke, and
what you changed because of it. The blocks tell the story where it
happened; these entries are the toolkit's own timeline.

All four entries are graded. Keep every heading below, and fill each
one in the week it belongs to.

**Unit 5: [one line on the tool work]**

[2-4 sentences: what you built (the scout, your strategy), what broke
or fell short, what changed because of it.]

```text
**Toolkit**

- Tool: issue-scout
- What it produced: top 5 ranked issues based on my fit profile and search strategy
- Difficulties: the search strategy was initially designed to prefer activity in the issue thread, but that made claude pick 5 issues that were already claimed
- What changed: updated the strategy to prefer less activity (if not none) so the ranked issues would be unclaimed
```

**Unit 6: [one line on the tool work]**

[2-4 sentences: the voice-guard, the repo-memory file. What broke or
fell short, and what changed because of it. "Nothing broke" counts when
it is true - say how you know.]

```text
**Toolkit**

- Tool: issue-scout
- What it produced: top 5 ranked issues based on my fit profile and search strategy
- Difficulties: the issues were not up to standards according to the rubric
- What changed: refined and fine-tuned rubrics and search strategy queries

- Tool: voice-guard
- What it produced: centralized all voice-guides in the skills directory under voice-guard to use as PreToolUse hook
- Difficulties: N/A
- What changed: N/A
```

**Unit 7: [one line on the tool work]**

[2-4 sentences: the ship-gate and your gate manifest. What it produced
on your real branch, what fought you, what changed because of it.]

```text
**Toolkit**

- Tool: ship-gate
- What it produced: pr-precheck hook
- Difficulties: I ran into some technical difficulties while running the install.py file because of having an older python version and not having my shell's path set up to the newer version.
- What changed: I updated python and fixed the shell's path, and was able to run the install.py file afterward.
```

**Unit 8: [one line on the tool work]**

[2-4 sentences: the PR-monitor and your playbook. What it read, what it
drafted, what you did with the draft.]

---

## Why I Chose This Issue

[1-2 paragraphs in your own words: how you searched, what your scan
surfaced, what your scout's verdict said, why this issue fits your
profile, and what you hope to learn. If your scout's verdict on it
was reject and you chose it anyway, say so here and say why; choosing
against your own tool silently is what loses points. Close with an
honest read of the tool itself: where the scout fell short on a real
wild search and what you changed or would change, or what convinced
you it held up. **Record the link to your claim comment in this section too.**
Not claimed yet? Write `claim pending` and today's date where the link goes,
and add the link the moment your claim lands.]

> I searched repeatedly for the right issues that match my fit profile. I had to
  fine-tune most of my rubric and search strategy in order to get satisfactory
  search results. My searches kept returning issues I was not interested in
  or issues that the grader kept rejecting. Finaly I was able to find an issue
  I was interested in after spending a lot of time refining my searches. And the
  grader's verdict for this issue was "accept" and the difficulty was "straightforward".
  The issue I selected is "Cover malformed JSON independently of text validation".
  I selected this because it is written in python which I'm fairly proficient in. This
  project also uses FastAPI which I'm interested to learn. Finally, this issue
  focuses on JSON which I'm familiar with and hopefully can find a fix for it.
  It is also labeled "good first issue", so the scope is not too broad and beginner friendly.
  Since this is part of the weekly prep task, I won't be claiming the issue by posting
  a claim comment. Instead, I will emulate the open source contribution workflow from week 6-8.

**Toolkit**

- Tool: issue-scout
- What it produced:
  - scamshield-api #113 (https://github.com/ashrafee-dev/scamshield-api/issues/113): add tests/roadmap/text/test_json_errors.py covering malformed JSON.
  - Ranking signals: carries help wanted, 0 comments, opened by the Owner.
  - The issue names the file, the acceptance criteria and the run commands.
  - The repo has AGENTS.md, 52 stars, commits within 10 days, and a maintainer who replied to another issue on the same day.
  - Difficulty: straightforward.
  - I found no linked, open or merged PR for it.
- Difficulties: none met
- What changed: nothing

---

## Understanding the Issue

**Problem Description**

[In your own words, what is broken or missing?]

The issue asks for adding tests to cover malformed JSON independently of text validation. This is not a bug-fix so nothing is broken.

**Expected Behavior**

[What should happen?]

The tests should do the following:
- Send truncated JSON and invalid encodings through TestClient
- Assert controlled client errors and no provider calls
- Document current FastAPI behavior without inventing a new envelope

**Current Behavior**

[What actually happens?]

No tests exist to test that behavior currently.

**Affected Components**

[Which parts of the codebase are involved?]

`tests/roadmap/text/test_json_errors.py`

**Toolkit**

- Tool:
- What it produced:
- Difficulties:
- What changed:

---

## Reproduction Process

**Environment Setup**

[What a stranger would need to stand this up: your operating system,
the relevant versions (language, runtime, package manager, the project
itself), and how you set the project up. Then the challenges you faced
and how you solved them, or that none came up.]

OS: MacOS 27.0.1
Release: v0.1.0
Source audit: 9d8ac3e01df1
Current main: bd8eb30

Since this issue focuses on adding tests, there is no reproduction necessary.

**Steps to Reproduce**

1. [Step 1]
2. [Step 2]
3. [Observed result]

**Reproduction Evidence**

- **Commit showing reproduction:** [link to commit in your fork]
- **Screenshots/logs:** [if applicable]
- **My findings:** [what you discovered during reproduction; an
  honest, evidenced cannot-reproduce that led you to re-pick or ask
  the maintainer belongs here and costs you nothing]

**Toolkit**

- Tool:
- What it produced:
- Difficulties:
- What changed:

---

## Solution Approach

**Analysis**

[Your analysis of the root cause: what is causing the issue, traced
to the files and functions involved.]

**Proposed Solution**

[High-level description of your fix approach, and what you are
deliberately NOT changing.]

**Implementation Plan**

1. [Modify file X to do Y]
2. [Add or change Z]
3. [Update tests]

[Record deviations here as they happen: what changed mid-build and
why. A recorded deviation is honest work; silent drift is not.]

**Toolkit**

- Tool:
- What it produced:
- Difficulties:
- What changed:

---

## Testing Strategy

[What observable checks prove the fix: your reproduction steps re-run
against the built change (before and after), and the repo's own test
suite or checks with the outcome shown. "Tests pass" with nothing
observable named is not a strategy.]

**Toolkit**

- Tool:
- What it produced:
- Difficulties:
- What changed:

---

## Implementation Notes

[A running log, added to as you work. Date each entry. What you
built, decisions you made when you made them, wrong turns included.]

**[Date]**

[Entry]

**[Date]**

[Entry]

**Toolkit**

- Tool:
- What it produced:
- Difficulties:
- What changed:

---

## Pull Request

**PR Link:** [GitHub PR URL when opened]

**PR Description:** [what the PR says; much of the content above
adapts into it]

**Maintainer Feedback:**

- [Date]: [feedback received, or "none yet"; silence is a normal
  state and costs you nothing]
- [Date]: [how you addressed it]

**Status:** [Awaiting review / Iterating / Merged / Closed. The
status is a fact you record, never a grade: the PR is graded as
opened.]

**Toolkit**

- Tool:
- What it produced:
- Difficulties:
- What changed:

---

## Learnings and Reflections

**Technical Skills Gained**

[What you learned technically, named concretely.]

**Challenges Overcome**

[What was hard and how you solved it; point at the real events, the
Toolkit blocks above are full of them.]

**What I'd Do Differently Next Time**

[Reflection on your process.]

---

## Resources Used

[What actually helped, not a reading list. List things this story
already shows you using: the doc you followed to set the environment
up, the thread that explained the bug, the person who answered you.
One real entry beats ten plausible ones.]

- [Link to documentation that helped]
- [Discussion, issue, or post that helped]
