# Contributing

This directory is only useful if it stays **neutral and evidence-based**. Two ways
to help:

## A. Add a relay (registry row)
Open a PR adding one row to the table in `README.md` and one object to
`data/relays.json`. Fill only what you can verify; leave `score` as `⏳ awaiting` if
you haven't run a test. Untested is fine — it's honest.

## B. Submit or update a score
Run an independent verifier (see [METHODOLOGY.md](METHODOLOGY.md)) and PR the result.
Your PR **must** include:
- the tool used (LLMprobe / LLMprobe-engine / llm-probe / other) and its version
- the exact `model` id tested and the date
- evidence: a run log, gist, or screenshot link
- a source tag: `independent`, `community`, or `vendor self-report`

## Rules (keep the list high-signal)
1. **One relay per PR.**
2. **Real evidence.** No evidence → `⏳ awaiting`, not a number.
3. **Disclose affiliation.** If you operate the relay, tag the score
   `vendor self-report`. You'll still be listed — transparency is the deal.
4. **No affiliate/referral links.**
5. **Be honest about weaknesses** (blocking, throttling, limited models, payment gaps).
6. **Competitors and critics welcome on equal terms.** Adding a rival relay with a
   strong verified score is exactly what this directory is for.

## What gets rejected / removed
- Scores with no reproducible evidence.
- Marketing copy in place of data.
- Entries whose relay is found to block the verification probes while claiming a
  score (that contradiction gets a `Verifiable? = no` flag, not a number).

## Disclosure
Maintained by the team behind [cocodot](https://cocodot.co). If you think an entry
(including cocodot's) is unfair or stale, open an issue — that's the correction
mechanism working as intended.
