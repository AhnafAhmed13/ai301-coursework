# Rubric: is this reproduction package ready to post?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever
checks you define here. It ships empty on purpose: the judgment is your
work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four
   columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where in the package. Name
     the part (the claim comment, the repro report's environment
     record, the artifacts read against the issue's description, the
     repo-facts block) or a location from your
     references/evidence-guide.md. "The report" is not a source; "the
     output excerpt read against the error the issue describes" is.
   - Pass condition: a decision rule about the OUTCOME that someone
     else could apply and get your answer. Judge the thing itself (does
     the artifact show the issue's behavior?), never the write-up's
     shape (how many steps it has, how long it is, whether it uses a
     template's headings). Structure-shaped checks are what make
     graders disagree with themselves.
   - Weight: `required` (a fail here holds the package) or `preferred`
     (never changes the verdict).

2. A verdict rule below the table: how the check grades combine into
   accept (ready) or reject (hold), including how `unclear` is
   treated. The verdict space is binary. If you write no rule for
   `unclear`, the skill treats it as fail.

Cover what actually gets bad packages posted. The lecture named the
proof families: the environment is recorded, the steps are complete
and followable, the behavior shown matches the issue (not an adjacent
one), the outcome is stated honestly (an evidenced cannot-reproduce is
a pass, a confident wrong-target is not), and the words respect the
repo's conventions. A rubric that ignores a family will fail eval
packages designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Environment record | references/evidence-guide.md > Environment | candidate claim comment OR candidate repro report includes environment record AND matches the issue body environment (OR addresses discrepancy with valid explanation) | required |
| Reproduction steps | references/evidence-guide.md > Steps | candidate claim comment OR candidate repro report includes steps taken to reproduce the issue (AND candidate steps match the issue steps exactly, if available; OR states cannot reproduce) | preferred |
| Expected vs actual behavior | references/evidence-guide.md > Behavior shown | candidate claim comment OR candidate repro report includes expected vs actual behavior (AND candidate behaviors match the issue behaviors exactly, if available) | preferred |
| Reproduces the proper bug | references/evidence-guide.md > Honesty | candidate claim comment AND candidate repro report reproduces the bug addressed in the issue AND doesn't go out of scope | required |
| Communication | references/evidence-guide.md > Comms | Candidate claim comment AND candidate repro report follows the repo's conventions and uses formal and friendly language with respectful tone AND if the repo has AI disclosure policy, candidate discloses it | required |


## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict;
unclear counts as fail." -->

Accept if every required check passes.
Preferred checks never change the verdict.
Unclear counts as fail.