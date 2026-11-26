---
name: hhtiming-help
description: Answer questions about HH Timing software using the offline help.hhtiming.com knowledge base (145 pages: displays, scoreboards, calculations, series/timekeeper setup, Excel exports, licensing, FAQ). Use when the user asks about HH Timing / HH Development / help.hhtiming.com / hh-dev.com — e.g. "HH Timing 怎么用", "Projected lap time 怎么算", "Alkamel 怎么连", "IMSA 设置", "Live excel export", "许可证 license", "Main Scoreboard 列含义", or any how-to about this timing software. Do NOT use for unrelated timing brands or general motorsport questions with no HH Timing context.
---

# HH Timing Help Knowledge Base

Offline Chinese/English knowledge base extracted from https://help.hhtiming.com/ (145/145 sitemap pages).

## Instructions

### Step 1 — Locate the answer (progressive disclosure)

All content is under this skill's `references/` directory. Do **not** re-crawl the site unless the user asks for live/recent pages.

1. Read `references/digests/INDEX.md` for the full page list (title → URL → page file).
2. Prefer **digests** first (analysis + FAQ per section):

| Topic | Digest |
|---|---|
| Install, project, UI, license portal | `references/digests/getting-started.md` |
| Workbooks & layouts | `references/digests/workbooks-layouts.md` |
| All displays / scoreboards / track maps / graphs | `references/digests/displays.md` |
| Session data, live feed, import/export, replays | `references/digests/timing-data-management.md` |
| Backstage / car / championship settings | `references/digests/settings-options.md` |
| Excel live exports | `references/digests/excel-exports.md` |
| Reports | `references/digests/reporting.md` |
| Series-specific (WEC, IMSA, IndyCar, …) | `references/digests/series-specific-info.md` |
| Timekeeper providers (Alkamel, MyLaps, …) | `references/digests/timekeeper-specific-info.md` |
| Formulas (Assumed Pace, stint, projected lap, …) | `references/digests/calculation-definitions.md` |
| Plugins | `references/digests/plugins.md` |
| Tips & tricks | `references/digests/tips-tricks.md` |
| Videos + release notes | `references/digests/videos-and-notes.md` |
| FAQ | `references/digests/faq.md` |
| Support / logs / payment | `references/digests/support.md` |
| What's New timeline | `references/digests/whats-new.md` |
| Site overview | `references/digests/overview.md` |

3. For full original wording, option lists, or step-by-step detail, open the page file under `references/pages/` (slug rule: URL `/a/b/c/` → `a__b__c.md`, home → `index.md`). Map every page via `references/digests/INDEX.md` (each line ends with the page path). Example pages: `references/pages/index.md`, `references/pages/calculation-definitions__projected-lap-time.md`.

### Step 2 — Answer

- Answer in the **user's language** (default zh-CN).
- Cite the source: digest section name and/or `help.hhtiming.com` URL when known.
- Keep English UI terms as-is (Ribbon Bar, Project Tree, Assumed Pace, Live excel export, …) and explain in Chinese.
- For calculation questions, state the **formula/rules and example** from the calculation digest; if missing, open the matching file in `references/pages/` whose name starts with `calculation-definitions__`.
- If the answer is not in the KB, say so clearly; optionally offer to fetch the live page (webfetch) only when the user wants up-to-date docs.

### Step 3 — Cross-checks (common pitfalls)

- License: **12-month lease**, one key for multiple PCs/series; demo mode **30 days** without a key → `faq.md` / `getting-started.md`.
- Assumed Pace = average of best 3 of last 5 green laps (excludes SC/yellow and in/out laps) → feeds fixed/predicted stint and race-finish calcs.
- Two Excel exports differ: parameter-level event-driven **Live excel export** vs scoreboard snapshot every ~10s **Scoreboard live excel export**.
- IMSA requires Al Kamel **V2 North America**; provider varies by series → series + timekeeper digests.
- Backstage settings are machine-local (export `.hhset` to move) → `settings-options.md`.
- Logs path `%localappdata%\HH Timing\Logs`; support email `support@hh-dev.com` → `support.md`.

## Examples

- User: 「Projected lap time 怎么算？」 → calculation-definitions digest + optional page file; give three modes and example numbers.
- User: 「怎么连 MyLaps X2？」 → timekeeper digest section MyLaps X2.
- User: 「Main Scoreboard 的 Proj Gap 是什么？」 → displays digest + calculation digest.
- User: 「HH Timing 多少钱？」 → faq/support: contact pricing; 12-month lease includes updates.

## Troubleshooting

- Digest too thin → open `references/pages/<slug>.md`.
- Unknown slug → search `references/digests/INDEX.md` for the title/URL.
- Question about a brand not in the KB → state coverage list from INDEX; do not invent HH Timing features.
