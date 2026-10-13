# Codex repository instructions — Gacha Advisor

This repository maintains a **ChatGPT Project configuration** for Gacha Advisor. It is NOT a custom chatbot or an MCP server.

## Purpose

- Improve the reliability of Genshin, WuWa, HSR, ZZZ, and NTE recommendations.
- Keep account facts separate from general game rules and advisor behavior.
- Prepare files for manual installation in the existing ChatGPT Project `gacha`.

## Working rules

- Before editing, locate the three knowledge files (`gacha-game-advisor.md`, `equipment-stat-reference.md`, `account-snapshots.md`). They may be at the repository root or under `references/`. Use the existing layout; do not move or overwrite files merely to match another ZIP.
- For advisor/refinement tasks, consult `.agents/skills/gacha-advisor/SKILL.md` and follow its workflow.
- The current knowledge files are at the repository root. Keep `.agents/skills/gacha-advisor/SKILL.md` as the single canonical Skill entrypoint; do not maintain a second root-level `SKILL.md`.
- Keep the three knowledge files canonical. Account facts belong in the matching game section of `account-snapshots.md`; equipment rules belong in `equipment-stat-reference.md`; recommendation behavior belongs in `gacha-game-advisor.md`. Maintenance notes and optional checks belong in `docs/`, not in Project sources.
- Keep the advisor instructions under **8,000 characters**; do not copy long rosters or stats tables into it.
- Treat account facts as user-reported; distinguish owned, discussed, and unknown.
- Revalidate time-sensitive gameplay information with up-to-date reliable sources when research tools are available, documenting date and version. Do not fabricate confirmation.
- Never infer legal Main Stats from recommendations or assume a stat is optimal because it is legal.
- Preserve existing user data; propose uncertain corrections instead of silently replacing it.
- Apply explicit newer user account corrections only to the affected fields, recording provenance; preserve separately named variants and unrelated data.
- Make edits in files, summarize changes, and identify what must be manually refreshed in the ChatGPT Project.

## Scope, phase 1
Markdown documentation + repo + reusable Codex Skill only. No MCP, API, chatbot, backend, frontend, database, Python app, or multi-agent implementation.

Read-only investigation and planning of HoYoLAB imports are allowed; see `docs/hoyolab-import.md`. Importer implementation requires a separate task. Never copy cookies or tokens into this public repository.

## Conversation boundaries

- The main chat handles repository maintenance and project decisions. Separate chats handle gameplay recommendations for each game; use the current files as durable context rather than assuming access to another chat's transcript.
- For gameplay advice in Codex, read `gacha-game-advisor.md` and the relevant game's account/equipment sections. Recommendation discussions do not require reorganizing the repository.
- Record explicit account updates only in the affected game section, with provenance. Distinguish a proposed team/build from what the user actually uses. Avoid concurrent edits to the same file across chats.

## Delivery checks

- Advisor length < 8,000 characters.
- Cross-links use actual filenames in this repository.
- User data provenance is explicit.
- README specifies how to copy project instructions and add project sources.
- The optional examples in `docs/quality-checks.md` cover Genshin ER% slot legality, WuWa Echo stat legality and unknown substats, NTE team-specific builds, and account-specific pull value.
- Distinguish local document/Skill checks from live ChatGPT results. Live checks are optional troubleshooting; run them only when requested and when the configured Project is accessible and current. Unexecuted cases do not block local work or publication.
