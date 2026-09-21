# Unit 2 — Claim and Reproduce

Path: `beat-1-sandbox/unit-2/reproduction.md`

Record of your claim and reproduction on the issue you chose in Unit 1, and of the
evaluation runs that produced `eval-run.txt`. This file is graded at the path above; a copy
kept anywhere else in the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the wrong
label is not graded.

---

## Your identity upstream

**GitHub username**

[Your GitHub username, exactly as it appears on your profile — no `@`, no profile URL. Your
comments upstream are identified by this name.]

AhnafAhmed13

---

## Posted upstream

**Claim comment**

[Link to the comment where you claimed the issue. Use the comment's own permalink, not the
issue page on its own. **Then paste the text of that comment underneath the link** — the
pasted text is what this field is graded on, so copy across what you actually posted.]

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/70#issuecomment-5757684338

Hey, I'm a TF from CodePath's AI 301 course. I'd like to take on this issue as part of the TF weekly prep task. Looking at the sample_readme_text() in tests/conftest.py, test_parse_standard_readme() in tests/unit/test_readme_parser.py, and parse() in ingestion/parsers/readme_parser.py, it appears that the pytest fixture is returning a sample readme text as a string with indentation which is causing the parser to miscount heading_count as 0. I will reproduce the bug locally using pytest and report back what I find.

---

**Reproduction comment**

[Link to the comment where you posted your reproduction. It must record the environment
(OS, relevant versions, code state), steps a stranger could follow, and what you observed.
**Then paste the text of that comment underneath the link** — the pasted text is what this
field is graded on, so copy across what you actually posted.]

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/70#issuecomment-5758409883

## Environment:
- Operating system: MacOS 27.0 (26A428) (arm64)
- Python 3.14.7
- Pytest 9.1.1
- colima version 0.10.3
- Docker version 29.8.1, build 4a63305d74
- Docker Compose version 5.5.1

## Steps to reproduce
`pytest tests/unit/test_readme_parser.py`
- Output:
```
========================================== test session starts ==========================================
platform darwin -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
benchmark: 5.3.0 (defaults: timer=time.perf_counter disable_gc=False min_rounds=5 min_time=0.000005 max_time=1.0 calibration_precision=10 warmup=False warmup_iterations=100000)
rootdir: .../pathreview-ai301-fa26-s1
configfile: pyproject.toml
plugins: cov-7.1.0, asyncio-1.4.0, benchmark-5.3.0, pytest_httpserver-1.1.5, anyio-4.15.1, hypothesis-6.168.0
asyncio: mode=Mode.STRICT, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
collected 15 items                                                                                      

tests/unit/test_readme_parser.py x........x.....                                                  [100%]

===================================== 13 passed, 2 xfailed in 0.17s =====================================
```
Failed test (relevant to this issue): `test_parse_standard_readme()` currently xfails as expected, per the issue's H-03 marker

## Expected behavior

The following input from `tests/conftest.py`
```
    """
    Jane Doe
    Software Engineer
    jane.doe@example.com | github.com/janedoe

    Experience:
    - Software Engineer at TechCorp (2022-2024)
      Built REST APIs using Python and FastAPI.

    Education:
    - B.S. Computer Science, State University (2022)

    Skills: Python, JavaScript, React, PostgreSQL, Docker
    """
```
should have `heading_count` > 0 in `test_parse_standard_readme()` in `tests/unit/test_readme_parser.py`

## Actual behavior

The same input fails in `assert result.metadata["heading_count"] > 0` in `test_parse_standard_readme()` in `tests/unit/test_readme_parser.py`

---

## Eval iterations

Answer all four sections. Quote source text directly; paraphrase does not satisfy these
fields.

**Run history**

[The agreement score of each run you did, in order. A single run is a complete answer if
only one run occurred. **The last score in your list must match the agreement line in the
`eval-run.txt` you committed** — that file is the record of your final run.]

> 19 19 19 18 19

**Package analysis**

[Pick one scored package (`pkg-01` through `pkg-20` — the four `calib-` packages are never
scored). Name it by id, say what your rubric decided and what the gold label said, and
explain why your rubric read it that way.]

Rubric's decision:

  ```issue-20: reject```

Gold label:

    ```json
    {
      "id": "pkg-20",
      "source": "ghostty-org/ghostty#13604",
      "category": "disclosure",
      "calibration": false,
      "verdict": "reject",
      "note": "excellent repro on every proof check; ghostty's stated AI policy requires disclosing all AI usage and the comments do not disclose (course packages are treated as AI-assisted work); the one-item category the floor exists for"
    }
    ```

Rubric rejected it because of the AI disclosure failure, same reason as the gold label.

**Check rationale**

[Quote one check from the `rubric.md` you uploaded to `tools/repro-check/`, exactly as it reads now.
Then say why it reads that way — what you revised to get there, or what you rejected in
favour of it.]


> Communication | references/evidence-guide.md > Comms | Candidate claim comment AND candidate repro report follows the repo's conventions and uses formal and friendly language with respectful tone | required |

Previously I had the AI disclosure policy check combined with Communication check. But later I seperated them to provide more priority for the AI disclosure policy.

**Trade-offs**

[Every check gives something up. Any one of these is a complete answer: a package whose
result it changes, a canary you re-ran with `--only`, a case you accept it will miss, or a
stated reason nothing changed elsewhere. "Nothing changed, and here is how I know" earns
the point in full when the reason follows.]

Package-20 was producing fluctuating results, but after the check split, it became more predictable.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/repro-check/`.
