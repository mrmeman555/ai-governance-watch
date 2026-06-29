# Automated updates

This repo can update itself on a schedule via **Claude Code** running in GitHub Actions —
it researches new AI-governance developments and **opens a pull request** with draft updates.
**Nothing is ever auto-merged; you review every PR.**

## How it works
- **Workflow:** [`.github/workflows/ai-gov-watch-update.yml`](workflows/ai-gov-watch-update.yml) — runs weekly (Mondays) + on manual trigger.
- **Instructions Claude follows:** [`.github/prompts/update-tracker.md`](prompts/update-tracker.md) — the conservative, convention-matching update task (research since the last update → draft event briefs from `templates/` → register `SOURCES.md` citation keys → update `README.md` "Latest" + `CHANGELOG.md`; **0–3 items per run; no changes if nothing new is verifiable**).
- **Output:** the `anthropics/claude-code-action@v1` action commits the changes and opens a PR for review.

## One-time setup
1. **Add the API-key secret:** repo → Settings → Secrets and variables → Actions → **New repository secret** → name `ANTHROPIC_API_KEY`, value = a key from <https://console.anthropic.com>. *(The scheduled runs bill per-token to this key; a weekly bounded run is cheap.)*
2. **Install the Anthropic GitHub App** on this repo if prompted (so the action can commit + open PRs as `claude[bot]`): <https://github.com/apps/claude>.
3. *(Optional)* adjust the cron in the workflow, or the `--max-turns` / model in `claude_args`.

## Testing it
- Go to the **Actions** tab → **"AI Governance Watch — weekly auto-update"** → **Run workflow** (the `workflow_dispatch` button). It will research, draft, and open a PR you can review.

## Editing the behavior
- Change *what/how* it researches by editing **`.github/prompts/update-tracker.md`** (no workflow change needed).
- Change *when* it runs by editing the `cron` in the workflow.
