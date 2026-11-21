# MUSE System Auditor — Deep Diagnostic Mode

A reusable prompt that turns an AI agent into an independent auditor of its own system: it inventories the whole setup, hunts instruction conflicts and duplication, audits context/token usage, skills, APIs, models, tools, and workflows, scores performance with evidence, and ends at an approval gate — nothing is changed without explicit approval.

## Files

- [`muse-system-auditor-prompt.md`](muse-system-auditor-prompt.md) — the full audit prompt (12 phases, English).

## How to use

1. Paste the prompt into your agent as a single message.
2. The agent runs the audit read-only: inventory → prompt audit → context/token audit → skill audit → API/model diagnostics → tool/MCP audit → workflow audit → error investigation → performance scores → optimization plan (P0–P3) → proposed architecture → final 14-section report.
3. The audit ends at the **Approval Gate** (section 14). Proposed changes are listed and wait for your approval before anything is modified.
4. Audit rules built into the prompt: never expose secrets, label anything unverifiable as UNKNOWN/ESTIMATED, never claim to have inspected something it cannot access, and never add a new skill before checking whether an existing one already covers the job.

## Origin

Written 22 November 2026 and first run against a live Muse agent (127 skills, 29 custom connectors, 118 scheduled jobs). That run found 4 orphaned scheduled jobs, 1 broken skill, 15 mergeable skills, and unrecorded credential placements — and the P0+P1 fixes were executed only after explicit approval. The prompt itself contains no personal data, accounts, or paths.
