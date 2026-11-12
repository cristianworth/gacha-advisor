---
name: build
description: Give Cristian a concise character build for Genshin Impact, Wuthering Waves, Honkai Star Rail, Zenless Zone Zero, or Neverness to Everness. Use for `$build <character>` or a complete build request covering upgrade order, gear, and team.
---

# Character build

Use the character name as the required input. An explicit game, team, role, target content, or constraint in the request takes precedence over defaults. Otherwise use the game established in the chat, or resolve it from the character if unambiguous. If the character or variant is ambiguous and the distinction changes the build, ask which one. Example: `$build Akane Rin com Zero, mantendo Sakiri no time do Zankou`.

## Context

- Follow the [Advisor instructions](../../../advisor/gacha-game-advisor.md) for research, evidence, and recommendations. Verify patch-sensitive claims as directed there.
- Read the relevant game section in [account snapshots](../../../advisor/account-snapshots.md) and use explicit newer account facts from the chat. Check ownership, dupes, equipment assignments, active teams, and current investment. Treat missing details as unknown.
- Consult the same game's [equipment reference](../../../advisor/equipment-stat-reference.md) before recommending Main Stats. Use the selected team and role to decide which legal stats are useful.
- Use a supplied team or propose one from the roster. If a missing detail could change the recommendation, give a useful conditional answer when possible and ask only for that detail. A build request authorizes advice; record account changes only on explicit request.

## Response

Answer in Portuguese with three compact bullets, using short lines where slot details or inputs need space. Start with the upgrade order. Aim for about 150 words by default. Expand when asked or when an extra detail changes the decision. Give one recommendation per decision by default, with an alternative only when it solves a concrete constraint. Cite the sources supporting the key numbers and mechanics once, close to the relevant bullet.

1. **Upe nesta ordem.** Use `pré-requisito → upgrade → próximo upgrade`, with target levels or thresholds where supported. Include the actual skill order and a practical stopping point. Put ascension, gear farming, or a breakpoint before talents when it is the bigger immediate upgrade. Use recorded levels and bottlenecks to choose the next action. If evidence supports only a qualitative order, give that order.
2. **Equipe.** Give the weapon, set, variable Main Stats by slot or cost, and substat priority. Include any breakpoint that affects the build and mention a borrowed weapon when its assignment matters. If the signature is a live decision, give the verdict and the main reason against the best available alternative at the recorded refinement or equivalent. When a reliable percentage matters or is requested, identify the baseline and whether it measures personal damage, team damage, or another relevant outcome.
3. **Jogue com.** Name one team and give the defining action sequence or trigger in a short line. Label untested adaptations as proposed. Expand opening, loop, input timing, member roles, and dupe effects when requested or necessary for the sequence to work.

Keep details in the bullet where they change an action. Skip fixed Main Stats, generic kit explanations, and a closing recap by default. If the user asks for just one part, answer that part directly.
