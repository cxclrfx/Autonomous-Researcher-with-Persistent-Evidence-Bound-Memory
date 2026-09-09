# Private Project Brain — Autonomous Researcher

> A fully local, offline autonomous research system with persistent evidence-bound memory.

## Overview

Private Project Brain — Autonomous Researcher is an experimental local AI system designed to do more than answer one prompt at a time.

It can work independently over a large local research corpus for extended periods, preserve what it learns, stop safely, resume later, and continue from the same persistent state without requiring Internet access.

The system is built around a simple idea:

**research should accumulate into durable understanding, not disappear when a chat window closes.**

This repository describes the public behavior and operating principles of the system.  
The underlying scientific framework, internal methodology, private research corpus, and implementation-specific mechanisms are intentionally not disclosed here.

---

## What it does

The Autonomous Researcher can:

- study a large local collection of documents, code, reports, experiments, logs, notes, and historical material;
- continue working autonomously across many bounded research cycles;
- build and maintain its own persistent structured understanding of the corpus;
- preserve links between conclusions and their source evidence;
- keep historical, current, superseded, uncertain, and conflicting interpretations distinct;
- record checkpoints during long-running work;
- resume after restart from the last valid persistent state;
- continue without Internet access when all required local components are present;
- leave original source material unchanged;
- keep its own working memory and research state separate from the source corpus;
- pause when the owner intervenes and continue later;
- request explicit permission when external information would materially help.

It is designed for long-lived research work rather than disposable chat sessions.

---

## The central difference

Most AI assistants are optimized around a conversation:

```text
prompt
  -> model
  -> answer
  -> next prompt
```

This system is organized around continuing research:

```text
local evidence
  -> autonomous investigation
  -> persistent structured memory
  -> source-linked conclusions
  -> checkpoint
  -> next research cycle
```

A restart does not imply starting over.

The active language model is only one component of the system.  
The research state is stored outside the transient model context and is designed to survive process restarts and long periods of inactivity.

---

## Persistent understanding, not just chat history

The system does not treat long-term memory as a transcript archive.

Its persistent state can distinguish between:

- observed source evidence;
- derived conclusions;
- current working state;
- historical state;
- superseded conclusions;
- unresolved questions;
- conflicting evidence;
- uncertainty;
- decisions and constraints;
- source provenance.

A later discovery does not need to erase an earlier conclusion.  
The system can preserve both the earlier interpretation and the evidence that caused it to change.

This makes the research history inspectable instead of silently rewriting the past.

---

## Domain-specialized assistants

The system can be prepared from the outset for a specific domain, with an authorized domain corpus, specialized tools and local utilities, domain terminology and operating rules, persistent project state, source and provenance requirements, and task-specific workflows.

For example, a deployment could focus on airdrop analysis or large-scale document comparison, then continue learning from new authorized local material while preserving source links and research state.

This does not necessarily require retraining or fine-tuning model weights. Specialization can be provided by the surrounding local system, its knowledge, tools, persistent state, and operating configuration.

---

## Evidence-bound research

Important conclusions remain connected to local evidence.

The system is designed so that exact source material can be resolved from its original local evidence rather than reconstructed from model memory.

This separation matters:

**model interpretation is not treated as source truth.**

Previous model answers, old reports, old PASS/FAIL labels, summaries, and historical conclusions may all be useful evidence, but none become authoritative merely because they were written earlier.

---

## Autonomous mode

The researcher can be given a broad task such as:

```text
Study the authorized local corpus.
Do not modify the originals.
Build your own understanding.
Preserve important findings in your own memory.
Continue while useful unexplored work remains.
```

From there, it can continue through many bounded research cycles on its own.

A long-running session is not one enormous prompt.  
Work is divided into recoverable units, with persistent state saved between them.

When useful work is exhausted, the system can stop and wait for the owner instead of repeatedly processing the same material.

---

## Offline by design

The primary research workflow can operate with:

- a local model;
- local source files;
- local persistent memory;
- local indexes;
- local checkpoints;
- local tools.

No Internet connection is required for ordinary research.

If an external fact becomes important, the system is expected to request permission rather than silently reaching outside the machine.

External access is therefore a controlled exception, not a dependency.

