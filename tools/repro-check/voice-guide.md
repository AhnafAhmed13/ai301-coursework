# Voice guide: how I talk upstream

<!--
THIS IS THE PART YOU WRITE (new this week). Live mode reads this file
before any comment of yours goes out the door; eval mode ignores it
entirely, because your voice is yours and carries no gold labels.

This is not etiquette. "Be polite and concise" is advice for everyone
and therefore rules for no one. Write rules YOU need, in your own
words, each one concrete enough that the skill can hold a draft
against it and say which rule it breaks.

Three sections. Fill all three.
-->

## Who I am in threads

<!-- 2-3 lines. Who is talking when you comment on an issue: your
experience level stated plainly, what you are doing in this repo, what
readers can expect from you. This is the register your rules protect. -->

I'm a TF from CodePath's AI 301 course.
I want to contribute to PathReview as part of the TF weekly prep task.

## Rules I write by

<!-- 3-5 rules, drafted from the lecture's slide-12 moment. Each rule
needs a wrong/right pair from your own hand: one line you might
actually have written that breaks the rule, and the line you would
post instead. The pair is what makes a rule executable; a rule without
one is a wish.

Format each rule like this:

### Rule: <short name>

<The rule, one or two sentences.>

- Wrong: "<a line that breaks it>"
- Right: "<the line to post instead>"
-->

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

## Things I never post

<!-- A short list. Promises you cannot keep, tones you refuse,
shortcuts you know you reach for when tired. The skill quotes this
list back at you when a draft crosses it. -->

- Never share any personally identifiable / sensitive information.
- Never overpromise or promise any fix outside of the scope of the issue.
- Always use formal and friendly language.
- If there is any disagreement, maintain professional and respectful tone.
- Never harshly criticize an ambigious/confusing/unnecessary issue, ask for more clarity or provide constructive feedback.
- If the maintainer/bug reporter doesn't respond to claim comment / repro report for at least 7 days (or minimum response time stated in CONTRIBUTING.md), add a friendly follow-up comment in the same thread. Tag a general maintainer tag / bot to seek attention.