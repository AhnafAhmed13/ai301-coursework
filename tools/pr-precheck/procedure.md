# Procedure: how this tool grades a PR package

<!--
THIS IS THE PART YOU WRITE (second week running for the procedure).
Week 3 you wrote these steps for a plan package; this week the graded
object is a PR package, and the read that matters most is a
side-by-side: the diff against the plan, the evidence against the test
plan, the description against both. Your week-3 procedure is the
pattern; do not paste it unchanged, because its read order was built
for a different object.

Your rotation is the design brief again, and this week friction routes
three ways: a stall on WHAT to decide is a rubric gap, a stall on
WHERE to look is a procedure gap (this file), and a stall on what the
tool even reads or outputs is a frame gap (your SKILL.md). A complete
procedure lets someone who has never seen a PR package before grade
one exactly the way you would.

Under each stage heading below, write the concrete steps for that
stage. The one-line note under each heading says what a complete
procedure must decide there. Write steps, not intentions: "read the
plan's scope pair before opening the diff, and list the files the plan
names" is a step; "understand the change" is a wish.
-->

## Read order

<!-- What gets read, in what order, before any check is graded, and
what to note down from each part while reading. A complete procedure
decides where the plan sits in the order (before the diff? before the
description?) and says why the order matters for the side-by-side
checks that come later. -->

Read each part of the package once, in this order, and write the
notes below as you go. Every later step works from these notes; do not
re-read the package to grade a check.

1. **Plan** (eval: the "Plan context" block; live: plan.md with its
   deviation notes, or the house plan). Note: the plan's steps, the
   files it names, its "Not in scope" list, every deviation or
   deferral, the test plan items, and the repro steps. Read the plan
   first: the diff and the description can only be judged against it.
2. **Issue and thread** (eval: "Issue" and "Thread highlights";
   live: the issue and thread on GitHub). Note: the issue's trigger
   (the exact repro) and any explicit maintainer direction.
3. **Repo facts** (eval: the "Repo facts" block; live: the repo's PR
   template, CONTRIBUTING.md, and any AI policy). Note: each template
   section or checklist item, each file the repo requires (changelog,
   tests, docs), and whether AI-use disclosure is required.
4. **Diff and commits** (eval: "### Diff" and "### Commits"; live:
   `git diff main...HEAD` and `git log main..HEAD`). Make one hunk
   list: for each hunk, the file, what it does, and whether it is a fix
   hunk, a test hunk, or something else. Flag debris while listing:
   debug prints, commented-out code, dead code, whitespace, import or
   reorder churn, and unrelated edits. Note each commit message.
5. **Test evidence** (eval: "### Test evidence"; live: your pasted or
   captured test output). Note each command or test shown, its
   before and after output, and each repo check with its outcome.
6. **Title and description** (eval: "### Title" and "### Description";
   live: your draft). Note each claim about what the change includes,
   the issue reference, each template section answered, and any AI
   disclosure. Read these last so the claims are judged against what
   you already know about the diff.

## Evidence gathering

<!-- For each evidence family your rubric's checks name, the concrete
gathering move: which part of the package (or, live, which file, diff,
or page per your evidence guide) to pull the fact from, and what to
record. The load-bearing gathers this week are pairings: diff files
against plan scope, claimed evidence against the plan's test plan and
the repo's checks, description claims against diff contents. A
complete procedure leaves no check whose evidence an executor would
have to hunt for. -->

Gather by pairing notes, once, using
[references/evidence-guide.md](references/evidence-guide.md) for where
each fact lives. Record each pairing in one line.

- **Plan fidelity:** pair each hunk with a plan step, a file the plan
  names, or a deviation note. Hunks with no pair are extra scope. Pair
  each plan step with a hunk or a deferral. Steps with no pair are
  missing scope. Pair each description claim with the hunks that
  support it.
- **Test evidence:** pair each test plan item with a shown
  before/after. Check that each shown command exercises the issue's
  trigger on the changed path. Pair each repo check the plan or repo
  facts name with a shown outcome. Note whether a test hunk exists and
  what it exercises.
- **Diff quality:** take the debris flags and unrelated hunks from the
  hunk list and the commit messages from your notes. Do not rescan
  the diff.
- **Standards and comms:** pair each template ask with the description
  content that answers it. Pair each required file with a hunk. Pair
  the AI policy with the description's disclosure. Pair the issue
  reference and the maintainer direction with the description.

## Check execution

<!-- How one check runs against gathered evidence: in what order the
checks execute, what an executor does when evidence for a check is
genuinely absent, and when a check may be graded without re-reading
the whole package. A complete procedure makes two executors grade the
same package the same way. -->

1. Run the checks from [rubric.md](rubric.md) in table order, using
   only the paired notes. Grade each `pass`, `fail`, or `unclear`, and
   write one line of evidence: the fact or quote that decided it.
2. Grade each fact under the check that names it. A hunk outside
   the plan fails "No extra scope". A hunk unrelated to the issue
   fails "Nothing unrelated rides along" as well. Do not add a failure
   the rubric does not name.
3. Judge the thing, not the polish: a terse description can pass, and
   a thorough checklist cannot rescue a diff that drifts. Grade a
   claim against the diff, not against how confidently it is written.
4. If the evidence for a check is absent from the package, grade it
   `unclear` and say what is missing. Do not guess, fetch, or
   improvise. Where a rubric check says it passes when nothing is
   required (no template, no policy, no named check), grade `pass`
   and cite that absence.
5. If the procedure is silent on a step you need, report the gap in
   the summary and continue without inventing a rule.
6. **Eval mode:** the bundle is the whole world. Fetch nothing, run
   nothing, and ignore scope.md and voice-guide.md. Grade every check.
7. **Live mode:** run the voice and scope steps from SKILL.md around
   this procedure, not inside the checks. Report any voice-guide rule
   the title or description breaks in the summary only. Grade the
   checks from your own notes, and run the repo's checks yourself only
   if the test evidence is missing and the user asks.

## Verdict assembly

<!-- How the per-check grades become the final accept or reject:
apply your rubric's verdict rule, state how unclear grades enter it,
and say what gets quoted in the output for the deciding check: the
check whose failure the verdict turned on. When more than one check
failed, your procedure picks which one gets quoted (first failing
required check in rubric order is a fine rule); nothing picks it for
you, so write the rule down. A complete procedure produces the same
verdict from the same grades, every time. -->

1. Apply the verdict rule in [rubric.md](rubric.md): accept if every
   required check is `pass`, reject if any required check is `fail`
   or `unclear`. Preferred grades are listed in the output but never
   change the verdict.
2. If more than one required check failed, quote the first failing
   required check in rubric order as the deciding check. Name the
   other failures after it, one line each.
3. The summary before the JSON gives the verdict, the deciding check
   with its evidence quote, then the rest. Live mode adds, for a
   reject, the smallest change that would flip the verdict.
4. End with the JSON block from SKILL.md, valid and last, with one
   entry per rubric check (preferred ones included) and the verdict
   from step 1.
