# Price refresh log

This page's model pricing table is refreshed daily by an unattended cloud
agent (a scheduled Claude Code routine) that re-searches each provider's
current per-token rates and updates `index.html` accordingly. There is no
live pricing API for any of these providers, so this is the same kind of
manual-research process a person would do — just automated and unreviewed.
**Treat it as a starting point, not a source of truth** — always confirm
against a model's own row-level source link, or the provider's official
pricing page, before using a number for a real budget.

Each entry below is added by the daily run and should note: the date, which
rows changed, why (a price change, a new model, a correction), and any
sources that disagreed.

---

## 2026-08-09 (manual update, not the daily routine)

The daily routine has fired every day since it was created on 2026-07-31 per
its `last_fired_at` timestamp, but produced zero commits to this repo in
that span — its automation appears broken and needs investigation. In the
meantime, this update was done by hand at the user's request:

- **Added Qwen3.8 Max** (Alibaba), replacing Qwen3 Max in the active roster —
  released Aug 2, 2026 at $2.00/$6.00 (was $0.78/$3.90), a 2.4T-parameter
  successor priced to match frontier US models rather than undercut them.
- **GPT-5.6 Terra**: $2.50/$15.00 → $2.00/$12.00 (OpenAI cut it 20% on
  Jul 30, 2026).
- **GPT-5.6 Luna**: $1.00/$6.00 → $0.20/$1.20 (OpenAI cut it 80% on
  Jul 30, 2026, its steepest cut). Cached-input on both Terra and Luna is
  an assumed 10%-of-input ratio, not separately confirmed at the new rates.
- **GPT-5.6 Sol**: unchanged, source/verified-date refreshed to OpenAI's own
  announcement post instead of a third-party aggregator.
- **Added Muse Spark 1.2** (Meta) — Meta's first-party proprietary
  reasoning/agentic API, released ~Aug 5, 2026 at $1.25/$4.25, distinct from
  the open-weight Llama models above (which stay, hosted by Together AI).
- No changes found for Anthropic, Google, xAI, DeepSeek, Kimi, GLM, or
  Mistral rows this pass.

---
