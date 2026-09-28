# Procedure: how this skill grades a plan package

<!--
THIS IS THE PART YOU WRITE, and it is a new kind of part. Weeks 1 and
2, SKILL.md carried a numbered workflow and you only wrote judgment
files. This week the workflow is gone from the frame: SKILL.md says
"execute procedure.md", and these are the operating steps you author.
The machinery is in your hands now.

Your operator swap is the design brief. When your executor stalled
because your rubric said WHAT to decide but not HOW to find the
evidence, that was a procedure gap. This file is where those gaps get
closed: a complete procedure lets someone who has never seen a plan
package before (a groupmate, or the skill itself) grade one exactly the
way you would.

Under each stage heading below, write the concrete steps for that
stage. The one-line note under each heading says what a complete
procedure must decide there. Write steps, not intentions: "read the
repro evidence before the plan, and note what behavior it pins down"
is a step; "understand the context" is a wish.
-->

## Read order

<!-- What gets read, in what order, before any check is graded, and
what to note down from each part while reading. A complete procedure
decides the order (issue first? repro evidence first?) and says why
the order matters for the checks that come later. -->

In live mode, read `scope.md` and confirm the issue is inside the scoped source; note any house rules. Then (both modes) read `rubric.md` and `references/evidence-guide.md`. List the rubric's checks and its verdict rule.

Read the whole package before grading anything, in this order: the issue context (including thread highlights) first, then the repo-facts block (eval mode) or the repo's docs/CONTRIBUTING.md (live mode) — the Comms checks (AI disclosure, follows stated conventions) depend on this and are ungradable without it — then the repro evidence, then the candidate plan, then the candidate plan comment.

Live mode, house issue: a student on the house issue has no posted repro comment of their own. There, the repro evidence is the house repro pack as quoted in the drafts; if the drafts quote no repro evidence at all, note that absence explicitly — it is itself what the diagnosis and test-plan checks grade.

Take notes as you read each part. Grading works from these notes (see Check execution) rather than a fresh re-read per check.

## Evidence gathering

<!-- For each evidence family your rubric's checks name, the concrete
gathering move: which part of the package (or, live, which page or
thread location per your evidence guide) to pull the fact from, and
what to record. A complete procedure leaves no check whose evidence an
executor would have to hunt for. -->

For each check, gather exactly the evidence the rubric names, using the evidence guide's map. Several checks compare two sources rather than reading one; record both sides:

- diagnosis matches repro evidence: the plan's cause/diagnosis section, against the repro evidence's actual described behavior.
- no scope creep: the plan's changes/scope section (in-scope line, not-in-scope line, file names).
- plan targets the cause: the plan's cause/diagnosis section and its approach/implementation section, read together.
- executable: the plan's approach/implementation section (files or areas, order of work).
- test plan: the plan's test-plan section, against the repro evidence's steps it claims to reuse.
- honesty about unknowns: the plan's cause/diagnosis section (confidence vs. evidence), its risks/unknowns section, its test-plan section (overclaiming a result), and any deviation note in `plan.md`.
- follows repo's stated conventions: the repo-facts contribution policy (or CONTRIBUTING.md, live), the thread highlights (or live thread), and the candidate plan comment.

Live mode: gather issue-side and repo-side evidence from the locations the guide names; the drafts are the candidate side. Eval mode: quote the relevant lines from the bundle for each side named above.

## Check execution

<!-- How one check runs against gathered evidence: in what order the
checks execute, what an executor does when evidence for a check is
genuinely absent, and when a check may be graded without re-reading
the whole package. A complete procedure makes two executors grade the
same package the same way. -->

Grade checks in the order they appear in the rubric's table. Grade each check `pass`, `fail`, or `unclear`, with a one-line evidence quote or fact for each grade, drawn from the notes taken during Read order and Evidence gathering — do not re-read the whole package per check. `unclear` means the evidence needed is genuinely absent, not that you did not look; when a comparison check is missing one of its two named sources entirely (for example, no repro evidence was quoted at all), that absence is the evidence for the grade.

## Verdict assembly

<!-- How the per-check grades become the final accept or reject:
apply your rubric's verdict rule, state how unclear grades enter it,
and say what gets quoted in the output for the deciding check. A
complete procedure produces the same verdict from the same grades,
every time. -->

Apply the rubric's verdict rule to produce the final verdict: `accept` (ready to post) or `reject` (hold). There is no third verdict. For the deciding check or checks (the required check(s) that failed or were unclear; if every required check passed, say so), quote the same one-line evidence recorded during Check execution.

In live mode, hold the drafts against `voice-guide.md` and note any broken rule in the summary.

Output the result as the fenced JSON block specified in `SKILL.md` (`item`, `checks` with `name`/`grade`/`evidence`, and `verdict`), last in the output.