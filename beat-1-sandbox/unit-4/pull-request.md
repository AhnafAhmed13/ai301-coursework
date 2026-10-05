# Unit 4 — Test and Submit

Path: `beat-1-sandbox/unit-4/pull-request.md`

Record of the pull request you opened against the Path Review repo, and of the evaluation
runs that produced `eval-run.txt`. This file is graded at the path above; a copy kept
anywhere else in the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the wrong
label is not graded.

---

## Your pull request

**Pull request**

[Link to the pull request you opened. It must be the pull request's own page on the Path
Review repo, not your fork's branch page.]

> https://github.com/codepath/pathreview-ai301-fa26-s1/pull/90

**Branch**

[The name of the branch the pull request comes from, exactly as it appears in your fork.
The naming shape is a type prefix, then the issue number, then a short description. **The
issue number in the branch name must be the number of the issue the pull request fixes** —
a name carrying any other number does not satisfy this field.]

> fix/70-readme-parser-test-fixture

## Eval iterations

Answer all four sections. Quote source text directly; paraphrase does not satisfy these
fields.

**Run history**

[The agreement score of each run you did, in order. A single run is a complete answer if
only one run occurred. **The last score in your list must match the agreement line in the
`eval-run.txt` you committed** — that file is the record of your final run.]

> 19

**Package analysis**

[Pick one scored package (`pkg-01` through `pkg-20` — the four `calib-` packages are never
scored). Name it by id, say what your rubric decided and what the gold label said, and
explain why your rubric read it that way.]

Rubric:
```
item    category        gold    verdict  agree  note
pkg-01  standards-wall  reject  reject   yes
```

Gold label:
```json
{"id": "pkg-01", "source": "pandas-dev/pandas#66657", "category": "standards-wall", "calibration": false, "verdict": "reject",
     "note": "solid C-parser fix with decisive ASAN evidence, but pandas' required PR checklist is visibly ignored: no closes #xxxx, no checklist, and the stated whatsnew entry is absent from the diff"}
```

**Check rationale**

[Quote one check from the `rubric.md` you uploaded to `tools/pr-precheck/`, exactly as it reads now.
Then say why it reads that way — what you revised to get there, or what you rejected in
favour of it.]

| No extra scope (silent drift) | The diff's changed files and hunks read against the plan's stated boundary, its "Not in scope" list, and its deviation notes. See [Plan fidelity](references/evidence-guide.md#plan-fidelity-harness-category-silent-drift). | Every changed file and hunk falls inside the plan's boundary or a deviation note. Fail if a hunk adds something the plan never names or scopes out (a new flag, config option, rewrite, or reworded unrelated text) with no note. | required |

**Trade-offs**

[Every check gives something up. Any one of these is a complete answer: a package whose
result it changes, a canary you re-ran with `--only`, a case you accept it will miss, or a
stated reason nothing changed elsewhere. "Nothing changed, and here is how I know" earns
the point in full when the reason follows.]

Nothing changed, this is a required check

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/pr-precheck/`.
