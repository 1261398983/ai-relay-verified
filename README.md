# AI API Relay — Verified 🔬

**Which AI API relays actually serve the model you pay for? A directory that ranks
relays on one thing everyone else ignores: whether you can *verify* they're not
silently downgrading the model — with a reproducible, open method.**

> 国内外 AI 中转/relay 目录,但**只评一件事:能不能验证它不降智**。
> 现有榜单都只"列",不"评"。这张榜列 + 评 + 给你可复现的方法自己测。

Most relay lists just take the vendor's "官转不降智" word for it. This one doesn't.
Every entry is scored on **verifiability**, and every score is backed by a
reproducible test you can re-run yourself.

## Why this exists

Relays control what actually runs behind your request — they can bill you for Opus
and serve a small model, and the response looks identical. This isn't hypothetical:
an independent 14-day study of **171 relay endpoints** (Bazaarlink's *LLMprobe-engine*
research) found model-impersonation in **~1.3% under strict and ~9.9% under relaxed
criteria** — roughly **1 in 10** relays misrepresents what it serves. So "trust me,
官转" is not good enough. **Verify.**

## The leaderboard

Scores are 0–100 on the [reproducible method](METHODOLOGY.md). `⏳ awaiting` = nobody
has submitted an independent test yet — **untested, not untrustworthy.** Vendor
self-reports are labeled as such; reproduce them before trusting.

| Relay | Pay | Models | Compat | Verifiable? | Score | Evidence |
|---|---|---|---|---|---|---|
| [OpenRouter](https://openrouter.ai) | card / crypto | 300+ | OpenAI | yes | ⏳ awaiting | — |
| [cocodot](https://cocodot.co) | Alipay/CNY | Claude/GPT/Gemini/DeepSeek | OpenAI + Anthropic | yes | **87** · vendor self-report ⚠️ | [method](METHODOLOGY.md) |
| [DSH API](https://api.dshapi.icu) | Alipay/WeChat (CNY) | DeepSeek V4 / GLM-5.3 / Kimi K3 / MiniMax M3 / Hunyuan | OpenAI + Anthropic | yes | ⏳ awaiting | operator self-report — no independent run yet |
| _your relay_ | … | … | … | … | submit a result → | [how](CONTRIBUTING.md) |

⚠️ **cocodot is maintained by this repo's author** (disclosed). Its score is a
*vendor self-report* run with the open method below — **don't take it on trust,
reproduce it.** cocodot is listed on the same terms as everyone else and is not
ranked above unverified peers.

## How a relay gets scored

Two open tools, both re-runnable by anyone (see [METHODOLOGY.md](METHODOLOGY.md)):

1. **Liveness & compat** — [relay-doctor](https://github.com/cocodot2026/relay-doctor):
   reachable? which models? latency? streaming?
2. **No-downgrade** — a 0–100 score from independent verifiers. Use whichever you
   trust; we list more than one on purpose:
   - [cocodot-llmprobe](https://github.com/cocodot2026/cocodot-llmprobe) (this toolkit)
   - [LLMprobe-engine](https://github.com/Bazaarlinkorg/LLMprobe-engine) (independent)
   - [llm-probe](https://github.com/telagod/llm-probe) (independent)

Using multiple independent tools is the point — a score you can only get from one
vendor's tool isn't a verification.

## Add or verify a relay

Anyone can. Add a row, or submit a score with evidence — see
[CONTRIBUTING.md](CONTRIBUTING.md). Rules: **one relay per PR, real evidence,
disclose affiliation, no affiliate links, be honest about weaknesses.** We list
competitors and critics on equal terms.

## Disclosure

Maintained by the team behind [cocodot](https://cocodot.co), a relay. cocodot
appears as one *disclosed, self-reported* entry — reproduce its score like any
other. This directory only earns its keep by being **neutral**: if it ever ranks
cocodot above better-verified peers, it's broken — open an issue.

MIT (code) · CC0 (the registry data).
