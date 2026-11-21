# Codex repository instructions — Gacha Advisor

This repository maintains a **ChatGPT Project configuration** for Gacha Advisor. It is NOT a custom chatbot or an MCP server.

## Purpose

- Improve the reliability of Genshin, WuWa, HSR, ZZZ, and NTE recommendations.
- Keep account facts separate from general game rules and advisor behavior.
- Prepare files for manual installation in the existing ChatGPT Project `gacha`.

## Working rules

- Before editing, read the layout in `README.md`. The three knowledge files live in `advisor/`; maintenance documents live in `docs/`. Do not move or overwrite them merely to match another starter kit.
- For advisor/refinement tasks, consult `.agents/skills/gacha-advisor/SKILL.md` and follow its workflow.
- The current knowledge files are in `advisor/`. Use `.agents/skills/gacha-advisor/SKILL.md` for maintenance and review, `.agents/skills/build/SKILL.md` for character builds, and `.agents/skills/meta-preview/SKILL.md` for upcoming versions and pull priorities. Keep shared guidance in `advisor/` and Skill entrypoints under `.agents/skills/`.
- Keep the three knowledge files canonical. Account facts belong in the matching game section of `advisor/account-snapshots.md`; equipment rules belong in `advisor/equipment-stat-reference.md`; recommendation behavior belongs in `advisor/gacha-game-advisor.md`. Maintenance notes and optional checks belong in `docs/`, not in Project sources.
- Keep only `advisor/gacha-game-advisor.md` under **8,000 characters**, the repository compatibility ceiling for the Project Instructions field reported by the user. This ceiling does not apply to the two uploaded Project sources; see README for their separately documented upload limits. Do not copy long rosters or stats tables into the instructions.
- Treat account facts as user-reported; distinguish owned, discussed, and unknown.
- Revalidate time-sensitive gameplay information with up-to-date reliable sources when research tools are available, documenting date and version. Do not fabricate confirmation.
- Never infer legal Main Stats from recommendations or assume a stat is optimal because it is legal.
- Preserve existing user data; propose uncertain corrections instead of silently replacing it.
- Apply explicit newer user account corrections only to the affected fields, recording provenance; preserve separately named variants and unrelated data.
- For listed owned weapons in WuWa and NTE, omit repeated default values: one copy at R1 unless an explicit exception is given. Preserve all exceptions; do not apply this default to other games or infer ownership from it.
- Keep provenance in the relevant account section and editing history in Git. Do not keep completed handoffs or maintenance logs in Project sources.
- Make edits in files, summarize changes, and identify what must be manually refreshed in the ChatGPT Project.

## Scope, phase 1
Markdown documentation + repo + reusable Codex Skill only. No MCP, API, chatbot, backend, frontend, database, Python app, or multi-agent implementation.

Read-only investigation and planning of HoYoLAB imports are allowed; see `docs/hoyolab-import.md`. Importer implementation requires a separate task. Never copy cookies or tokens into this public repository.

## Conversation boundaries

- The main chat handles repository maintenance and project decisions. Separate chats handle gameplay recommendations for each game; use the current files as durable context rather than assuming access to another chat's transcript.
- For gameplay advice in Codex, read `advisor/gacha-game-advisor.md` and the relevant game's account/equipment sections. Recommendation discussions do not require reorganizing the repository.
- Record explicit account updates only in the affected game section, with provenance. Distinguish a proposed team/build from what the user actually uses. Avoid concurrent edits to the same file across chats.

## GitHub contribution workflow

- Use an issue when work needs tracking; reuse an existing issue instead of duplicating it. The proposals in `docs/ROADMAP.md` remain conditional, not a mandatory backlog.
- Work on a short-lived branch from the updated remote default branch, `origin/main`. Preserve unrelated local commits, staged changes and files.
- Describe the problem, resulting behavior, validation and limitations in the PR, linking the issue when there is one. Keep the PR in draft while review or validation is pending; track current delivery status in the issue/PR.
- Review the diff and applicable checks for the current head SHA. Pending checks or evidence for another SHA do not validate that head. When no CI applies, explicitly record the documentary checks performed and their limits.
- Integrate only after Cristian approves the reviewed diff and authorizes integration. If the content changes, renew review, applicable checks and approval before integration. Direct pushes to `main` require explicit authorization.
- This workflow grants no standing permission for commits, pushes, integration or publication beyond the current request. Continue routine implementation decisions within the already authorized scope without requesting approval for each step.
- Git commits, pushes and merges do not update the ChatGPT Project. Refreshing its instructions or sources is a separate manual publication step, requiring authorization; follow `README.md` when requested.

## Delivery checks

- `advisor/gacha-game-advisor.md` length < 8,000 characters, including whitespace. No 8,000-character check for `account-snapshots.md` or `equipment-stat-reference.md`.
- Cross-links use actual filenames in this repository.
- User data provenance is explicit.
- README specifies how to copy project instructions and add project sources.
- The optional examples in `docs/quality-checks.md` cover Genshin ER% slot legality, WuWa Echo stat legality and unknown substats, NTE team-specific builds, and account-specific pull value.
- Distinguish local document/Skill checks from live ChatGPT results. Live checks are optional troubleshooting; run them only when requested and when the configured Project is accessible and current. Unexecuted cases do not block local work or publication.
