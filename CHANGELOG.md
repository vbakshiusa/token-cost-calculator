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
