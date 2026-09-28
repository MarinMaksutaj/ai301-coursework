# Unit 2 — Claim and Reproduce

## Your identity upstream

**GitHub username**

MarinMaksutaj

## Posted upstream

**Claim comment**

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/68#issuecomment-5863525042

I'd like to investigate #68, where `KeywordSearcher.index([])` raises `ZeroDivisionError` instead of handling an empty corpus. I'll run the empty-index case on a recorded revision, check the existing `test_empty_index` test, and follow up with my environment, steps, and observed output.

**Reproduction comment**

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/68#issuecomment-5863729777

Reproduction report for #68

Environment:

- Repository revision: `2f4e82f52efbcfcc57d65b3fa5348672163ca088`
- macOS 26.6 on arm64
- Python 3.11.5 in a virtual environment
- `rank-bm25` 0.2.2
- Installed with `.venv/bin/pip install -e '.[dev]'`

Steps:

```bash
git clone https://github.com/codepath/pathreview-ai301-fa26-s3.git
cd pathreview-ai301-fa26-s3
git checkout 2f4e82f52efbcfcc57d65b3fa5348672163ca088
python3 -m venv .venv
.venv/bin/pip install -e '.[dev]'
.venv/bin/python - <<'PY'
from rag.retriever.keyword_search import KeywordSearcher

searcher = KeywordSearcher()
print("calling KeywordSearcher.index([])")
searcher.index([])
print("index completed")
PY
```

Observed output:

```text
calling KeywordSearcher.index([])
Traceback (most recent call last):
  File "<stdin>", line 5, in <module>
  File ".../rag/retriever/keyword_search.py", line 25, in index
    self.bm25 = BM25Okapi(tokenized_corpus)
  File ".../rank_bm25.py", line 52, in _initialize
    self.avgdl = num_doc / self.corpus_size
ZeroDivisionError: division by zero
```

I also ran the focused test:

```bash
.venv/bin/pytest tests/unit/test_keyword_search.py::TestKeywordSearcher::test_empty_index -q -rxX
```

It was reported as the expected failure:

```text
XFAIL tests/unit/test_keyword_search.py::TestKeywordSearcher::test_empty_index - issue #68 (manifest H-01): BM25 keyword search raises ZeroDivisionError on an empty index
1 xfailed in 0.77s
```

Expected: indexing an empty corpus does not raise, and a subsequent search returns `[]`.

Actual: `KeywordSearcher.index([])` reaches `BM25Okapi` with an empty corpus and raises `ZeroDivisionError` before a search can run. This reproduces the behavior described in #68 on the revision and environment above.

## Eval iterations

**Run history**

- Full run 1: `19/20` scored packages — PASS. This is the run saved in `eval-run.txt`.

**Package analysis**

`pkg-16`: my rubric decided **accept**, while the gold label was **reject**. The candidate's command and `ValueError` matched the reported tuple-name symptom, so Target-matched evidence passed. However, the candidate tested pandas 1.5.3 rather than the latest release or main branch requested by the repository, omitted the requested `pd.show_versions()` output, and did not acknowledge the version mismatch. The grader passed Recorded environment after finding concrete version strings and passed Repo conventions despite those missing requirements. This shows that the run under-applied the written rules: concrete environment details are insufficient when they do not cover the project's required target.

**Check rationale**

> Target-matched evidence — Evidence: Report's actual output/logs/screenshots or explicit observed UI state compared with the issue's trigger, expected behavior, and failure signature; evidence guide Behavior shown. Pass condition: "The report contains concrete observed evidence from exercising the issue's relevant trigger. A reproduced outcome shows the reported symptom, not an adjacent parse/setup/network error that prevents reaching it. A cannot-reproduce outcome passes when the same relevant trigger was attempted and evidence shows the observed nonfailure. Mere assertions such as \"same error\" or an unrelated failure are insufficient." Weight: required.

I wrote this check around the observed outcome because an error message alone is not proof. The trigger must reach the same behavior described by the issue. The cannot-reproduce clause also allows an honest negative result when the relevant attempt and actual nonfailure are shown.

**Trade-offs**

This check rejects reports whose setup fails before reaching the target, even if that adjacent failure is useful information. That is intentional for a reproduction package: the contributor can report the setup problem separately, but should not call it proof of the original bug. The first full run passed at 19/20, so I kept its transcript unchanged and documented the pkg-16 false acceptance rather than spending another full-run credit.