---

## Source preservation

The original research corpus is treated as evidence, not as a disposable workspace.

The researcher works in its own writable area and is designed to avoid modifying the source corpus automatically.

This allows:

- reproducible review;
- comparison between old and new conclusions;
- recovery from mistakes;
- separation between evidence and interpretation.

The system may create its own notes, indexes, memory structures, checkpoints, and derived views without rewriting the original material.

---

## Recovery and continuity

Persistent state is designed to survive ordinary shutdowns and restarts.

A typical lifecycle is:

```text
work
 -> save persistent state
 -> checkpoint
 -> stop
 -> machine powers off
 -> later restart
 -> restore
 -> continue
```

The goal is not to preserve volatile RAM state byte-for-byte.

The goal is to preserve enough durable research state that the system can continue the same investigation rather than reconstructing its identity and progress from scratch.

---

## Owner control

Autonomy does not mean unrestricted authority.

The owner remains above the autonomous worker.

The system is designed around explicit boundaries for:

- stopping autonomous work;
- resuming it;
- recording owner decisions;
- distinguishing owner-supplied facts from independently verified evidence;
- requesting external access;
- preventing automatic promotion of derived findings into original source material.

The researcher may work independently inside its authorized space, but it does not silently redefine the owner's source of truth.

---

## What this is not

This project does **not** claim:

- consciousness;
- sentience;
- artificial general intelligence;
- proof of human-like reasoning;
- perfect factual accuracy;
- autonomous authority over external systems;
- that persistent memory alone constitutes intelligence.

It is an engineering and research system for **long-duration, local, evidence-aware autonomous investigation**.

---

## Why this matters

Large research projects often fail at continuity.

Important context becomes scattered across:

- documents;
- chat histories;
- experiments;
- abandoned branches;
- old conclusions;
- later corrections;
- code;
- logs;
- human memory.

A conventional assistant can help with one piece at a time, but the researcher itself usually has to reconstruct the larger state repeatedly.

The goal of this project is different:

> **make the machine carry forward the research state itself.**

Not merely the text of previous conversations, but the evolving structure of what is known, what changed, what conflicts, what remains uncertain, and where the supporting evidence lives.

---

## Current prototype

The following capabilities were reported for the private prototype. They are not all independently established by the sanitized evidence package; see its VERIFIED OBSERVATION and DESIGN CLAIM sections for the checked scope:

- multi-hour autonomous research sessions;
- repeated persistent checkpoints;
- continued memory growth across many autonomous cycles;
- recovery after process restarts;
- local GPU inference;
- fully local research operation;
- source-linked memory records;
- integrity verification of persistent state;
- controlled interruption by the owner;
- continued work after explicit resume.

The private research corpus and the scientific mechanisms used to construct the system are not included in this public repository.

---

## Public repository scope

The public version is intended to contain only material necessary to explain and demonstrate the system safely.

It will not include:

- the private research corpus;
- private conversation history;
- unpublished scientific work;
- proprietary internal methodology;
- private memory databases;
- model weights;
- credentials or secrets;
- private project artifacts.

Any public demonstration should use a synthetic or openly redistributable corpus.

---

## Status

**Experimental / active research**

The system is already functional as a local autonomous research worker, but its architecture and operating policies continue to evolve through real use.

The project is published to document the direction, behavior, and reproducible public surface — not to disclose the private scientific framework behind it.

---

## Short version

**Private Project Brain — Autonomous Researcher** is a local AI system that can independently study a large body of material, build persistent source-linked understanding, survive restarts, preserve conflicting and historical conclusions, and continue working without Internet access or modifying the original evidence.

It is designed to remember the research — not merely the conversation.


## Evidence

This repository contains sanitized evidence from an operating private prototype and a fully synthetic demonstration corpus. The evidence separates verified observations of local runtime records from design claims and producer-reported checks. The demo is a conceptual/test fixture, not a runnable distribution of the private implementation.

- [Prototype evidence](evidence/PROTOTYPE_EVIDENCE.md)
- [Evidence manifest](evidence/EVIDENCE_MANIFEST.json)
- [Synthetic demonstration](demo/README.md)

The underlying scientific framework, internal methodology, and private corpus are not disclosed.
