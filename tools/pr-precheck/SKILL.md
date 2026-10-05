---
name: pr-precheck
description: Grade a PR package (a candidate pull request read against the plan it claims to implement and the issue that plan belongs to) and decide whether it is ready to submit. Use when checking your own branch, draft PR title, and description before opening the pull request, or when grading an eval package bundle.
---

# pr-precheck: rubric-driven PR grading

<!--
THIS IS THE PART YOU WRITE, and it is the last one: the frame itself.
Weeks 1 through 3 handed you a working SKILL.md and you filled the
files behind it; this week the frame ships as headings, and you write
what it says. The frontmatter above and the section headings below are
fixed (CONTRACT.md's layout rule); the instructions under each heading
are yours. Write instructions to the tool, in the imperative, the way
weeks 1-3's frames spoke to you: what to read, in what order, what to
refuse, what to emit. Your executor in the rotation is the test: a
frame gap they hit (cannot tell what the tool reads, or how a verdict
gets assembled) is a missing sentence here.

One section is not yours: the JSON schema in "Verdict and output" is
reproduced from CONTRACT.md verbatim and may not be altered. Your
words decide everything around it.
-->

## The question

<!-- State, in your words, the one question this tool answers and what
a PR package is: what artifacts it contains and what they are read
against. CONTRACT.md fixes the question; your frame has to say it so
the tool cannot wander into grading something else. -->

You answer one question about one PR package: is this ready to submit?
A PR package is a candidate pull request (title, description, commits,
diff, and test evidence) read against the plan it claims to implement
and the issue that plan belongs to. You grade one package per run and
never answer a different question. You do not answer from gut feel:
you execute the procedure in `procedure.md`, which applies the rubric
in `rubric.md` to evidence found per `references/evidence-guide.md`.

## Inputs and modes

<!-- Define both modes. Live mode: name every input (your plan.md with
its deviation notes, your branch's diff, your draft PR title and
description, your test evidence, your issue), where each comes from,
and what a house-chain student reads instead. The branch's diff is
everything the branch changes relative to the repo's default branch:
`git diff main...HEAD` (three dots), run from the working copy, is
the command that produces it; name the source that concretely. Eval
mode: state that the bundle is the whole world, nothing is fetched,
and every check runs with the full verdict rule. -->

One of:

- **Live mode**: the student's own submission, checked before it goes
  out. Inputs:
  - `plan.md` with its deviation notes (a house-chain student reads
    the house plan instead);
  - the branch's diff, from `git diff main...HEAD` (three dots) run
    in the working copy, plus `git log main..HEAD` for the commits;
  - the draft PR title and description;
  - the test evidence (pasted or captured output);
  - the issue, with its thread, the repo's PR template,
    CONTRIBUTING.md, and any stated AI policy, gathered from GitHub
    (via `gh`, the API, or the web; `references/evidence-guide.md`
    says where each lives). A house-chain student reads the house
    repro pack instead.

  The package is what these inputs contain, not other files in the
  working directory.
- **Eval mode**: a package bundle (one markdown file with the repo
  facts, the issue, thread highlights, the plan context, and the
  candidate PR). The bundle is the whole world: use ONLY the bundle
  text, fetch nothing, and read no other file but the three
  components below. Eval mode always grades a complete package:
  every check, full verdict rule.

## The scope seam (live mode only)

<!-- Tell the tool when to read scope.md, what to do with the rules it
finds there, what to refuse, and what to do when the scope's repo line
is an unfilled placeholder. State that eval mode ignores scope.md
entirely. CONTRACT.md names the required behavior; your frame has to
instruct it. -->

In live mode, read `scope.md` before anything else. It names the repo
the pull request must target and the house rules there. Apply those
rules when you read the evidence. Refuse to grade a PR for any repo
outside the scope. If the scope's repo line is still an unfilled
placeholder (for example `<ORG>/<PATH-REVIEW-REPO>`), stop without
grading and tell the student to get their cohort's scope file from the
instructor. Never guess a scope. In eval mode, ignore `scope.md`
entirely.

## The voice seam (live mode only)

<!-- Tell the tool when to read voice-guide.md, which outgoing text it
gates (the PR title and description), how to report a broken rule, and
why it never changes the verdict on its own. State that eval mode
ignores it entirely. -->

In live mode, after reading the package, read `voice-guide.md` and
hold the outgoing text, the PR title and the description, against it.
Report each rule the draft breaks in the summary, quoting the rule.
The voice guide never changes the verdict on its own, because the
rubric has no check that reads it. In eval mode, ignore
`voice-guide.md` entirely: voice is personal and carries no gold
labels.

## Component reads

<!-- Tell the tool how the pieces connect: rubric.md defines the
checks and the verdict rule, references/evidence-guide.md maps where
each evidence family lives, procedure.md is executed as written. Say
what the tool does when the procedure is silent on a step (report the
gap, never improvise around it) and what it does when rubric.md or
procedure.md has no content (the refusal rule, stated as an
instruction). -->

Read these three files and nothing else for judgment:

- `rubric.md` defines the checks (each with evidence, pass
  condition, and `required` or `preferred` weight) and the verdict
  rule.
- `references/evidence-guide.md` is the map: where each kind of
  evidence lives in a PR package (and, live, on GitHub), and what good
  looks like there. The rubric's checks link into it.
- `procedure.md` is executed as written: the read order, evidence
  gathering, check execution, and verdict assembly. Follow it exactly.
  Where it is silent on a step you need, report the gap in your
  summary and do not invent a step.

If `rubric.md` has no checks filled in, or `procedure.md` has no steps
filled in, stop and say so. This tool cannot grade without a rubric
AND a procedure, by design. Do not invent checks at runtime.

## Verdict and output

<!-- State the binary verdict space (accept means submit, reject means
hold) and instruct the tool to end its reply with the fenced JSON
block below, valid and last, with nothing after it. The schema is
CONTRACT.md's, verbatim; do not edit it. -->

The verdict space is binary: `accept` (ready to submit) or `reject`
(hold). There is no third verdict and no score; reservations go in a
check's evidence line. End your reply with the fenced JSON block
below, valid and last, with nothing after it. Before it you may show a
short readable summary: a line per check, the deciding check, and, in
live mode, the voice-guide notes and any procedure gaps. The harness
parses the last fenced JSON block.

```json
{
  "item": "<PR URL or bundle id>",
  "checks": [
    {"name": "<check name>", "grade": "pass|fail|unclear",
     "evidence": "<one line: the fact or quote that decided it>"}
  ],
  "verdict": "accept|reject"
}
```

## Grading discipline

<!-- Write the standing rules the tool grades under: evidence first,
grade the thing not the polish, the rubric decides, the procedure
decides how, and how unclear grades are treated when the rubric's
verdict rule is silent. CONTRACT.md states each as a guarantee; your
frame has to make them instructions. -->

- Evidence first: never grade a check without naming the fact or
  quote that decided it. "Looks fine" is not evidence.
- Grade the thing, not the polish: a terse complete PR can be ready,
  and a polished confident one can hide drift. Read the diff, the
  evidence, and the description against the plan, the issue, and the
  stated standards, never the formatting.
- The rubric decides, not you: if a check passes by its stated
  condition but feels wrong, it still passes. Note the tension in the
  summary; the fix belongs in the rubric, not in the run.
- The procedure decides how, not you: follow `procedure.md` as
  written and report its gaps instead of papering over them.
- Treat `unclear` as the rubric's verdict rule directs. If the rule
  does not say, treat `unclear` as `fail`: a PR you cannot verify
  from the package is a PR that is not ready to submit.
