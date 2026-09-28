# Rubric: is this plan ready to post and build from?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever
checks you define here (via your procedure.md). It ships empty on
purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four
   columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where in the package. Name
     the part (the plan's scope statement, the test plan read against
     the repro evidence's steps, the plan comment read against the
     thread highlights, the repo-facts block) or a location from your
     references/evidence-guide.md. "The plan" is not a source; "the
     plan's stated cause read against what the repro evidence shows"
     is.
   - Pass condition: a decision rule about the OUTCOME that someone
     else could apply and get your answer. Judge the thing itself (is
     this one bounded change? could a stranger start executing it?),
     never the write-up's shape (how many sections it has, how long it
     is, whether it uses headings). Structure-shaped checks are what
     make graders disagree with themselves.
   - Weight: `required` (a fail here holds the package) or `preferred`
     (never changes the verdict).

2. A verdict rule below the table: how the check grades combine into
   accept (ready) or reject (hold), including how `unclear` is
   treated. The verdict space is binary. If you write no rule for
   `unclear`, the skill treats it as fail.

Cover what actually gets bad plans posted. The lecture named the
failure families: the diagnosis ignores or contradicts the reproduced
evidence, the change is unbounded (scope creep), the plan targets the
symptom while the evidence points at the cause, a stranger could not
start executing it, the test plan proves nothing observable, the
unknowns are dressed up as certainty, and the comment ignores what the
thread or the repo's stated conventions ask. A rubric that ignores a
family will fail eval packages designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| diagnosis matches repro evidence | references/evidence-guide.md > diagnosis & grounding | diagnosis must match the repro evidence | required |
| no scope creep | references/evidence-guide.md > scope | the changes must be bounded, with in/out-of-scope stated and the file names where changes would be made | required |
| plan targets the cause | references/evidence-guide.md > diagnosis & grounding and executability | the plan/approach must target the cause and not the symptoms | required |
| executable | references/evidence-guide.md > executability | lists concrete steps anyone can follow | required |
| test plan | references/evidence-guide.md > test plan | repro steps are re-run and show an observable result | required |
| honesty about unknowns | references/evidence-guide.md > honesty | stated confidence in the diagnosis/approach doesn't exceed what the repro evidence supports, material risks/unknowns are named rather than omitted, and if a test result doesn't fix the bug/issue, that is clearly stated without wrongly claiming the issue is fixed | required |
| follows repo's stated conventions | references/evidence-guide.md > comms | the plan comment follows the repo's stated conventions and doesn't ignore direction already given on the thread | required |

## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict;
unclear counts as fail." -->
Accept if every required check passes.
Preferred checks never change the verdict.
Unclear counts as fail.
Each failed check must cite the exact missing or conflicting evidence.