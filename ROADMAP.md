# Gacha Advisor — próximos passos

Proposta de prioridades em 2026-10-12. A base documental e a Skill já estão no repositório público [cristianworth/gacha-advisor](https://github.com/cristianworth/gacha-advisor). Os passos abaixo são sugestões; não representam dados de conta confirmados nem funcionalidades implementadas.

## Sugestão para começar

**Completar o contexto do jogo que você estiver jogando ou planejando pulls agora.** Escolha dois ou três times usados e registre as armas/signatures, dupes/refinamentos, investimento atual e o objetivo da próxima decisão. Não é necessário cadastrar todas as builds dos cinco jogos antes de obter recomendações úteis.

HSR e ZZZ já têm rosters extensas registradas, mas equipamentos e builds continuam desconhecidos. Em WuWa, ainda falta uma roster confirmada para avaliar substitutos e valor de pulls. A escolha do primeiro jogo fica com sua necessidade atual; o snapshot não estabelece qual é seu favorito.

Depois de registrar os dados, use uma pergunta real — por exemplo, qual melhoria priorizar em um time — para descobrir se ainda falta alguma informação. Atualize o Projeto ChatGPT quando quiser usar esse contexto lá. Também pode pedir a recomendação diretamente ao Codex neste repositório.

## Ordem proposta

| Prioridade | Melhoria | Resultado concreto | Quando fazer |
|---|---|---|---|
| 1 | Completar o contexto da conta aos poucos | Snapshot com armas/signatures, refinamentos, times usados, investimento e objetivo do jogo escolhido | Antes de uma decisão que dependa desses dados |
| 2 | Registrar contexto dos times | Separar time usado, time pretendido e composição apenas discutida; informar conteúdo-alvo e limitações relevantes | Ao pedir build, rotação ou troca de integrante |
| 3 | Resolver regras de equipamento ainda incertas | Referência corrigida com fonte, data e versão identificada quando disponível | Quando a regra afetar a escolha de uma peça ou gasto de recursos |
| 4 | Refinar as instruções a partir de erros reais | Correção curta que trate a causa de uma resposta errada sem ampliar desnecessariamente o prompt | Quando uma resposta inventar dados, confundir variantes ou recomendar stats ilegais |
| 5 | Registrar prioridades de investimento e pulls | Snapshot com metas, alternativas possuídas e orçamento informado pelo usuário | Antes de decidir entre personagem, signature, dupe ou melhoria de build |
| 6 | Reavaliar a organização dos documentos | Divisão por jogo somente se o arquivo atual ficar difícil de manter ou consultar | Se aparecer um problema concreto de manutenção ou consulta |

As primeiras duas prioridades podem ser feitas juntas, com os dados disponíveis. Não dependem de pesquisa completa de todos os personagens nem de preencher cada campo do snapshot.

## Lacunas já identificadas

- **HSR:** Light Cones, refinamentos, builds e times usados; forma específica dos registros de Trailblazer e March 7th quando relevante. Preservar variantes e Eidolons já informados.
- **ZZZ:** W-Engines, refinamentos, Drive Discs e times usados. Preservar a regra relatada de S-rank M0 e A-rank M6 para os 47 Agents registrados; novas aquisições precisam de confirmação própria.
- **WuWa:** roster e armas possuídas, time atual e recursos relevantes para pulls. Os 157 Echoes nível zero não permitem inferir substats.
- **Genshin:** armas individuais/refinamentos e builds dos times escolhidos; esclarecer as notações pendentes somente quando necessário, sem substituir o relato original.
- **NTE:** distinguir membros possuídos de composições discutidas; confirmar `Skia C6` antes de converter a notação. Verificar regras de Arc/Console e de Main Stats/substats em Modules quando afetarem uma recomendação.
- **Referência WuWa:** confirmar regras atuais de Data Modify/reroll antes de recomendar o uso desses recursos.

## Como manter sem transformar isso em outra tarefa

1. Informe uma aquisição, mudança de investimento ou objetivo quando achar relevante. O Codex atualiza apenas os campos afetados no documento adequado, preservando origem e dados anteriores ainda válidos.
2. Se uma pergunta depender de mecânica atual, pesquise essa mecânica e registre a fonte na referência. Não é necessário revisar todos os jogos a cada patch.
3. Versione as alterações desejadas no Git. O README explica quais arquivos atualizar manualmente no Projeto ChatGPT; enviar ao GitHub não atualiza o Projeto.
4. Use o checklist do README somente se quiser investigar um erro ou conferir uma mudança importante. Não há rotina obrigatória de testes no ChatGPT nem necessidade de comparar interfaces.

`ROADMAP.md`, `AGENTS.md` e a Skill são documentos de manutenção. No Projeto ChatGPT, continue usando `gacha-game-advisor.md` nas instruções e `equipment-stat-reference.md` + `account-snapshots.md` como fontes.

## Ideias adiadas

Sincronização automática, MCP, chatbot próprio, APIs, backend, frontend, banco de dados e aplicação Python continuam fora desta fase. Só vale reconsiderar automação se a atualização manual se tornar um problema frequente e você pedir essa mudança. O próximo ganho esperado vem de contexto melhor e correções fundamentadas nos documentos existentes.
