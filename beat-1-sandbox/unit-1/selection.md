# Unit 1 — Issue Selection

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/68

**Verdict output**

### Issue #68: Keyword Search ZeroDivisionError on Empty Index

**Check: Human maintenance**
- Grade: **PASS**
- Evidence: Last commit 2026-09-16 by Andrew Burke (11 days ago, within 90 days)

**Check: Active project**
- Grade: **PASS**
- Evidence: Repository not archived, last push 2026-09-16 (11 days ago, within 90 days)

**Check: Bounded contribution**
- Grade: **PASS**
- Evidence: One identifiable code change - adding empty-check guard in `index()` method; specific file and test identified; estimated 2-4 hours

**Check: Available work**
- Grade: **PASS** (with Path Review house rule applied)
- Evidence: Issue open, no assignee, PR #74 is open (not merged). Multiple claim comments (acordero4852, SingLZ, b-tanyileke) present, but Path Review house rule applies

**Check: AI workflow permitted**
- Grade: **PASS**
- Evidence: CONTRIBUTING.md has no AI ban; requires testing and CI compliance which are conditions, not bans

**Check: Easy verification (preferred)**
- Grade: **PASS**
- Evidence: Clear reproducer showing ZeroDivisionError; specific test `test_empty_index` with xfail marker to remove; error traceback location provided

```json
{
  "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/68",
  "checks": [
    {"name": "Human maintenance", "grade": "pass", "evidence": "Last commit 2026-09-16 by Andrew Burke (11 days ago, within 90 days)"},
    {"name": "Active project", "grade": "pass", "evidence": "Repository not archived, last push 2026-09-16 (11 days ago, within 90 days)"},
    {"name": "Bounded contribution", "grade": "pass", "evidence": "One identifiable code change - adding empty-check guard in index() method; 2-4 hour estimate"},
    {"name": "Available work", "grade": "pass", "evidence": "Issue open, no assignee, PR #74 open but not merged; Path Review house rule applies to multiple claims"},
    {"name": "AI workflow permitted", "grade": "pass", "evidence": "CONTRIBUTING.md has no AI ban; requires testing and CI compliance (conditions, not bans)"},
    {"name": "Easy verification", "grade": "pass", "evidence": "Clear reproducer showing ZeroDivisionError; specific test test_empty_index with xfail marker to remove"}
  ],
  "verdict": "accept"
}
```

## Eval iterations

**Run history**

- Full run 1: `18/20` scored items — PASS. This is the run saved in `eval-run.txt`.

**Issue analysis**

`issue-09`: my rubric decided **reject**, while the gold label was **accept**. The run marked Bounded contribution as failed because the issue was eight years old with one closed PR, even though my written check only rejects an old issue after at least two closed unmerged attempts. It also marked Available work unclear because a 2022 claim had no explicit withdrawal and the closed PR's merge status was unknown. Since required unclear evidence rejects under my verdict rule, that conservative availability result also produced the rejection.

**Check rationale**

> Easy verification — Evidence: Reproduction steps, expected/actual behavior, examples, test references, and maintainer guidance in the body and comments. Pass condition: "The report provides a concrete reproducer, a specific existing test to extend, or an explicit before/after example that can verify the change." Weight: preferred.

I kept this check preferred because concrete verification makes an accepted issue faster and safer to start, but an otherwise bounded contribution should not be rejected only because its report is brief or lacks polished reproduction steps.

**Trade-offs**

Making Easy verification preferred means an accepted issue can still require extra investigation before I can prove the bug. The trade-off is intentional: report quality helps rank accepted issues, while the required scope and availability checks decide whether the work is viable at all.

## Selection rationale

1. I chose #68 because it is a small Python edge-case bug with a concrete failure, one focused existing test, and an estimated two-to-four-hour scope that fits the time available.
2. The verdict correctly identified the active repository, bounded code path, and easy verification. The rubric could not tell me exactly how long local dependency setup would take, so I also weighed the short reproducer and isolated test file.
3. Claiming it was straightforward under the Path Review classroom rule: other student claims do not block mine, but I still needed to post my own specific claim and later provide my own reproduction evidence.

