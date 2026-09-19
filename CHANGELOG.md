# Price refresh log

This page's model pricing table is intended to be refreshed daily by an
unattended cloud agent (a scheduled Claude Code routine) that re-searches
each provider's current per-token rates and updates `index.html`
accordingly. As of 2026-08-16 that routine has not been reliably producing
commits (see the 2026-08-09 entry below) — until it's fixed, updates happen
manually on request instead. There is no live pricing API for any of these
providers, so this is the same kind of
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

## 2026-08-16 (manual update — routine still not producing commits)

Re-ran the routine on demand this session and watched for 10+ minutes; it
fired (per `last_fired_at`) but again pushed nothing, with no error surfaced
via the API. Root cause still unconfirmed — needs a look at the routine's
actual run transcript in the dashboard. Also dropped the "auto-refreshed
daily" claim from the page header and disclaimer since it wasn't true;
replaced with a plain "last updated" date until the automation is fixed.

Roster/price changes this pass:

- **Added Gemini 3.7 Flash**, replacing Gemini 3.6 Flash — released Aug 13,
  2026 at an introductory $0.75/$3.75 (half 3.6 Flash's rate), reverting to
  $1.50/$7.50 on Jan 1, 2027.
- **Added Grok 4.6**, replacing Grok 4.5 — released Aug 12, 2026 at the same
  $2.00/$6.00 headline rate, but cached input rose to $0.50 (was $0.30) and
  a >200K-token tier ($4.00/$12.00) now applies.
- **Added GPT-5.6 Cyber** (off by default) — OpenAI's cybersecurity-focused
  variant, $12.50/$75.00, gated behind a separate approval program and not
  available to typical API customers.
- **DeepSeek V4 Pro / Flash**: no price change, but DeepSeek warned Aug 6,
  2026 of a coming increase with no rate/date disclosed yet — flagged in
  each row's note.
- Checked GLM-5.3 (launched Aug 14) — subscription-only via the GLM Coding
  Plan, no per-token API rate published, so not added as a row.
- Checked Grok Imagine Image 2.0 (Aug 8) — an image-generation model, out of
  scope for this token-based calculator.
- No changes found for Anthropic, Kimi, or Mistral rows this pass.

---

## 2026-09-04 (manual update — routine still not investigated)

- **Claude Sonnet 5**: no price change, but the note was wrong — Anthropic
  made $2/$10 *permanent* on Aug 11, 2026. The previously planned Sept 1
  rise to $3/$15 will not happen.
- **Claude Fable 5 → Fable 5.1**: same $10/$50, but cache reads cut 75% to
  $0.25 (was $1.00).
- **Gemini 3.7 Flash → 3.8 Flash**: identical pricing, new generation.
  Google also launched a gated "3.8 Flash Cyber" variant with no public
  pricing — not added.
- **DeepSeek V4 Flash**: the price increase warned about Aug 6 landed Aug 16
  as time-of-day pricing. This row now uses peak rates ($0.44/$1.32) as the
  conservative default; off-peak is half that. DeepSeek V4 Pro unchanged.
- **Meta Muse Spark 1.2 → 1.3**: same standard price. Added a new
  **Muse Spark 1.3 (Contributor)** row at $0.10/$0.20 — same model, ~12x
  cheaper, in exchange for Meta being able to train on your data.
- **Added GLM-5.3-Flash** (Z.ai) and **replaced Qwen3.5 Flash with
  Qwen3.8 Flash-Next** (Alibaba) — both launched Aug 26, 2026 at roughly
  $0.15/$0.50, a ~10x cut to each provider's budget tier.
- Skipped "Qwen3.8 27B (Consensus Protocol)" — a minor third-party release,
  not a major-lab entry in the spirit of this list.
- No changes found for Opus 5, Haiku 4.5, GPT-5.6 (Sol/Terra/Luna/Cyber),
  Grok 4.6, Kimi, GLM-5.2, Qwen3.8 Max, Llama 3.3 70B, or Mistral rows.

---

## 2026-09-19 (manual update — routine still not investigated)

This pass checked the Anthropic, OpenAI, Google, and DeepSeek rows against
those providers' **own pricing pages** rather than aggregators, and found
several rows that had gone stale:

- **GPT-5.6 Sol**: $5/$30 → **$4/$20** (cached $0.40). OpenAI's page calls it
  promotional pricing "available at least through November 21, 2026", so it
  may revert. Added the >272K long-context tier ($8/$30).
- **DeepSeek V4 Pro**: $0.435/$0.87 → **$1.32/$3.96 peak** ($0.66/$1.98
  off-peak) — roughly triple what the page showed. Peak is 01:00–04:00 and
  06:00–10:00 UTC, Mon–Fri excluding Chinese public holidays; the row uses
  peak as the conservative default.
- **DeepSeek V4 Flash → V4.1 Flash**: DeepSeek retired V4 Flash. V4.1 Flash is
  cheaper than V4 Flash was: $0.30/$1.20 peak ($0.15/$0.60 off-peak).
- **Added GPT-6 Astra** (OpenAI, launched Sep 3): $10/$50, cached $1.00,
  >272K tier $20/$75.
- **GPT-5.6 Terra / Luna**: added the >272K tiers and replaced the "assumed"
  cache prices with the confirmed ones (unchanged values).
- **GPT-5.6 Cyber**: removed the long-context tier I had guessed — OpenAI
  lists it as short-context only.
- **Gemini 3.5 Flash-Lite**: cached input is published after all ($0.03);
  Gemini 3.1 Pro's cache price is now confirmed rather than estimated.
- **Claude Opus 5**: corrected the note — Anthropic lists Opus 5 and Opus 4.8
  as separate models, not one model under two names.
- **Claude Sonnet 5 now has two rows: high effort and medium effort** (see
  below).
- Checked, no change: Fable 5.1, Haiku 4.5, Gemini 3.8 Flash, Grok 4.6 (Grok
  4.7 is promised but unreleased), Kimi K3 (no K3.1 exists). Skipped Sakana's
  Fugu Ultra v2 / Fugu Max (a multi-agent orchestration product, not a base
  model) and Qwen3.8 27B (conflicting attribution/pricing).

**New: "Out tokens ×" column and Sonnet 5 effort rows.** Effort never changes
Anthropic's per-token price — it changes how many output and thinking tokens
the model spends. The calculator now has a per-row multiplier on output and
thinking tokens. High effort is Sonnet 5's default, so it is the 1.00×
baseline; medium is **0.57×**, taken from Artificial Analysis's Intelligence
Index (51M output tokens at medium vs. 89M at high; scores 28 vs. 32). That
ratio is one benchmark's measurement, not an Anthropic figure — the multiplier
is editable so it can be replaced with your own.

**Fixed: returning visitors never saw roster updates.** Saved state
(localStorage, imports, share links) replaced the entire model list, so anyone
who had used the page before kept seeing their old roster — new models and
price changes never appeared. Saved state and share links now carry a
fingerprint of the built-in roster; when it changes, built-in rows are reset
to the new data while workload inputs and custom models are kept, and a
message explains it.

---
