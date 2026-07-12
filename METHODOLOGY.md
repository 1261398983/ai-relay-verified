# Scoring methodology (reproducible)

The whole point of this directory is that **you can re-run every score yourself**.
No black box, no "trust our number." Here's exactly how an entry is scored.

## Inputs
A relay's `base_url` + a key you control + the `model` id you're paying for.

## Step 1 — Liveness & compatibility (pass/fail)
Run [relay-doctor](https://github.com/cocodot2026/relay-doctor):
```bash
python relaydoc.py --base-url https://<relay>/v1 --api-key <key> --model <id>
```
Record: reachable, model count, chat works, streaming works, latency, TTFT. A relay
that can't serve a completion doesn't get a downgrade score — it's simply `broken`.

## Step 2 — No-downgrade score (0–100)
Run an **independent verifier** and record the score + which tool produced it. We
deliberately accept more than one tool, because a verification you can only get from
a single vendor's tool isn't independent:

- [cocodot-llmprobe](https://github.com/cocodot2026/cocodot-llmprobe) — 6 probes (identity,
  capability via LLM-judge, latency, context, rate-limit, consistency), 0–100.
- [LLMprobe-engine](https://github.com/Bazaarlinkorg/LLMprobe-engine) — 36 probes /
  8 dimensions, behavior-vector classifier.
- [llm-probe](https://github.com/telagod/llm-probe) — trust score across protocol /
  injection / authenticity.

A submitted score **must state which tool, which model id, and the date**, and
ideally link a run log. Different tools use different scales — we record the tool
alongside the number rather than pretending they're interchangeable.

## Step 3 — Label the source honestly
Every score carries a source tag:
- `independent` — run by someone with no stake in the relay
- `vendor self-report ⚠️` — run by the relay operator (still useful, but reproduce it)
- `community` — submitted by a user, evidence attached

## What the columns mean
- **Verifiable?** — does the relay *let* you test freely (open endpoint, no blocking
  the probes)? A relay that discourages testing scores `no` here regardless of any
  number — that itself is the signal.
- **Score** — the 0–100 from Step 2, with its source tag.
- **Evidence** — link to a run log / gist / screenshot.

## Re-verification
Scores go stale (relays change upstreams, throttle at peak). Entries older than ~90
days are marked stale; anyone can submit a fresh run. Peak-hour vs off-hour runs are
both welcome — divergence is itself informative.

## Bias controls
- The maintainer operates a relay (cocodot). Its entry is tagged `vendor self-report`
  and is **not** placed above better-verified peers.
- We link competing verifiers, not just our own, so no single tool gates the scores.
- PRs that add a relay without reproducible evidence are marked `⏳ awaiting`, not scored.
