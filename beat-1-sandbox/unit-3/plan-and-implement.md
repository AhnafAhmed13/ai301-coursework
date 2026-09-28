# Unit 3 — Plan and Build

Path: `beat-1-sandbox/unit-3/plan-and-implement.md`

Record of your plan, the branch you built it on, and the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in the
repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the wrong
label is not graded.

---

## Posted upstream

**GitHub username**

[Your GitHub username, exactly as it appears on your profile - no @, no
profile URL. Your comment upstream is identified by this name, and it is
the only thing that ties it to you. Several students may plan the same
house issue, so this is what keeps their comments off your score and
yours off theirs.]

> AhnafAhmed13

**Plan comment**

[Link to the comment where you posted your plan on the issue. Use the comment's own
permalink. **Then paste the text of that comment underneath the link** — the pasted text is
what this field is graded on, so copy across what you actually posted.]

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/70#issuecomment-5862694818

# Plan

## Environment

- Operating system: MacOS 27.0 (26A428) (arm64)
- Python 3.14.7
- Pytest 9.1.1

## Cause

The pytest fixture is returning a sample readme text as a string with indentation which is causing the parser to miscount heading_count as 0

## Scope

- **In-scope:** `sample_readme_text()` in `tests/conftest.py` and `test_parse_standard_readme()` in `tests/unit/test_readme_parser.py`
- **Not-in-scope:** `ingestion/parsers/readme_parser.py`

## Changes

1. De-indent each line of the return string in `sample_readme_text()` in `tests/conftest.py` ->
    ```py
    """
    # Weather App
    A weather forecasting application built with React and OpenWeatherMap API.

    ## Features
    - Current weather display
    - 5-day forecast
    - Location search

    ## Tech Stack
    - React 18
    - TypeScript
    - Tailwind CSS
    - OpenWeatherMap API
    """
    ```
2. Remove the `@pytest.mark.xfail` marker (manifest id H-03) above `test_parse_standard_readme()` in `tests/unit/test_readme_parser.py`

## Test plan

Reuses the repro steps above:

- `$ cd "pathreview rootdir"`
- `$ pytest tests/unit/test_readme_parser.py`

## Expected behavior

`assert result.metadata["heading_count"] > 0` passes and `test_parse_standard_readme()` passes instead of xfailing

## Risks/unknowns

- I have not verified whether `sample_readme_text()` is used as a fixture anywhere else in `tests/`. If another test depends on its current indented form, de-indenting it could change that test's behavior. The repro evidence only covers `test_parse_standard_readme()`.
- The fix assumes the parser itself is correct once given unindented input, per the issue's framing ("the parser isn't wrong"). I have not independently re-verified `readme_parser.py`'s heading-detection logic beyond what the repro evidence shows; that file is out of scope for this change.

---

## Your branch

**Branch**

[The name of the branch you built the change on, exactly as it appears in your fork. The
naming shape is a type prefix, then the issue number, then a short description. **The issue
number in the branch name must be the number of the issue you claimed** — a name carrying
any other number does not satisfy this field.]

> fix/70-readme-parser-test-fixture

**Evidence**

[Your Unit 2 reproduction steps re-run against the built change: the before, then the
after. Paste both, including the commands you ran and their output.]

Before:

```
$ cd "pathreview rootdir"
$ pytest tests/unit/test_readme_parser.py

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


After:
```
$ cd "pathreview rootdir"
$ pytest tests/unit/test_readme_parser.py

platform darwin -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
benchmark: 5.3.0 (defaults: timer=time.perf_counter disable_gc=False min_rounds=5 min_time=0.000005 max_time=1.0 calibration_precision=10 warmup=False warmup_iterations=100000)
rootdir: .../pathreview-ai301-fa26-s1
configfile: pyproject.toml
plugins: cov-7.1.0, asyncio-1.4.0, benchmark-5.3.0, pytest_httpserver-1.1.5, anyio-4.15.1, hypothesis-6.168.0
asyncio: mode=Mode.STRICT, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
collected 15 items                                                                                                                                     

tests/unit/test_readme_parser.py .........x.....                                                                                                 [100%]

============================================================ 14 passed, 1 xfailed in 0.15s =============================================================
```

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

My rubric:
```txt
item    category     gold    verdict  agree  note
pkg-01  wrong-cause  reject  reject   yes
```

Gold label:
```json
{"id": "pkg-01", "source": "httpie/cli#1838", "category": "wrong-cause", "calibration": false, "verdict": "reject",
"note": "plan blames the request-item tokenizer; the package's own control run (same items, no -v flag) parses fine, ruling the tokenizer out, and --debug shows argparse consuming positionals before the item parser runs"}
```

The plan misdiagnosed the issue. Builds the solution with the wrong cause.

**Check rationale**

[Quote one check from the `rubric.md` you uploaded to `tools/plan-check/`, exactly as it reads now.
Then say why it reads that way — what you revised to get there, or what you rejected in
favour of it.]

| plan targets the cause | references/evidence-guide.md > diagnosis & grounding and executability | the plan/approach must target the cause and not the symptoms | required |

**Trade-offs**

[Every check gives something up. Any one of these is a complete answer: a package whose
result it changes, a canary you re-ran with `--only`, a case you accept it will miss, or a
stated reason nothing changed elsewhere. "Nothing changed, and here is how I know" earns
the point in full when the reason follows.]

Nothing changed, here is how I know: got the same value with --only and full run for pkg-01

---

Related paths: `plan.md` and `eval-run.txt` in this directory; your skill's files in
`tools/plan-check/`.
