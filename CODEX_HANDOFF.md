# Handoff for Codex — Gacha Advisor, Phase 1 (no app development)

You are continuing the existing Gacha Advisor workspace. The current architecture is the ChatGPT Project `gacha` for recommendations, Git-versioned Markdown knowledge, `AGENTS.md` for Codex repository instructions, and `.agents/skills/gacha-advisor/SKILL.md` for Codex maintenance/review. Preserve completed work; do not create another project, reinitialize/reset Git, or replace the knowledge files with an older starter kit.

## Scope — strictly limited

The three knowledge files remain at the workspace root:

- `gacha-game-advisor.md`: advisor behavior, source policy, how to make recommendations.
- `equipment-stat-reference.md`: allowed equipment stats by game and slot.
- `account-snapshots.md`: account facts supplied by me, plus unknown/discussed flags.

Your job is to **review, improve, and prepare these files for use as ChatGPT Project instructions and Project sources**.

Read `AGENTS.md` and use `.agents/skills/gacha-advisor/SKILL.md` for relevant maintenance/review tasks. The Skill is local Codex guidance; do not upload it or `AGENTS.md` as Advisor instructions or Project sources.

Scope: Markdown documentation, Git versioning when available, and the reusable Codex Skill. DO NOT create an MCP server, chatbot, Python app, API, backend, frontend, database, JSON schema, package manager config or multi-agent setup. Do not make a large scaffold. No application scripts or automated gameplay tests are required; local Skill validation and document checks are in scope.

Current state (2026-10-12): the Skill was incorporated from the incremental patch. HSR has 72 user-reported roster entries; ZZZ has 47 (34 S-rank M0, 13 A-rank M6). Preserve all account data and existing historical-source caveats. Following explicit user authorization, Git was initialized in this existing workspace and published to the private repository https://github.com/cristianworth/gacha-advisor, branch `main`, remote `origin`. No project was restarted or knowledge file moved. The original patch and incremental review diff remain local ignored artifacts.

User preference: use Codex for maintenance or gameplay advice and manually refresh the ChatGPT Project whenever desired. Live response checks are optional troubleshooting tools, not a recurring requirement or publication gate; comparison between interfaces is not required. See `ROADMAP.md` for proposed next steps, prioritizing account context over new infrastructure.

## What to do

1. Inspect the current state and read the relevant knowledge files. Do not move them merely to match another starter kit.
2. Tighten `gacha-game-advisor.md` into effective, precise project instructions, staying under **8,000 characters**. Avoid duplicating equipment-slot stat tables or account roster inside instructions. Ensure it references the two accompanying Project source files.
3. Review the equipment reference for internal contradictions, incorrect terminology, slot legality, and uncertainty. For any game detail you cannot confirm with current official or authoritative sources, label it **needs verification**; do not invent corrections. Preserve a short source/date trail.
4. Review account snapshot provenance. Keep owned, discussed and unknown clearly separated. Do not remove user-reported entries just because they are not available in public character databases.
5. Create or improve a short `README.md` explaining exactly how to use the three files in the existing **ChatGPT Project named `gacha`**:
   - Paste `gacha-game-advisor.md` in **Project settings → Instructions**.
   - Add `equipment-stat-reference.md` and `account-snapshots.md` under **Project sources**.
   - Explain that these local Codex files do NOT automatically synchronize with the ChatGPT Project; when changed, update the Project separately.
6. Maintain a concise, optional **quality checklist** in README for troubleshooting, with at least these cases:
   - Genshin ER Main Stat is valid on Sands but invalid on Goblet and Circlet.
   - WuWa Fusion DMG Main Stat is valid for 3-cost Echo, not 1-cost.
   - Blackbird and Daffodil builds can depend on which NTE team is used.
   - Pull value of Hsin must consider the team's units, signature, available roster and investment.
   - WuWa level-zero Echoes have unknown substats; never assume their rolls.
7. Check Skill frontmatter, local references, and advisor length. Review applicable README regression criteria locally. Live ChatGPT checks are optional; if requested, run them only with access to the configured Project and report which were actually run. Unexecuted live checks do not block local work or publication.
8. Briefly identify what was changed, what remains uncertain, and which file belongs in Project instructions versus Project sources. Explain how to invoke the Codex Skill and show the actual diff; distinguish local edits from updates to the ChatGPT Project.

## Quality bar

- Do not confuse the local Codex workspace with the active ChatGPT Project.
- Verify technical details when currentness matters and browsing is available, and explicitly note uncertainty otherwise.
- Prioritize exactness over sheer prompt length.
- Keep the output usable immediately without further development.
- Focus on producing better ChatGPT answers, not an app.

Please **make the edits now** in the current workspace. Do not stop at planning or request unnecessary confirmation.
