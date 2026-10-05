# Rubric: is this pull request ready to submit?

<!--
THIS IS THE PART YOU WRITE (fourth week running; this is the rubric's
final form in the sandbox). Your frame in SKILL.md executes whatever
checks you define here, via your procedure.md. It ships empty on
purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four
   columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where in the package. Name
     the part (the diff read against the plan's scope, the test
     evidence read against the plan's test plan, the description read
     against the diff, the repo-facts block's template asks) or a
     location from your references/evidence-guide.md. "The PR" is not
     a source; "the diff's changed files read against the plan's
     stated boundary" is.
   - Pass condition: a decision rule about the OUTCOME that someone
     else could apply and get your answer. Judge the thing itself
     (does the diff fall inside the plan plus its deviation notes? is
     the claimed evidence observable?), never the write-up's shape
     (how long the description is, how many commits there are).
     Structure-shaped checks are what make graders disagree with
     themselves.
   - Weight: `required` (a fail here holds the package) or `preferred`
     (never changes the verdict).

2. A verdict rule below the table: how the check grades combine into
   accept (submit) or reject (hold), including how `unclear` is
   treated. The verdict space is binary. State the `unclear`
   treatment explicitly: the frame here is YOUR SKILL.md, so a rubric
   that stays silent is only covered if your frame's grading
   discipline says what happens (the contract's own default is that
   an unverifiable claim fails).

Cover what actually gets bad PRs submitted. The failure families the
lecture named ARE the harness's scoring categories, same names as the
eval README: silent drift (the diff silently does more or less than
the posted plan, or the description claims fidelity the diff
contradicts), not tested (the evidence proves nothing observable, or
the repo's own checks were never run), unreviewable (debris or
unrelated hunks bury the change), and standards wall (the repo's
stated template and disclosure asks are ignored). Your evidence
guide's four headings map onto these one to one (plan fidelity =
silent drift, test evidence = not tested, diff quality =
unreviewable, standards and comms = standards wall), and the category
floor is scored on exactly these names plus clear accept. A rubric
that ignores a category will fail the eval packages built around
that category. And remember the honest-outcome
rule, fourth week running: a PR that honestly discloses a shortfall
can be ready; a rubric that equates "less than everything" with
"hold" fails the set.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| No extra scope (silent drift) | The diff's changed files and hunks read against the plan's stated boundary, its "Not in scope" list, and its deviation notes. See [Plan fidelity](references/evidence-guide.md#plan-fidelity-harness-category-silent-drift). | Every changed file and hunk falls inside the plan's boundary or a deviation note. Fail if a hunk adds something the plan never names or scopes out (a new flag, config option, rewrite, or reworded unrelated text) with no note. | required |
| No missing scope (silent drift) | The plan's step list read against the diff, and against any deferral note. See [Plan fidelity](references/evidence-guide.md#plan-fidelity-harness-category-silent-drift). | Every planned step has a matching hunk or an explicit deferral in the plan or a deviation note. A disclosed shortfall passes. Fail if a promised step (docs, warning, second fix) is absent with no note. | required |
| Description matches diff (silent drift) | The description's fidelity claims ("exactly as planned", "docs now document X", "no changes beyond") read against the diff. See [Plan fidelity](references/evidence-guide.md#plan-fidelity-harness-category-silent-drift). | Every claim the description makes about what the change does or does not include is true of the diff. Fail if it claims more or less than the diff delivers. | required |
| Deviations restated (silent drift) | A deviation or deferral note in the plan context read against the description. See [Plan fidelity](references/evidence-guide.md#plan-fidelity-harness-category-silent-drift). | Where the diff deviates from or defers part of the plan, the description says so as well. Pass if the diff has no deviation. This check never changes the verdict. | preferred |
| Observable before/after (not tested) | The test-evidence section read against the issue's and the plan's repro steps. See [Test evidence](references/evidence-guide.md#test-evidence-harness-category-not-tested). | The evidence shows the repro's behavior before and after the change (an error, output, or exit code named, expected-after stated). Fail if the evidence is "tests pass", "works on my machine", or "tested locally" with nothing shown. | required |
| Evidence exercises the fix (not tested) | The command or test in the test-evidence section read against the issue's trigger and each item in the plan's test plan. See [Test evidence](references/evidence-guide.md#test-evidence-harness-category-not-tested). | The evidence runs the changed, failing path and covers every item the plan's test plan names. Fail if it exercises only a control or the unchanged path, or leaves a named failure mode unrun. | required |
| Repo checks run (not tested) | The outcome of the repo's own checks or suite in the test-evidence section, read against the checks the plan's test plan and the repo-facts block name. See [Test evidence](references/evidence-guide.md#test-evidence-harness-category-not-tested). | Where the plan or repo facts name a check, suite, or lint, its outcome is shown. Where none is named, the plan's own checks stand in and this passes. Fail if a named check is never shown or only asserted ("cargo test passes" with no output). | required |
| Regression test added (not tested) | The test hunks in the diff read against the fix. See [Test evidence](references/evidence-guide.md#test-evidence-harness-category-not-tested). | A new test exists that would fail without the fix and exercises the fixed behavior itself. Pass if the change is one the plan verifies by a manual repro. This check never changes the verdict. | preferred |
| No debug or commented-out code (unreviewable) | The added lines of the unified diff. See [Diff quality](references/evidence-guide.md#diff-quality-harness-category-unreviewable). | No added debug print, `DEBUG` marker, or commented-out code or attempts. Fail if any appear, even around a correct fix. | required |
| No dead code or churn (unreviewable) | The unified diff's imports, new functions, and whitespace-only or reordered hunks. See [Diff quality](references/evidence-guide.md#diff-quality-harness-category-unreviewable). | No added function, import, or `allow(dead_code)` without a caller; no re-indent, import-reorder, or re-printed-line hunk. Fail if any appear. | required |
| Nothing unrelated rides along (unreviewable) | Every hunk in the diff read against the issue and the plan. See [Diff quality](references/evidence-guide.md#diff-quality-harness-category-unreviewable). | Every hunk serves the issue's fix as the plan scopes it. Fail if a hunk makes an unrelated edit (an unrelated file or function, a drive-by rename or rewording). | required |
| Commits are readable (unreviewable) | The commit list. See [Diff quality](references/evidence-guide.md#diff-quality-harness-category-unreviewable). | Each commit message says what changed. "wip", "fix", "fmt + cleanup", and "misc cleanups" are tells. This check never changes the verdict. | preferred |
| Template asks met (standards wall) | The repo-facts block's PR template asks, read against the description. See [Standards and comms](references/evidence-guide.md#standards-and-comms-harness-category-standards-wall). | Every required template section or checklist item is answered with real content for this change. Fail if a required section is ignored, left as a placeholder, or boilerplate. Pass if the repo states no template. | required |
| Required files present (standards wall) | The files the template and contributing instructions require (changelog or whatsnew entry, tests, docs, i18n), read against the diff's changed files. See [Standards and comms](references/evidence-guide.md#standards-and-comms-harness-category-standards-wall). | Each file or entry the repo's stated asks require appears in the diff. Fail if one is absent, even when the description claims it is done. Pass if the repo requires none. | required |
| AI-use disclosure (standards wall) | The repo-facts block's stated policy read against the description. See [Standards and comms](references/evidence-guide.md#standards-and-comms-harness-category-standards-wall). | If the repo's policy requires disclosing AI use, the description discloses it in the author's own words (treat every package as AI-assisted). Fail if a stated disclosure ask is unmet. Pass if no policy requires it. | required |
| Issue linked and thread engaged (standards wall) | The description read against the issue number and the thread highlights. See [Standards and comms](references/evidence-guide.md#standards-and-comms-harness-category-standards-wall). | The description references the issue, and any explicit maintainer direction in the thread is engaged. This check never changes the verdict. | preferred |

## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict;
unclear counts as fail." -->

Accept if every required check passes. A package that fails none of the
four categories (silent drift, not tested, unreviewable, standards wall)
is a clear accept, honest disclosed shortfalls included. Reject if any
one required check fails, with no partial credit. Preferred checks are
graded and reported but never change the verdict. `unclear` on a
required check counts as fail, because a claim the package cannot
verify means the PR is not ready to submit. Reservations belong in the
check's evidence line, not in the verdict.
