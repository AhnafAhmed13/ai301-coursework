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

## Deviations

[What changed between the plan you posted and the change you built, and
why. If nothing changed, say so in your own words - "nothing changed;
the plan held" earns these points in full. Leaving this blank does not.]

Nothing changed; the plan held. Discovered alternative solutions but the initial solution fixes the issue.