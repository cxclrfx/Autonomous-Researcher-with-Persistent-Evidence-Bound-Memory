# Prototype evidence v1

## Scope and observation date

Local read-only inspection on 2026-09-09; extraction completed at 2026-09-09T20:41:06.676813Z.
These sanitized observations derive from existing local runtime records of an operating private prototype. No new autonomous experiment, shutdown, restart, or private implementation execution was performed for this package. This is a fixed sample of a changing runtime, not a statement of its future state.

## VERIFIED OBSERVATION

Here, VERIFIED OBSERVATION means that the inspector read the local records and checked the stated metadata relationship. The records are producer-generated. Readers receive sanitized derivatives, not independent access to the private sources.

- The captured inventory contained 1165 JSON state checkpoints, from 2026-09-07T03:54:46.204493Z to 2026-09-09T20:40:10.463510Z.
- Across that inventory, the stored completed-batch counter increased from 0 to 1083, with 0 decreases in embedded-timestamp order. The stored memory-event counter at the endpoints increased from 1533 to 3703. This demonstrates recorded counter growth, not the number of correct conclusions, unique memories, or useful discoveries.
- The five consecutive checkpoints in [checkpoint_sequence.txt](samples/checkpoint_sequence.txt) record RUNNING state and continuous autonomous mode, with completed-batch values 1079 through 1083 and session-batch values 38 through 42. This supports persisted progress across successive recorded cycles. Counters and mode labels alone cannot prove absence of human intervention.
- All 1165 checkpoint envelope digests were recomputed locally using the inspected serialization convention; 0 mismatches were found. This checks envelope integrity only. It does not independently validate the referenced memory, queues, source corpus, lineage, or semantic correctness. Private envelope digests and source identifiers are omitted.
- The endpoint and sampled records contain producer-reported integrity PASS, source-hash-verification PASS, and SQLite status ok. Those checks were not independently rerun against the private corpus for this publication review.
- 83 checkpoints contain a checkpoint-error field. Error text is withheld because it may contain private paths. Those records remain in the inventory; a stored integrity PASS must not override a recorded error. The count is of records carrying the field, not distinct incidents. The five displayed final checkpoints do not carry that field.
- [restart_resume_record.json](samples/restart_resume_record.json) shows operation records under four distinct run identifiers, anonymized here. RESTORE and later batch/memory-write operation records are present. The logger emits records even when an operation raises an exception; operation counts are not success counts. Successful stop/restart/resume, exact restored-state identity, and power-cycle recovery are NOT_ESTABLISHED by this package.
- Checkpoints and operation records were read from local storage. Read-only inspection of the current runner found loopback model requests and an external-network restriction. No packet capture, network-disconnected test, historical-code binding, GPU measurement, or audit of all components was performed. Fully offline end-to-end execution is not independently established here.

The broad timestamp span does not establish one uninterrupted multi-hour run. The evidence establishes persisted records and counter continuity; it does not establish complete memory-content continuity after a restart.

## DESIGN CLAIM

The system is intended to accumulate source-bound research state, preserve historical and conflicting interpretations, recover after restart, and operate with local inference. These design statements, and the broader behavior descriptions in the README, extend beyond what this sanitized package independently verifies. The synthetic demo illustrates desired evidence-state behavior; it is not output from the private implementation.

## Redaction and reproducibility boundary

Only selected timestamps, counters, generic states, integrity labels, error-presence flags, and locally recomputed hash-match results were retained. Private filenames, absolute paths, source/corpus identifiers, raw source hashes, run identifiers, process identifiers, prompts, owner messages, scientific material, research conclusions, memory contents, queue contents, implementation code, and raw error messages were intentionally excluded. No private source corpus is included.

The public manifest hashes the sanitized files so a reader can check their byte integrity. These hashes do not authenticate the hidden sources or prove correctness. Readers can inspect the public counter relationships and the fully synthetic fixture; full reproduction of the private run is unavailable. No independent adversarial closure or fresh holdout result is claimed.

See [runtime_summary.json](samples/runtime_summary.json) for the fixed inventory summary and [EVIDENCE_MANIFEST.json](EVIDENCE_MANIFEST.json) for artifact hashes.
