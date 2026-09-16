# Rubric: is this a good first issue?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever checks
you define here. It ships empty on purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where. Name the source
     (repo-facts block, issue body, comment thread, or the locations in
     references/evidence-guide.md). "The repo" is not a source; "the last
     5 default-branch commit dates" is.
   - Pass condition: a condition someone else could apply and get your
     answer. Prefer thresholds with numbers ("a maintainer commented
     within 30 days") over adjectives ("maintainer is responsive").
   - Weight: `required` (a fail here rejects the issue) or `preferred`
     (never changes the verdict; a nice-to-have that helps rank the
     issues you accept).

2. A verdict rule below the table: how the check grades combine into
   accept or reject, including how `unclear` is treated. The verdict
   space is binary. If you write no rule for `unclear`, the skill treats
   it as fail.

Cover what actually kills first contributions. The lecture named four
families: the maintainer is alive, the repo is in use, the scope fits a
newcomer, and nobody else is already on it. A rubric that ignores a family
will fail eval issues designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Recent default-branch commits | Repo facts > last 5 default-branch commits > dates | last default-branch commit was made within  60 days | preferred |
| Who is committing | Repo facts > last 5 default-branch commits > author names | not all commits were made by bots (username ending in [bot]) | preferred |
| Issue response latency | Repo facts > maintainer first-response sample | last issue opened was within 180 days & average response time < 60 days (if available) | required |
| Maintainer activity in this thread | Comments | at least 1 comment from Owner, Member, or Collaborator | preferred |
| Release recency | Repo facts > latest release > date | last release was within 180 days (if published) | required |
| Last push | Repo facts > last push to any branch | last push was within 30 days | preferred |
| Archived flag | Repo facts > repo > archived | repo is not archived | required |
| Adoption scale | Repo facts > repo > stars | repo has 100+ stars | preferred |
| Issue availability | Issue > state | issue is open | required |
| Newcomer friendly | Issue > labels | labels contains 'good first issue' | preferred |
| Issue scope | Issue | not an umbrella or tracking issue & doesn't mention "Out of scope" | required |
| Issue description | Issue | has acceptance-criteria checklist, reproduction steps and/or suggested fix | preferred |
| Non pure usage question | Issue | not a support request | required |
| Age and history | Issue > date | issue was opened within last 2 years | preferred |
| Asignee | Repo facts > this issue > asignee | issue is not assigned to anyone | preferred |
| Linked PRs | Repo facts > this issue > linked PRs & Comments > PR mentions | issue has no linked PRs | preferred |
| Claim comments | Comments | no claim comment within last 90 days and/or no reply or acknowledgement from maintainers | required |
| Label freshness | Issue open date vs capture date | label is within 180 days | preferred |
| Contribution policy | Repo facts > contribution policy | allows AI-assisted contribution | preferred |
| Dedicated AI policy files | Repo facts > contribution policy | has dedicated AI policy | preferred |
| Templates | Repo facts > contribution policy | has AI-use disclousure checkbox | preferred |

## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict, they
rank accepted issues; unclear counts as fail." -->

Accept if every required check passes.
Preferred checks never change the verdict, they rank accepted issues.
Unclear counts as fail.
