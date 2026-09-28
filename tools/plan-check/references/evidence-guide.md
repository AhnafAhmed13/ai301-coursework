# Evidence guide: where evidence lives in a plan package

<!--
THIS IS THE PART YOU WRITE (second week running: the judgment files
stay in your hands). The skill uses this guide as its map: for every
kind of evidence a rubric check names, this file says WHERE to find it
in a plan package and WHAT GOOD LOOKS LIKE when you do.

Under each family heading below, write:

- Where it lives: the exact places to look. In an eval bundle (which
  section of the package: the issue context, the repro-evidence block,
  the candidate plan's scope statement or test plan, the plan comment,
  the repo-facts block). In live mode (where on GitHub or in the
  draft: the issue thread, the student's posted repro comment, the
  repo's docs, the draft plan and comment).
- What good looks like: one or two sentences someone else could apply.
  Prefer observable conditions ("the stated cause cites behavior the
  repro evidence actually shows") over adjectives ("diagnosis is
  solid").

A rubric check whose evidence this guide cannot locate is a check
nobody else can execute, and this week that cuts twice: your
procedure.md tells the skill WHEN to gather each family, and this
guide tells it WHERE. Write the map you wish your executor had.
-->

## Diagnosis and grounding

<!-- Where the plan states its cause, and where the repro evidence
pins down the behavior that cause must explain. What it means for a
diagnosis to follow from the evidence rather than contradict or
ignore it. -->


| Signal | On github.com | In the eval bundle | What good looks like |
|---|---|---|---|
| Cause | Issue threads > candidate plan > cause/diagnosis section (or something similar) | Candidate plan > cause/diagnosis section (or something similar) | the stated cause cites behavior the repro evidence actually shows |
| Repro evidence | Issue threads > candidate repro report (or something similar) | Repro evidence | repro evidence includes environment, steps, expected, and actual behavior |


## Scope

<!-- Where the plan bounds itself: the in-scope statement, the
not-in-scope line, the files or areas named. What one bounded change
looks like next to a drive-by rewrite. -->

| Signal | On github.com | In the eval bundle | What good looks like |
|---|---|---|---|
| Change scope | Issue threads > candidate plan > changes and/or scope section (or something similar) | Candidate plan > changes and/or scope section (or something similar) | Scope is bounded |
| In-scope | Issue threads > candidate plan > changes and/or scope section (or something similar) | Candidate plan > changes and/or scope section (or something similar) | In-scope mentions the names of specific files in scope |
| Not-in-scope | Issue threads > candidate plan > changes and/or scope (or something similar) | Candidate plan > changes and/or scope (or something similar) | Not in scope / out of scope (or something similar) mentions the names of specific files outside scope |


## Executability

<!-- Where the plan says what will actually be done: files or areas,
approach, order of work. What it means for a stranger to be able to
start executing without asking the author anything. -->

| Signal | On github.com | In the eval bundle | What good looks like |
|---|---|---|---|
| Files or areas | Issue threads > candidate plan > changes and/or approach section (or something similar) | Candidate plan > changes | approach names the specific files or areas it will touch, not just "the relevant code" |
| Approach / order of work | Issue threads > candidate plan > approach/implementation section (or something similar) | Candidate plan > approach/implementation section (or something similar) | the plan lists concrete steps in an order a stranger could follow, not just the end state |
| Stranger-executable | Issue threads > candidate plan (whole) | Candidate plan (whole) | a stranger reading only the plan could start the first step without asking the author a clarifying question |


## Test plan

<!-- Where the plan says how success will be observed, and how that
maps onto the repro evidence's steps and artifacts. What a decisive
test plan names that a vague one does not. -->

| Signal | On github.com | In the eval bundle | What good looks like |
|---|---|---|---|
| Repro steps reused | Issue threads > candidate plan > test plan section (or something similar) | Candidate plan > test plan section (or something similar) | test plan reuses the same steps named in the repro evidence, not a different or looser check |
| Observable result | Issue threads > candidate plan > test plan section (or something similar) | Candidate plan > test plan section (or something similar) | test plan names a concrete, checkable outcome (an assertion, an output, absence of the reported error), not "verify it works" |
| Honest result claim | Issue threads > candidate plan > test plan section (or something similar) | Candidate plan > test plan section (or something similar) | if the plan hasn't been run yet or won't fully resolve the issue, the test plan says so plainly instead of asserting the fix is confirmed |


## Honesty

<!-- Where claims meet uncertainty: risks, unknowns, and deviations.
How to tell stated unknowns from false confidence, and where an
honest mid-build deviation gets recorded. -->

| Signal | On github.com | In the eval bundle | What good looks like |
|---|---|---|---|
| Stated risks/unknowns | Issue threads > candidate plan > risks/unknowns section (or something similar) | Candidate plan > risks/unknowns section (or something similar) | the plan names what it isn't sure about (an untested edge case, an assumption about cause) instead of asserting it as settled |
| Confidence vs evidence | Issue threads > candidate plan > cause/diagnosis section (or something similar) | Candidate plan > cause/diagnosis section (or something similar) | the plan's stated confidence matches what the repro evidence actually supports, not stronger language than the evidence earns |
| Recorded deviation | Issue threads > plan.md updated after a build deviation (or something similar) | Candidate plan's deviation note (if present) | when the build departs from the posted plan, the deviation and its reason are written into the plan itself, not left only in the diff |


## Comms

<!-- Where the words meet the thread and the repo: the plan comment
read against the issue's maintainer signals (thread highlights, or
the live thread) and against the repo-facts block's stated templates,
contributing asks, and contribution policy (including AI-use
disclosure requirements). What thread-aware looks like next to
boilerplate. -->

| Signal | On github.com | In the eval bundle | What good looks like |
|---|---|---|---|
| AI disclosure | repo > CONTRIBUTING.md OR repo > docs/CONTRIBUTING.md & issue's comment threads OR linked PRs | Repo facts > contribution policy & Candidate plan comment | if the repo has an AI-use disclosure policy and the candidate used AI, the plan comment discloses it |
| Thread-aware | Issue's comment threads (thread highlights) | Thread highlights & Candidate plan comment | the plan comment responds to what maintainers already said on the thread (a suggested direction, a raised concern) instead of ignoring it |
| Follows stated conventions | repo > .github > PULL_REQUEST_TEMPLATE.md or CONTRIBUTING.md (or something similar) | Repo facts > contribution policy (or something similar) | the plan comment follows the repo's stated format/ask for proposing a plan, where one exists |
