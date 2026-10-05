# Evidence guide: where evidence lives in a PR package

<!--
THIS IS THE PART YOU WRITE (third week running: the map stays in your
hands). Your tool uses this guide as its map: for every kind of
evidence a rubric check names, this file says WHERE to find it in a PR
package and WHAT GOOD LOOKS LIKE when you do.

The four families below are the harness's failure categories under
the names the eval README uses: plan fidelity = silent-drift, test
evidence = not-tested, diff quality = unreviewable, standards and
comms = standards-wall. A package that fails none of them is a
clear-accept. Under each family heading below, write:

- Where it lives: the exact places to look. In an eval bundle (which
  section of the package: the plan-context block's scope pair and test
  plan, the candidate PR's diff, commits, description, or
  test-evidence section, the repo-facts block's template asks and
  stated policy). In live mode (where in your working copy and on
  GitHub: your plan.md and its deviation notes, your branch's diff,
  your draft title and description, your captured test output, the
  repo's PR template and CONTRIBUTING.md).
- What good looks like: one or two sentences someone else could apply.
  Prefer observable conditions ("every changed file falls inside the
  plan's stated boundary or a deviation note") over adjectives ("the
  diff is clean").

A rubric check whose evidence this guide cannot locate is a check
nobody else can execute, and this week that cuts three ways: your
procedure says WHEN to gather each family, this guide says WHERE, and
your SKILL.md says the tool reads both. Write the map you wish your
executor had.
-->


## Plan fidelity (harness category: silent-drift)

<!-- Where the plan states its scope, boundary, and deviation notes,
and where the diff shows what actually changed. What it means for a
diff to match the plan, for an honest deviation to re-tie a mismatch,
and what silent drift looks like in each direction (more than the
plan, or less with no note). The description's fidelity claims read
against the diff live here too: a description claiming more or less
than the diff delivers is silent drift, not a comms problem. -->

| Signal | On github.com | In the eval bundle | What good looks like |
|---|---|---|---|
| The plan's scope and boundary (files, steps, "not in scope") | Your plan.md; the plan comment posted on the issue | "Plan context" block: the Plan paragraph (steps, "Not in scope", "Files") | Every step, file, and exclusion is listed, so each diff hunk can be checked against it. |
| Deviation notes | The deviation-notes section of plan.md; any later comment on the issue explaining a change | Any deviation or deferral sentence in "Plan context" (e.g. "deferred in the plan's note") | A deviation is written down before or alongside the change, and the description restates it. |
| What actually changed (files and hunks) | `git diff main...HEAD` on your branch; the PR's "Files changed" tab | "Candidate PR" > "### Diff" (every `---`/`+++` file header and hunk) | Every changed file and hunk falls inside the plan's boundary or a deviation note. A missing hunk for a planned step needs a note too. |
| Extra scope: new flags, config options, renames, rewrites | Added options, settings, or renamed symbols anywhere in the diff | New `+` lines in the diff that add config keys, CLI flags, or function renames the plan never names (and the plan's "Not in scope" list) | None. A hunk the plan scopes out, or never mentions, is silent drift even when it is adjacent and harmless. |
| Missing scope: planned steps absent from the diff | The plan's step list read against the diff (docs, warnings, tests) | Each planned step ("and a docs update") has a matching hunk | Every planned step has a hunk, or an explicit deferral. A step the plan promises that the diff lacks is drift. |
| Fidelity claims in the description | Your draft PR description ("implements the plan exactly", "no changes beyond", "docs now document X") | "Candidate PR" > "### Description" | Each claim is true of the diff. Claiming more or less than the diff delivers is drift, even with a clean checklist and strong evidence. |
| Honest shortfall | A deferral in plan.md, repeated in the PR description | A deferral in "Plan context", restated in the description | The shortfall is named in both the plan and the description, so the diff is ready as scoped. |


## Test evidence (harness category: not-tested)

<!-- Where the PR shows its proof: the test-evidence section's
before/after against the plan's test plan and the reproduction's own
steps, and the outcome of the repo's own checks or suite. What
decisive looks like (an observable behavior named, the expected-after
stated, the checks' outcome visible) next to "tests pass". -->

| Signal | On github.com | In the eval bundle | What good looks like |
|---|---|---|---|
| The plan's test plan | The "Test plan" lines in plan.md | "Plan context": the "Test plan:" sentence | The checks the PR must show, named one by one (every failure mode and path the plan lists). |
| The reproduction's own steps | The issue body and your repro report | "Issue" body, plus "Repro evidence" in "Plan context" | The exact command or input that showed the bug is the one re-run. |
| Before/after of that repro | Pasted terminal output in the PR description, or a linked CI log | "Candidate PR" > "### Test evidence": output labeled before and after | An observable behavior is named (error text, exit code, rendered output), the before shows the bug, and the after shows the expected result. |
| The path exercised | The command in your pasted output, read against the issue's trigger | The command or test in "### Test evidence" read against the issue's trigger | The evidence exercises the changed, failing path. A control or the unchanged path (a single-file case, a GET with casing) does not count. |
| Full coverage of the plan's test plan | Each test-plan item matched to a pasted output | Each "Test plan:" item matched to something in "### Test evidence" | Every item the plan names is re-run. Covering one of two named failure modes leaves the other unproven. |
| Added tests | Test files in the diff; the PR's checks tab | Test hunks in "### Diff" | A new test fails without the fix and exercises the fixed behavior itself, not an adjacent one. |
| Repo's own checks or suite | The PR's CI checks; the commands CONTRIBUTING.md names, run locally | A command and its outcome shown in "### Test evidence"; the "Repo facts" test/check asks | The check is named with its outcome visible. "Tests pass", "works on my machine", or "tested locally" with nothing shown is not evidence. |

## Diff quality (harness category: unreviewable)

<!-- Where the change itself lives: the unified diff and the commit
list. What a reviewable change looks like (the fix visible, nothing
unrelated riding along) and the debris tells: debug leftovers, dead
code, commented-out blocks, formatting churn, drive-by edits. -->

| Signal | On github.com | In the eval bundle | What good looks like |
|---|---|---|---|
| The fix itself | `git diff main...HEAD`; the "Files changed" tab | "### Diff" | The fix is visible in the first read, and the diff is about the size the plan implies. |
| Debug leftovers | `+` lines with print, `eprintln`, `console.log`, or `DEBUG` markers | Same patterns in `+` lines of "### Diff" | None. Debug output is removed before submit. |
| Commented-out code | `+` lines that are code behind a comment marker | Same in "### Diff" | None. No commented-out attempts or probes. |
| Dead code | New functions, imports, or `allow(dead_code)` with no caller in the diff | Same in "### Diff" | Everything added is used, and a TODO appears only if the plan names it. |
| Formatting and import churn | Whitespace-only hunks, re-indents, reordered imports, repeated identical lines | Hunks whose only change is whitespace, ordering, or re-printed lines | No hunk exists only to reformat or reorder. Mechanical churn around a correct fix still buries it. |
| Drive-by edits | Hunks in files or functions unrelated to the issue | Hunks in unrelated files, such as reworded help text or renames | Every hunk serves the plan. An unplanned behavior change is a plan-fidelity problem. Unrelated tidying is a debris problem. |
| Commit list | `git log main..HEAD`; the PR's "Commits" tab | "### Commits" | Messages say what changed. "wip", "fix", "fmt + cleanup", and "misc cleanups while debugging" are tells. |

## Standards and comms (harness category: standards-wall)

<!-- Where the repo states its asks (the repo-facts block's PR
template sections, contributing instructions, and stated policy,
including AI-use disclosure) and where the PR honors them: the
stated sections filled with real content, the disclosure present,
explicit maintainer direction in the thread engaged. What compliant
looks like next to boilerplate or a visibly ignored ask. (Whether
the description's claims match the diff is plan fidelity, above.) -->

| Signal | On github.com | In the eval bundle | What good looks like |
|---|---|---|---|
| The repo's PR template asks | `.github/PULL_REQUEST_TEMPLATE.md` in the repo | "Repo facts": the "pull requests:" line | Every required section or checklist item is answered with real content for this change: "closes #N" with the real number, type of change, and tests/checks stated. |
| Files the checklist requires | The template and CONTRIBUTING.md (changelog or whatsnew entry, i18n, docs, type annotations) | The same asks in "Repo facts", read against the files in "### Diff" | Each required file or entry appears in the diff. A claim to have done it does not count. |
| Contribution policy | CONTRIBUTING.md and any `AI_POLICY` or similar file | "Repo facts": the "contribution policy" line | The PR follows the stated rules (small PRs, issue referenced, branch naming). |
| AI-use disclosure | CONTRIBUTING.md or the PR template, plus the disclosure line in your description | "Repo facts" policy line, read against "### Description" | If the policy requires disclosure, the description states the AI use in the author's own words. Treat every package as AI-assisted. If no policy exists, nothing is required. |
| Issue linkage | Closing keyword in the description ("Closes #N") | "### Description" referencing the issue number | The issue is referenced and the number is correct. |
| Maintainer direction in the thread | The issue and PR thread | "Thread highlights" | An explicit maintainer ask (a design question, a preferred option) is engaged in the description or diff, not ignored. |
| Boilerplate | Template sections left as placeholders, or unchecked boxes with no comment | Template headings with empty or copied text | Filled sections say something specific to this change. A terse description that is complete passes. |
