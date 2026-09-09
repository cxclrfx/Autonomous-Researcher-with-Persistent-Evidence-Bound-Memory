# Synthetic evidence-state fixture

All names, dates, statements, and documents in this directory were invented specifically for this demonstration. They are unrelated to the private research corpus.

This is a reproducible conceptual/test fixture: synthetic inputs plus a manually authored expected evidence-state example. It contains no private implementation and no generated output from that implementation. Outsiders cannot run the private researcher from this repository.

## Inspect the fixture

1. Read `corpus/01_initial_notice.txt`: opening at 09:00 is the initial assertion.
2. Read `corpus/02_corrected_notice.txt`: an explicit correction targets the earlier notice in the same scope. Retain 09:00 as superseded and bind 10:00 to the correcting source.
3. Read `corpus/03_event_listing.txt` and `corpus/04_event_card.txt`: retain the incompatible event times as a conflict. Neither source has declared precedence; ingestion order must not select a winner.
4. Keep the access question unresolved. Missing confirmation does not mean no access.
5. Compare these relationships with [expected_evidence_state.json](expected_evidence_state.json). Each assertion/question binds to a file, its SHA-256, a one-based line, and an exact quote. File hashes establish byte identity, not source authority or truth.

The intermediate views in `ingestion_trace` distinguish the initial conclusion from its later supersession. CURRENT_WITHIN_FIXTURE is a fixture status, not an independently verified real-world fact. Alternative implementations may use different schemas but should preserve these relationships. The schema here is illustrative and does not disclose the private system's memory representation.

## Reproduce source-binding checks

With Python 3, run the following from the repository root. This checks only the supplied fixture's file hashes and quotations. It is not a test of the autonomous researcher, its reasoning, persistence, or restart behavior.

```python
from pathlib import Path
import hashlib
import json

root = Path("demo")
fixture = json.loads((root / "expected_evidence_state.json").read_text(encoding="utf-8"))
for state in fixture["states"]:
    source = state["source"]
    data = (root / source["file"]).read_bytes()
    assert hashlib.sha256(data).hexdigest() == source["sha256"]
    assert data.decode("utf-8").splitlines()[source["line"] - 1] == source["quote"]
print("Synthetic fixture source bindings verified; private implementation not run.")
```

A wrong source hash or quote must fail this check. Reversing the two event-source ingestion orders must not resolve their conflict. A later date without an explicit correction must not by itself supersede an assertion. These are expected fixture semantics, not reported private-runtime test results.
