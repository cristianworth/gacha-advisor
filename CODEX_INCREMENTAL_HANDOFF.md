# Incremental handoff — preserve the existing Codex workspace

You are continuing an already-started **Gacha Advisor 2.0** repository. DO NOT create a new project, clone a new scaffold, reset Git, or overwrite work that has already been completed.

## What was missing from the original simple ZIP

Comparing `gacha-advisor-simple-starter.zip` to `gacha-advisor-repo-v1.zip`:
- **Added:** `AGENTS.md` (Codex repository instructions).
- **Added:** `.agents/skills/gacha-advisor/SKILL.md` (Codex maintenance/research workflow).
- **Organizational only:** the three Markdown knowledge files were moved into `references/` in the second ZIP; their contents were byte-identical. Moving them is OPTIONAL; preserve whatever structure this repository currently uses.
- **Changed:** `README.md` and `CODEX_HANDOFF.md` in the second ZIP to mention the Skill, AGENTS.md, and the clarified scope. Their older versions explicitly prohibited creating a Skill; remove those obsolete prohibitions if they remain.

## Your task now (incremental, not a restart)

1. Inspect the current repository, existing changes, `README.md` and any prior handoff.
2. Merge/add `AGENTS.md` and `.agents/skills/gacha-advisor/SKILL.md` from the attached incremental patch/content. If these files already exist, compare and merge deliberately rather than overwriting.
3. Retain the existing three knowledge documents and all edits already made. Do not replace them with older ZIP versions or move them just to match a template.
4. Update the current README/handoff ONLY where needed: describe Git repository + Codex Skill + the three Markdown knowledge sources. Remove any outdated directive that says 'do not create a Skill'.
5. Distinguish responsibilities:
   - `AGENTS.md`: instructions for Codex while editing the repo.
   - `.agents/skills/gacha-advisor/SKILL.md`: reusable workflow for maintaining/reviewing the Advisor.
   - `gacha-game-advisor.md`: content for ChatGPT Project **instructions**, under 8,000 characters.
   - `equipment-stat-reference.md` and `account-snapshots.md`: content for ChatGPT Project **sources**.
6. No MCP, standalone chatbot, backend, Python package, schemas or tools in this phase. Research and manual regression checks are in scope; code is not.
7. Check paths, frontmatter validity, prompt character count, account provenance, historical source caveats, and manual regression examples (Genshin ER Sands vs Goblet/Circlet; WuWa 1/3-cost; NTE Daffodil different teams; account-specific pull value).
8. Report actual files changed and any conflicts found. Explain how to use the Skill in Codex and how to manually update the existing ChatGPT Project `gacha`. Do not claim local repository files auto-sync with ChatGPT Project.

Do the incremental edits in the current workspace. Do not stop at a proposal and do not start over.

## Incorporation status — 2026-10-12

- The provided root `AGENTS.md` and `SKILL.md` matched the patch content. `AGENTS.md` was merged with delivery/provenance clarifications; the Skill was moved to `.agents/skills/gacha-advisor/SKILL.md` and refined there. No duplicate root Skill remains.
- Knowledge files remain at the root, with all prior edits preserved, including the 72 HSR entries and 47 ZZZ Agents. README and `CODEX_HANDOFF.md` now describe the Skill and manual Project updates.
- The patch is retained as the original input, not as the current authoritative instructions; do not reapply it blindly over the incorporated files.
- No Git metadata was found in this workspace. Git initialization, commits and remotes were not created. Continue from the existing files and report this versioning limitation.
- Local validation is separate from the live README regression checklist; cases requiring the configured ChatGPT Project remain pending until run there.
