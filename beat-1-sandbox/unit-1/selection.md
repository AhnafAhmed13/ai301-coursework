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

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/68

**Verdict output**

[Your skill's live-mode output for this issue, pasted verbatim and ending with the
fenced JSON verdict block. A summary does not satisfy this field.]

**The verdict must record `accept` for this issue.** Choose an issue your own skill
accepts. If your skill rejects every candidate you try, that is a signal about your
rubric rather than about the issues: revise it and re-run — retries are unlimited and a
partial re-run costs about $0.20 — or run the skill on different candidates. Output
recording `reject` for the issue you chose earns no credit for this field.

```json
{
  "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/68",
  "checks": [
    {"name": "Recent default-branch commits", "grade": "pass", "evidence": "last main commit 2026-08-24 (23 days ago, < 60)"},
    {"name": "Who is committing", "grade": "pass", "evidence": "last 5 main commits all authored by Aburke225, not
a [bot]"},
    {"name": "Issue response latency", "grade": "pass", "evidence": "newest issue #72 opened 2026-09-10 (6 days
ago); no issue has any comment, so no respole"},
    {"name": "Maintainer activity in this thread", "grade": "fail", "evidence": "issue #68 has 0 comments; no
Owner/Member/Collaborator reply"},
    {"name": "Release recency", "grade": "pass", "evidence": "/releases returns [] — no release published,
condition not triggered"},
    {"name": "Last push", "grade": "pass", "evidence": "repo pushed_at 2026-09-10 (6 days ago, < 30)"},
    {"name": "Archived flag", "grade": "pasived: false"},
    {"name": "Adoption scale", "grade": "fail", "evidence": "stargazers_count: 0 (< 100)"},
    {"name": "Issue availability", "grade":e state: open"},
    {"name": "Newcomer friendly", "grade": "pass", "evidence": "labels: bug, good first issue, rag, tier-1"},
    {"name": "Issue scope", "grade": "pass"in KeywordSearcher.search() naming 2 files,2-4h estimate; no sub-item list and no 'Out of scope'"},
    {"name": "Issue description", "grade": s expected behavior ('should return an emptyresult list'), relevant files, and the xfail marker to remove"},
    {"name": "Non pure usage question", "gr"reports a ZeroDivisionError crash and thefix required, not a how-do-I question"},
    {"name": "Age and history", "grade": "p_at 2026-09-10, 6 days old (< 2 years)"},
    {"name": "Asignee", "grade": "pass", "evidence": "assignees: []"},
    {"name": "Linked PRs", "grade": "pass",s in the timeline and the repo has 0 PRstotal; only a 2026-09-16 'referenced' commit in classmate yulijasso's fork, which the Path Review house rule does
not treat as a block"},
    {"name": "Claim comments", "grade": "pass", "evidence": "comments: 0 on the thread"},
    {"name": "Label freshness", "grade": "pirst issue' labeled 2026-09-10, 6 days ago (< 180)"},
    {"name": "Contribution policy", "grade"s/CONTRIBUTING.md states no restriction onAI-assisted work; silence passes"},
    {"name": "Dedicated AI policy files", ": "no AI_POLICY.md, AI_USAGE_POLICY.md, orAGENTS.md in the repo tree"},
    {"name": "Templates", "grade": "fail", REQUEST_TEMPLATE.md checklist covers CI,tests, lint, typecheck and xfail removal — no AI-use disclosure box"}
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
