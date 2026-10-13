# Gacha Advisor — handoff de manutenção

Atualizado em **2026-10-13**. Continue neste repositório; preserve os arquivos e o histórico. Leia [AGENTS.md](../AGENTS.md), [README.md](../README.md) e a [Skill gacha-advisor](../.agents/skills/gacha-advisor/SKILL.md) conforme a tarefa.

## Estado atual

- Repositório público [cristianworth/gacha-advisor](https://github.com/cristianworth/gacha-advisor), branch `main`, remoto `origin`.
- Os três documentos de conhecimento estão em `advisor/`; os nomes dos arquivos e seu conteúdo foram preservados na reorganização. A raiz mantém README, AGENTS e `.gitignore`; este handoff e o roadmap ficam em `docs/`. Instruções do Advisor: menos de 8.000 caracteres; regras de equipamentos e dados da conta em fontes separadas.
- A Skill do patch incremental já foi incorporada. O handoff incremental foi removido após conclusão; seu conteúdo permanece no histórico Git. O patch e o diff locais da integração foram removidos.
- HSR: 72 registros de personagens com Eidolons relatados. ZZZ: 47 Agents, com 34 S-rank M0 e 13 A-rank M6 conforme a regra informada pelo usuário. Preservar variantes, nomes, origem e desconhecidos.
- Chat principal: manutenção do repositório. Chats separados por jogo: recomendações e atualizações da seção correspondente. Os arquivos são o contexto durável; não presuma acesso ao histórico de outros chats.
- Fontes do Projeto ChatGPT são atualizadas manualmente pelo usuário. Nenhuma alteração local implica upload.

## Pendências e decisões

- Completar equipamentos, builds, times e objetivos conforme necessário; ver [ROADMAP.md](ROADMAP.md).
- Preservar ressalvas históricas na referência: Arc/Console e coincidência de Main Stats/substats em Modules NTE; regras atuais de Data Modify/reroll WuWa. `Skia C6`, formas HSR e outras notações pendentes não devem ser corrigidas por suposição.
- Importação HoYoLAB: pesquisa documentada em [docs/hoyolab-import.md](hoyolab-import.md). A estrutura de cookies do Auto-Checkin foi inspecionada; não houve consulta autenticada da conta nem implementação de importador.
- [Checklist de qualidade](quality-checks.md) é opcional para investigar problemas. Verificações documentais não comprovam respostas do ChatGPT; nenhum teste ao vivo é requisito de publicação.

## Escopo e entrega

A implementação atual é Markdown + Git + Skill. Pesquisa e planejamento de importação são permitidos; implementação de importador requer uma tarefa própria. MCP, chatbot próprio, backend, frontend, banco de dados e aplicação Python continuam adiados.

Faça mudanças focadas, confira o diff e as referências, preserve dados da conta e informe exatamente quais arquivos o usuário precisa atualizar no ChatGPT. Não mantenha handoffs de tarefas concluídas duplicando README, AGENTS ou roadmap.
