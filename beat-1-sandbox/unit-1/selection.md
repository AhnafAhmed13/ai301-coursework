# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the
wrong label is not graded.

---

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/70

**Verdict output**

[Your skill's live-mode output for this issue, pasted verbatim and ending with the
fenced JSON verdict block. A summary does not satisfy this field.]

**The verdict must record `accept` for this issue.** Choose an issue your own skill
accepts. If your skill rejects every candidate you try, that is a signal about your
rubric rather than about the issues: revise it and re-run — retries are unlimited and a
partial re-run costs about $0.20 — or run the skill on different candidates. Output
recording `reject` for the issue you chose earns no credit for this field.


Grading: Issue #70 — "README parser test fixture is indented, so it contains no headings"

┌─────────────────────────┬───────────┬─────────┬────────────────────────────────────────────────────────────────────┐
│          Check          │  Weight   │  Grade  │                              Evidence                              │
├─────────────────────────┼───────────┼─────────┼────────────────────────────────────────────────────────────────────┤
│ Recent default-branch   │ preferred │ pass    │ Last commit 2026-09-16, 5 days before capture (today 2026-09-21)   │
│ commits                 │           │         │                                                                    │
├─────────────────────────┼───────────┼─────────┼────────────────────────────────────────────────────────────────────┤
│ Who is committing       │ preferred │ pass    │ All 5 recent commits by human user Aburke225, no bots              │
├─────────────────────────┼───────────┼─────────┼────────────────────────────────────────────────────────────────────┤
│ Issue response latency  │ required  │ pass    │ Last issue (#73) opened 2026-09-16 (within 180d); one sampled      │
│                         │           │         │ maintainer response (#52, COLLABORATOR) took ~6 days               │
├─────────────────────────┼───────────┼─────────┼────────────────────────────────────────────────────────────────────┤
│ Maintainer activity in  │ preferred │ fail    │ Issue #70 has 0 comments                                           │
│ this thread             │           │         │                                                                    │
├─────────────────────────┼───────────┼─────────┼────────────────────────────────────────────────────────────────────┤
│ Release recency         │ required  │ pass    │ No releases published (404) — conditional "if published" doesn't   │
│                         │           │         │ apply                                                              │
├─────────────────────────┼───────────┼─────────┼────────────────────────────────────────────────────────────────────┤
│ Last push               │ preferred │ pass    │ Repo pushed_at 2026-09-16, 5 days before capture                   │
├─────────────────────────┼───────────┼─────────┼────────────────────────────────────────────────────────────────────┤
│ Archived flag           │ required  │ pass    │ archived: false                                                    │
├─────────────────────────┼───────────┼─────────┼────────────────────────────────────────────────────────────────────┤
│ Adoption scale          │ preferred │ fail    │ 1 star                                                             │
├─────────────────────────┼───────────┼─────────┼────────────────────────────────────────────────────────────────────┤
│ Issue availability      │ required  │ pass    │ state: open                                                        │
├─────────────────────────┼───────────┼─────────┼────────────────────────────────────────────────────────────────────┤
│ Newcomer friendly       │ preferred │ fail    │ Labels: bug, ingestion, tier-2 — no "good first issue"             │
├─────────────────────────┼───────────┼─────────┼────────────────────────────────────────────────────────────────────┤
│ Issue scope             │ required  │ pass    │ Single bounded bug (fixture indentation), no "Out of scope"        │
│                         │           │         │ mention, not a tracking issue                                      │
├─────────────────────────┼───────────┼─────────┼────────────────────────────────────────────────────────────────────┤
│ Issue description       │ preferred │ pass    │ Names failing test, files involved, xfail annotation to remove,    │
│                         │           │         │ effort estimate                                                    │
├─────────────────────────┼───────────┼─────────┼────────────────────────────────────────────────────────────────────┤
│ Non pure usage question │ required  │ pass    │ Bug report, not a support question                                 │
├─────────────────────────┼───────────┼─────────┼────────────────────────────────────────────────────────────────────┤
│ Age and history         │ preferred │ pass    │ Opened 2026-09-10, well within 2 years                             │
├─────────────────────────┼───────────┼─────────┼────────────────────────────────────────────────────────────────────┤
│ Assignee                │ preferred │ pass    │ No assignees                                                       │
├─────────────────────────┼───────────┼─────────┼────────────────────────────────────────────────────────────────────┤
│ Linked PRs              │ preferred │ pass    │ Search found 0 PRs referencing #70                                 │
├─────────────────────────┼───────────┼─────────┼────────────────────────────────────────────────────────────────────┤
│ Claim comments          │ required  │ pass    │ 0 comments — no claim comments exist                               │
├─────────────────────────┼───────────┼─────────┼────────────────────────────────────────────────────────────────────┤
│ Label freshness         │ preferred │ pass    │ Opened 11 days before capture, within 180 days                     │
├─────────────────────────┼───────────┼─────────┼────────────────────────────────────────────────────────────────────┤
│ Contribution policy     │ preferred │ pass    │ No CONTRIBUTING.md — silence passes                                │
├─────────────────────────┼───────────┼─────────┼────────────────────────────────────────────────────────────────────┤
│ Dedicated AI policy     │ preferred │ fail    │ No AI_POLICY.md/AGENTS.md found                                    │
│ files                   │           │         │                                                                    │
├─────────────────────────┼───────────┼─────────┼────────────────────────────────────────────────────────────────────┤
│ Templates               │ preferred │ unclear │ Not checked (PR/issue template disclosure checkbox)                │
└─────────────────────────┴───────────┴─────────┴────────────────────────────────────────────────────────────────────┘

All required checks pass → accept.

```json
{
  "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/70",
  "checks": [
    {"name": "Recent default-branch commits", "grade": "pass", "evidence": "Last commit 2026-09-16, 5 days before capture"},
    {"name": "Who is committing", "grade": "pass", "evidence": "All 5 recent commits by human author Aburke225, no bots"},
    {"name": "Issue response latency", "grade": issue opened 2026-09-16 (within 180d); sampledmaintainer (COLLABORATOR) response on #52 took ~6 days"},
    {"name": "Maintainer activity in this threaence": "Issue #70 has 0 comments"},
    {"name": "Release recency", "grade": "pass", "evidence": "No releases published (404) — conditional pass"},
    {"name": "Last push", "grade": "pass", "evi26-09-16, 5 days before capture"},
    {"name": "Archived flag", "grade": "pass", "evidence": "archived: false"},
    {"name": "Adoption scale", "grade": "fail",ount: 1"},
    {"name": "Issue availability", "grade": "pass", "evidence": "state: open"},
    {"name": "Newcomer friendly", "grade": "faie bug, ingestion, tier-2 — no good-first-issuelabel"},
    {"name": "Issue scope", "grade": "pass", "efixture bug, no 'Out of scope' mention, not atracking issue"},
    {"name": "Issue description", "grade": "pasling test, files involved, xfail annotation toremove, effort estimate 2-4h"},
    {"name": "Non pure usage question", "grade" report describing a concrete defect, not asupport question"},
    {"name": "Age and history", "grade": "pass"-09-10, within last 2 years"},
    {"name": "Assignee", "grade": "pass", "evidence": "assignees: none"},
    {"name": "Linked PRs", "grade": "pass", "evund 0 PRs referencing issue 70"},
    {"name": "Claim comments", "grade": "pass", "evidence": "0 comments on the issue — no claim comments"},
    {"name": "Label freshness", "grade": "pass"d 11 days before capture, within 180 days"},
    {"name": "Contribution policy", "grade": "pass", "evidence": "No CONTRIBUTING.md found — silence passes per rubric
guidance"},
    {"name": "Dedicated AI policy files", "grade": "fail", "evidence": "No AI_POLICY.md or AGENTS.md found in repo"},
    {"name": "Templates", "grade": "unclear", "ate AI-disclosure checkbox not checked"}
  ],
  "verdict": "accept"
}
```

---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

[The agreement score of each run you did, in order. A single run is a complete answer if
only one run occurred. **The last score in your list must match the agreement line in the
`eval-run.txt` you committed** — that file is the record of your final run.]

>10
16
16
16
19

**Issue analysis**

[One scored issue, identified by id (`issue-01` through `issue-20`; the `calib-`
issues are not scored). State your rubric's decision, the gold label, and the
reasoning that produced your rubric's result.]

Rubric's decision:
```
      {
      "id": "issue-01",
      "verdict": "accept",
      "failed_checks": [
        "Maintainer activity in this thread",
        "Newcomer friendly",
        "Templates"
      ],
      "checks": [
        {
          "name": "Recent default-branch commits",
          "grade": "pass",
          "evidence": "last default-branch commit 2026-08-04, 1 day before capture"
        },
        {
          "name": "Who is committing",
          "grade": "pass",
          "evidence": "last 5 commits by codewithdaniel1 and danyeaw, no [bot] authors"
        },
        {
          "name": "Issue response latency",
          "grade": "pass",
          "evidence": "last issue opened 2026-08-04 (within 180 days); only available data point #16275 = 32.9 days (<60)"
        },
        {
          "name": "Maintainer activity in this thread",
          "grade": "fail",
          "evidence": "0 comments total on the issue"
        },
        {
          "name": "Release recency",
          "grade": "pass",
          "evidence": "latest release 26.7.0 on 2026-07-31, within 180 days of 2026-08-05 capture"
        },
        {
          "name": "Last push",
          "grade": "pass",
          "evidence": "last push to any branch 2026-08-04, within 30 days of capture"
        },
        {
          "name": "Archived flag",
          "grade": "pass",
          "evidence": "repo facts state archived: no"
        },
        {
          "name": "Adoption scale",
          "grade": "pass",
          "evidence": "repo has 7481 stars"
        },
        {
          "name": "Issue availability",
          "grade": "pass",
          "evidence": "issue state: open"
        },
        {
          "name": "Newcomer friendly",
          "grade": "fail",
          "evidence": "labels: type::documentation only, no 'good first issue' label"
        },
        {
          "name": "Issue scope",
          "grade": "pass",
          "evidence": "single feature/docs proposal with concrete plan, not a tracking/umbrella issue, no 'Out of scope' mention"
        },
        {
          "name": "Issue description",
          "grade": "pass",
          "evidence": "issue contains detailed proposed changes and content notes acting as a suggested fix"
        },
        {
          "name": "Non pure usage question",
          "grade": "pass",
          "evidence": "issue proposes new documentation structure, not a usage question"
        },
        {
          "name": "Age and history",
          "grade": "pass",
          "evidence": "opened 2026-07-31, well within 2 years"
        },
        {
          "name": "Asignee",
          "grade": "pass",
          "evidence": "repo facts: assignees: none"
        },
        {
          "name": "Linked PRs",
          "grade": "pass",
          "evidence": "repo facts: linked PRs: none"
        },
        {
          "name": "Claim comments",
          "grade": "pass",
          "evidence": "0 comments total, so no claim comment exists"
        },
        {
          "name": "Label freshness",
          "grade": "pass",
          "evidence": "issue opened 2026-07-31, captured 2026-08-05, well within 180 days"
        },
        {
          "name": "Contribution policy",
          "grade": "pass",
          "evidence": "CONTRIBUTING.md 'Generative AI' section: 'generative AI tools welcome'"
        },
        {
          "name": "Dedicated AI policy files",
          "grade": "pass",
          "evidence": "CONTRIBUTING.md has a dedicated 'Generative AI' section"
        },
        {
          "name": "Templates",
          "grade": "fail",
          "evidence": "no mention of an AI-use disclosure checkbox in issue or repo facts"
        }
      ],
      "error": null
    }
```

Gold label:
```
    {"id": "issue-01", "source": "conda/conda#16475", "category": "clear-accept", "calibration": false, "verdict": "accept", "note": "docs task with a stated home and scope; active repo, unclaimed"},
```


**Check rationale**

[One check from the `rubric.md` uploaded to `tools/issue-select/`, quoted as it is
currently written, with the reasoning behind its current form.]

> Issue response latency | Repo facts > maintainer first-response sample | last issue opened was within 180 days & average response time < 60 days (if available) | required |

**Trade-offs**

[What the quoted check gives up. Any one of these is a complete answer: an issue whose
result it changes, a canary you re-ran with `--only`, a case you accept it will miss, or a
stated reason nothing changed elsewhere. "Nothing changed, and here is how I know" earns
the point in full when the reason follows.]

> Started with average response time < 14 to 28 to 30 to finally 60. Changed reject to accept for 10 issues.

---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

[Answer all three:

1. The issue's fit to your interests and to the time available.
> Yes
2. What the verdict identified correctly, and what you weighed that the rubric could not.
> Everything identified as expected
3. The anticipated difficulty in claiming it.]
> Since it's a sandbox environment, there should not be any difficulty

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
