# Voice guide: how I talk upstream

<!--
THIS IS A CARRY-OVER SLOT, not a new hole. You wrote this guide in
week 2; paste your filled week-2 voice-guide.md here, whole. It is not
re-authored and it is not graded as new work this week.

Then reread it with the plan comment in mind. Your claim and repro
comments promised and reported; a plan comment commits you to an
approach in front of the people who maintain the code. If your rules
do not cover that register (for example: how you state an approach you
are not certain of, or how you respond when a maintainer already
suggested a direction), extend the guide with what it needs. Extending
is allowed and encouraged; starting over is not required.

Live mode reads this file before your plan comment goes out and
reports any rule your draft breaks. Eval mode ignores it entirely,
because your voice is yours and carries no gold labels.
-->

## Who I am in threads

<!-- Paste your week-2 section here. -->

I'm a TF from CodePath's AI 301 course.
I want to contribute to PathReview as part of the TF weekly prep task.

## Rules I write by

<!-- Paste your week-2 rules here, wrong/right pairs and all. Add any
rule the plan-comment register needs that your week-2 comments did
not. -->

### Rule: Include environment record

Include the operating system, app, build, toolkit, release etc version.

- Wrong: tested on the latest release
- Right:
    Environment:
    - Operating System: MacOS 27.0 (26A428)
    - Release: (e.g., v2.3.1)
    - Language: (e.g., Python3.14)
    - Installed via: (e.g., homebrew)
    - Other toolkits based on the template/issue

### Rule: Include steps used to reproduce bug

Include the exact chain of commands used to reproduce the bug. Remove any personally identifiable information. Replace username with `<user>/<username>`. Replace sensetive information (file/folder name/content) with `...`. Truncate long error messages and only show the relevant parts. Use comments to signal keyboard inputs (if needed).

- Wrong: i was able to reproduce the bug by following the steps mentioned above.
- Right:
    Steps used to reproduce the bug:
    - a detalied chain of commands:
        - `cd folder`
        - `python3 app.py`
        - `# keyboard input: cmd+f`
    - failed unit tests:
        - `pytest test/unit/function_test.py`
        - passed 5/10 tests
        - failed tests: ...

### Rule: Include expected vs actual behavior

Include what the expected behavior was and what is the (current) actual behavior.

- Wrong: didn't behave as expected
- Right:
    - Expected: raise ZeroDivisionException
    - Actual: no exception raised, instead program breaks on division by zero

### Rule: Include cause / diagnosis

Include what the cause of the issue is, and cite the repro evidence that shows it — a stated cause with nothing behind it is a guess, not a diagnosis.

- Wrong: the bug happens because of a race condition somewhere in the sync code
- Right:
    Cause: `fetchData()` in `sync.py` runs before the connection pool reports ready, so the first call after startup reads a stale cache slot instead of raising. Repro steps 2-3 show the stale value only on the first call after a cold start.

### Rule: Include scope

Include in-scope and not-in-scope, naming the specific files each covers.

- Wrong: I'll fix the sync issue, and clean up the module while I'm in there
- Right:
    In scope: `sync.py` (`fetchData()`), `pool.py` (`is_ready()`)
    Not in scope: the retry-logic rewrite in `retry.py` (tracked separately in #482)

### Rule: Include changes made

Include what change will be made and its intended effect, and confirm the effect stays inside scope.

- Wrong: I'll fix the sync issue
- Right:
    Change: add an `is_ready()` check before `fetchData()` reads from the pool in `sync.py`; if not ready, raise `ConnectionNotReady` instead of returning the stale cache slot.
    Effect: no behavior change once the pool is warm; before that, callers get an explicit exception instead of stale data. No other files touched.

### Rule: Include steps to execute/test the changes

Include steps to execute/test the changes made. Steps should match the repro report's steps.

- Wrong: I'll test it and make sure it works
- Right:
    Test plan (reuses repro steps 1-3):
    - `cd folder && python3 app.py --cold-start`
    - call `fetchData()` immediately after startup
    - expected: raises `ConnectionNotReady`
    - `pytest test/unit/sync_test.py::test_cold_start_raises`

### Rule: Include expected result

This is a plan, not a build report: state the result expected once the change above is made, not results already produced. If the fix would only partially resolve the reported issue, say that plainly instead of implying it's fully fixed.

- Wrong: this will fix the issue
- Right:
    Expected result: `test_cold_start_raises` passes; existing `test_warm_start` tests are unaffected. This addresses the reported freeze on cold start; it does not address the separate slow-warm-up behavior mentioned in the thread, which is out of scope for this fix.

### Rule: Include risks / unknowns

Name what you're not sure about: an untested edge case, an assumption behind the diagnosis, a part of the fix you couldn't verify. State confidence only as strong as the repro evidence supports.

- Wrong: this fix resolves the issue
- Right:
    Risks/unknowns: verified against the reported cold-start case (repro steps 1-3). Not tested against a warm restart after a failed connection; that path is untouched by this change and could still hit the same bug.

### Rule: Disclose AI use

If the repo's CONTRIBUTING.md or issue template asks for AI-use disclosure, include it plainly. Name the tool and what it was used for.

- Wrong: used some AI assistance while writing this
- Right:
    AI use: Claude Code was used to draft this plan. The diagnosis, scope, and test plan were reviewed and verified against the repro evidence before posting.

### Rule: Acknowledge a maintainer's suggested direction

If a maintainer already proposed an approach on the thread, say so, and state whether the plan follows it or diverges from it, and why.

- Wrong: posting a plan that doesn't mention an existing maintainer suggestion already on the thread
- Right:
    This follows the approach @maintainer suggested in the thread (check pool readiness before the read). One change from that suggestion: raising `ConnectionNotReady` instead of retrying, since the repro evidence shows retries silently returning stale data instead of failing loudly.


## Things I never post

<!-- Paste your week-2 list here; extend it if planning tempts you
toward new ones (overpromised timelines are the classic). -->

- Never share any personally identifiable / sensitive information.
- Never overpromise or promise any fix outside of the scope of the issue.
- Always use formal and friendly language.
- If there is any disagreement, maintain professional and respectful tone.
- Never harshly criticize an ambigious/confusing/unnecessary issue, ask for more clarity or provide constructive feedback.
- If the maintainer/bug reporter doesn't respond to claim comment / repro report for at least 7 days (or minimum response time stated in CONTRIBUTING.md), add a friendly follow-up comment in the same thread. Tag a general maintainer tag / bot to seek attention.
- Use Simple Sentence. Avoid Common AI patterns (not this but that, semicolons, em-dashes, etc)
- Never omit AI-use disclosure when the repo's CONTRIBUTING.md or issue template asks for it.
- Never post a plan as if it's risk-free or fully verified when parts of it are still an assumption or untested.
- Never post a plan on a thread where a maintainer already suggested a direction without acknowledging it.