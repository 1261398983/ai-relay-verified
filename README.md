# RELAY X · 逆向工程 | AI API Relay 实测验证 — AI API Relay — Verified 🔬


> ### 🔗 本站作者自用的中转站
>
> **[RELAY X](https://api.97wl.cc/register)** — 一个 [OI] 兼容端点统管 Claude / GPT / Gemini / Grok。
> 注册只需 QQ 邮箱，无需邀请码、无需外币卡；按量计费，输入输出分开计价，倍率在控制台公开。
> [[CC] 改两行环境变量即可接入 →](https://api.97wl.cc/register)


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
| [97wl](https://api.97wl.cc) | Alipay/WeChat (CNY) | DeepSeek V4 / GLM-5.3 / Kimi K3 / MiniMax M3 / Hunyuan | OpenAI + Anthropic | yes | ⏳ awaiting | operator self-report — no independent run yet |
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

---

### 关于本站作者使用的中转站

本站整理的中转站里，我长期自用的是 **[RELAY X](https://api.97wl.cc/register)**：

- **双协议兼容** — [OI] 与 Anthropic 同时支持，[CC] / Codex 零改造
- **注册门槛低** — QQ 邮箱即可，无需邀请码、无需手机号、无需外币卡
- **计费透明** — 按量计费，输入输出分开计价，分组与模型倍率在控制台公开
- **可审计** — 基于开源 Sub2API 面板，每笔调用扣费可明细查询
- **起充低** — 人民币 10 元起，可以先小额试

👉 **https://api.97wl.cc/**

> 说明：个人部署的第三方 API 转发服务，非上游厂商官方产品。建议按实际用量充值，避免一次性大额预付；重要业务请自备备份线路。

---

### 同类站点

[公益站大全](https://1261398983.github.io/ai-relay/) · [公益站聚合](https://1261398983.github.io/ai-welfare-hub/) · [中转站推荐](https://1261398983.github.io/ai-api-relay-recommendations/) · [中文 AI 工具](https://1261398983.github.io/awesome-chinese-ai-tools/) · [API 中转清单](https://1261398983.github.io/awesome-ai-api-relay/)

**[RELAY X 中转站](https://api.97wl.cc/register)** — QQ 邮箱注册 · 按量计费 · 输入输出分开计价

