# Evidence guide: where proof lives in a reproduction package

<!--
THIS IS THE PART YOU WRITE (new this week: week 1 handed you this file
finished; the scaffolding fades). The skill uses this guide as its map:
for every kind of proof a rubric check names, this file says WHERE to
find it in a package and WHAT GOOD LOOKS LIKE when you do.

Under each family heading below, write:

- Where it lives: the exact places to look. In an eval bundle (which
  section of the package: the issue context, the repo-facts block, the
  claim comment, the repro report and its parts). In live mode (where
  on GitHub or in the draft: the issue thread, the repo's docs, the
  student's draft comment).
- What good looks like: one or two sentences someone else could apply.
  Prefer observable conditions ("the versions named match what the
  issue targets, or the difference is called out") over adjectives
  ("environment is thorough").

A rubric check whose evidence this guide cannot locate is a check
nobody else can execute; your operator swap showed you what that feels
like. Write the map you wish your executor had.
-->

## Environment

<!-- Where the environment record lives, and what a sufficient one
looks like against the issue's stated target. -->

| Signal | On github.com | In the eval bundle |
|---|---|---|
| Bug report template (repo standards) | repo > .github > ISSUE_TEMPLATE > bug_report.md (or something similar) > operating system, app, build, languages, toolkit, release, etc versions | repo facts > bug reports > operating system, app, build, languages, toolkit, release, etc versions |
| Issue body (bug reporter) | In the issue's body > Environment section (or something similar) | Issue > Environment section (or something similar) |
| Candidate (reproduction environment) | In the issue's comment threads OR linked PRs > reproduction environment description | Candidate claim comment OR Candidate repro report > reproduction environment description |

- The issue environment should follow the repo's issue template.
- The candidate's reproduction environment should match the issue's reported environment.
- If there's a discrepancy, it should be addressed and have a valid explanation.

## Steps

<!-- Where the reproduction steps live, and what makes them followable
by a stranger, starting state to trigger. -->

| Signal | On github.com | In the eval bundle |
|---|---|---|
| Issue body (bug reporter) | In the issue's body > steps to recreate/reproduce section (or something similar) | Issue > steps to recreate/reproduce section (or something similar) |
| Candidate (reproduction steps) | In the issue's comment threads OR linked PRs > reproduction steps | Candidate repro report > reproduction steps |

- The listed steps should be linear and easy to follow
- The list should not skip any major step in the process.
- The candidate should follow the exact steps shown in the issue and verify it leads to the reported bug/error.

## Behavior shown

<!-- Where the artifacts live (output excerpts, logs, screenshots),
and what it means for an artifact to show the issue's behavior rather
than an adjacent one. -->

| Signal | On github.com | In the eval bundle |
|---|---|---|
| Issue body (bug reporter) | In the issue's body > Behavior section (expected and/or actual) (or something similar) | Issue > Behavior section (expected and/or actual) (or something similar) |
| Candidate (reporduced bug/error) | In the issue's comment threads OR linked PRs > Behavior section (expected and/or actual) (or something similar) | Candidate repro report > Behavior section (expected and/or actual) (or something similar) |

- The issue should show the expected vs actual behavior.
- The candidate should verify the same behavior is present during reproduction.

## Honesty

<!-- Where claims and their backing meet: how to tell a report that
says exactly what happened (including an honest cannot-reproduce) from
one that claims more than its evidence shows. -->

| Signal | On github.com | In the eval bundle |
|---|---|---|
| Matching errors | In the issue's comment threads OR linked PRs > bug/error matches reported bug/error in the issue's body | Candidate repro report > bug/error matches reported bug/error in issue |
| Fixed scope | In the issue's comment threads OR linked PRs > reproduced bug is within the scope of the reported bug and doesn't claim/promise to fix any extended issues | Candidate claim comment OR Candidate repro report > reproduced bug is within the scope of the reported bug and doesn't claim/promise to fix any extended issues |

- The candidate's reproduced bug/error should match the reported bug/error in the issue.
- The candidate should not try to fix a bug outside the scope of the issue.
- If another (out of scope) bug is found, the candidate should open a new issue or report it to the maintainers, and not include it in their fix for the current issue.
- If the candidate cannot reproduce the bug/error, they should let the maintainers know about it and explain why they weren't able to reproduce it.

## Comms

<!-- Where the words meet the repo: the claim comment against the
issue, the comments against the repo's stated templates and
contribution policy (including AI-use disclosure requirements), and
what specific-and-honest looks like next to boilerplate. -->

| Signal | On github.com | In the eval bundle |
|---|---|---|
| AI disclosure | repo > CONTRIBUTING.md & issue's comment threads OR linked PRs | Repo facts > contribution policy & Candidate claim comment OR Candidate repro report |
| On topic discussion | In the issue's comment threads | Thread highlights & Candidate claim comment |

- The comment thread discussions and the candidate claim comment should only address the issue or related topics.
- The candidate claim comment and candidate repro report language should be formal and friendly.
- If there is a disagreement, it should have a respectful tone.
- No personal details (of the candidate, bug reporter, maintainers, etc) should be included.
- If the repo has AI disclosure policy, and the candidate has used AI in their workflow, they should disclose that.