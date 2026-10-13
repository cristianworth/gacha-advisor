# Importação HoYoLAB — pesquisa e proposta

Estado em **2026-10-13**: viabilidade identificada em código e documentação; **nenhum importador implementado e nenhuma consulta autenticada da conta executada**. Este é um documento de manutenção, não uma fonte do Advisor.

## O que foi verificado

- [Enka.Network](https://enka.network/) consulta personagens da vitrine pública por UID. Não deve ser tratado como uma roster completa. A consulta pública de ZZZ feita nesta conversa retornou HTTP 424; isso não confirmou dados da conta nem a invalidade do UID. O Enka associa esse status a manutenção/problemas após atualização: [documentação de códigos](https://github.com/EnkaNetwork/API-docs/blob/master/api.md#http-response-codes).
- [genshin.py](https://github.com/seriaati/genshin.py) implementa consultas autenticadas do HoYoLAB para os jogos HoYoverse. Em ZZZ, `avatar/basic` lista Agents possuídos e `avatar/info` consulta detalhes: [implementação](https://github.com/seriaati/genshin.py/blob/master/genshin/client/components/chronicle/zzz.py). Há modelos para Mindscapes, W-Engines e Drive Discs: [referência](https://seria.is-a.dev/genshin.py/reference/models/zzz/character/).
- O repositório privado [HoyoLab-Auto-Checkin](https://github.com/cristianworth/HoyoLab-Auto-Checkin) do usuário foi inspecionado. Usa Google Apps Script, `UrlFetchApp` e cabeçalho `Cookie` com `ltoken_v2`/`ltuid_v2`. O script não foi executado, os valores das credenciais não foram incorporados neste repositório e a validade atual deles não foi testada.
- `ltuid_v2` identifica a conta HoYoLAB; o UID de ZZZ identifica a conta no jogo. Cookie da conta correta, UID do jogo e servidor devem corresponder. Check-in funcionando não demonstra que todo endpoint de detalhes aceite a mesma requisição.
- Dependendo do endpoint, podem ser necessários cabeçalhos ou tokens adicionais, como `e_nap_token` e identificação de dispositivo: [exemplo ZZZ](https://github.com/Syqhu/zzz-api#optional-hoyolab-integration). A documentação comunitária não garante estabilidade de uma API oficial para desenvolvedores.

Fontes consultadas em 2026-10-13. Esta pesquisa não verificou o inventário real do usuário, os detalhes de cada endpoint em produção nem a completude de uma futura exportação.

## Proposta para uma próxima tarefa

Aproveitar a estrutura de autenticação já utilizada no Apps Script, com uma função separada de leitura, executada manualmente quando o usuário quiser atualizar.

1. Confirmar que a sessão corresponde à conta ZZZ desejada e identificar seu servidor.
2. Consultar a roster e os Mindscapes; comparar os campos retornados com o HoYoLAB.
3. Consultar um Agent para validar W-Engine, discos e habilidades antes de ampliar a coleta.
4. Exportar somente dados de jogo necessários, com data, origem e indicação de completude.
5. Mostrar diferenças contra [account-snapshots.md](../advisor/account-snapshots.md), preservando nomes, variantes e observações. Dados ausentes ou consultas parciais não removem registros. Valores coletados só substituem a regra relatada M0/M6 nos campos confirmados e com origem registrada.
6. Atualizar o Markdown após revisão. O usuário continua substituindo a fonte do Projeto ChatGPT manualmente.

As etapas acima são propostas, não trabalho concluído. A biblioteca Python serve como referência de comportamento; não exige criar uma aplicação Python neste repositório. A coleta DOM no navegador permanece alternativa caso a autenticação existente não seja suficiente.

## Credenciais e exportações

Como o Gacha Advisor é público, mantenha cookies/tokens fora do código versionado, dos logs e das fontes ChatGPT. Para uma solução Apps Script, usar propriedades do script para configuração de autenticação é a sugestão inicial; não copiar credenciais do projeto privado para este repositório.

Uma importação captura estado de conta; não determina a build ótima, as preferências ou os times pretendidos. Esses conceitos continuam separados conforme o [README](../README.md). MCP, servidor, chatbot e sincronização automática com o ChatGPT permanecem adiados.
