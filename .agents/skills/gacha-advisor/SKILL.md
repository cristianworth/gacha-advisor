---
name: gacha-advisor
description: Maintain the Gacha Advisor Markdown instructions, equipment references and account snapshots. Use for repository updates and reviews of build, rotation or pull recommendations for the ChatGPT Project gacha.
---

# Gacha Advisor — Codex Skill

## Purpose
This Skill guides **Codex work on the repository**, not a standalone chatbot. It does not automatically run within a ChatGPT Project. For user-facing gameplay advice, prepare the Project instructions and reference files in the existing knowledge files.

## Required repository context

Paths below resolve from this Skill directory into the existing repository layout. Read only the context needed for the requested change; preserve the layout.

- [AGENTS.md](../../../AGENTS.md) — repository scope and delivery checks.
- [gacha-game-advisor.md](../../../advisor/gacha-game-advisor.md) — ChatGPT behavior and research policy.
- [account-snapshots.md](../../../advisor/account-snapshots.md) — user-reported ownership, builds, teams and unknowns.
- [equipment-stat-reference.md](../../../advisor/equipment-stat-reference.md) — historical stat legality, sources and verification caveats.
- [README.md](../../../README.md) — installation, chat organization and manual source updates.

This workflow covers Markdown maintenance and recommendation review. MCP, standalone chatbot, APIs, backend, frontend, databases and Python applications remain outside this phase. A review request does not authorize updating the live ChatGPT Project or messaging another chat.

## Workflow

1. **Determine request:** documentation improvement, game account update, equipment rule correction, or recommendation-quality review.
2. **Collect known context:** read relevant files; do not convert "discussed" into "owned" or turn unknown items into zero. Apply explicit newer user updates to the affected fields with provenance. Preserve unrelated entries and separately named variants; public metadata does not invalidate user-reported ownership.
3. **Check currentness:** when a kit, mechanic, banner or patch matters, seek official/in-game info first, then specialist guides, then community testing. Record source links, consultation date and game version where found. A consultation date does not certify the current patch. Label unverified facts; do not pass beta/leaks as confirmed. If research is unavailable, preserve the caveat rather than inventing a correction.
4. **Separate concepts:** slot-legal Main Stat vs team-optimal Main Stat; source claims vs user-reported facts; baseline vs signature/dupe investment.
5. **For recommendation reviews, analyze the specific team:** field time, application, buffs/debuffs, triggers, energy, constraints, realistic rotation, and replacements already owned. Do not require a team analysis for a simple account-data update.
6. **Avoid invented details:** never fabricate sources, numerical gains, input sequences, stat availability, account inventory or pull probabilities.
7. **Write focused changes:** keep the behavior prompt below 8,000 characters, put stable mechanics in equipment reference, put ownership only in snapshots.
8. **Quality check:** inspect the actual diff, verify local references/frontmatter and count all advisor characters, including whitespace. Check applicable [quality criteria](../../../docs/quality-checks.md) against the documents. Run live ChatGPT cases only when requested and when the configured Project is accessible and current; report only cases actually run. Unexecuted cases are not mandatory pending work. Do not claim a document review proves live response quality.

## Example regressions

- Genshin: ER% is legal Sands, illegal Goblet and Circlet Main Stat.
- WuWa: Fusion DMG primary on 3-cost, not on 1-cost; a level-zero Echo does not have revealed substats.
- NTE: compare Daffodil requirements in Blackbird vs Zankou teams rather than reusing a universal build.
- HSR/ZZZ: use the recorded rosters and dupes, keep variants distinct, and do not infer unreported weapons or builds.
- Pull value: consider team composition, options already owned, signature/dupes and opportunity cost.

## Output for repo changes

Summarize edited files with the actual diff, verified facts, unresolved questions, local checks versus any live cases actually run, length of advisor instructions, and exact manual steps needed to refresh the ChatGPT Project. If Git metadata is absent, report it and compare file contents without initializing/resetting Git unless explicitly requested. Do not claim the Codex workspace and the ChatGPT Project synchronize.
