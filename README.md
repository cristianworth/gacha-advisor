# Gacha Advisor — configuração do Projeto ChatGPT

O Projeto ChatGPT existente **`gacha`** continua como interface para recomendações. O conhecimento fica em Markdown para versionamento Git; `AGENTS.md` e a Skill local orientam sua manutenção no Codex. Revisão dos documentos: 2026-10-12.

## Instalação

1. Abra o Projeto **`gacha`** no ChatGPT.
2. Abra **Project settings → Instructions** (Configurações do projeto → Instruções). Cole o conteúdo completo de `gacha-game-advisor.md` e salve. Use-o como as instruções do Advisor; não basta anexar esse arquivo como fonte. O conteúdo deve permanecer com **menos de 8.000 caracteres**, incluindo espaços e quebras de linha.
3. Em **Project sources / Fontes do projeto**, adicione os arquivos `equipment-stat-reference.md` e `account-snapshots.md`, mantendo esses nomes.
4. Inicie uma conversa dentro de `gacha` e peça: “Consulte as duas fontes do Advisor e diga quais dados de conta e regras de equipamentos estão disponíveis e quais ainda são desconhecidos.” Confira a resposta contra os arquivos; repetir os nomes dos arquivos não comprova que foram consultados.

| Documento local | Destino |
|---|---|
| `gacha-game-advisor.md` | Conteúdo colado em **Instructions** |
| `equipment-stat-reference.md` | Arquivo adicionado às **Project sources** |
| `account-snapshots.md` | Arquivo adicionado às **Project sources** |
| `AGENTS.md` | Regras locais do Codex para editar este workspace; não enviar ao Projeto |
| `.agents/skills/gacha-advisor/SKILL.md` | Workflow local do Codex para manutenção e revisão; não enviar ao Projeto |
| `README.md` | Guia local; não precisa ser enviado |
| `CODEX_HANDOFF.md` | Orientação local para revisão; não enviar como instruções ou fonte do Advisor |
| `CODEX_INCREMENTAL_HANDOFF.md` / `gacha-advisor-incremental.patch` | Histórico da incorporação incremental; não enviar ao Projeto nem reaplicar o patch sobre os arquivos atuais |

Projetos ChatGPT compartilham instruções e fontes entre suas conversas; arquivos de uma pasta local precisam ser enviados separadamente. Veja a [documentação oficial — Projects and chats](https://learn.chatgpt.com/docs/projects), consultada em 2026-10-12. Os rótulos da interface podem variar conforme idioma/cliente.

## Usar a Skill no Codex

Abra este workspace no Codex. A Skill está em `.agents/skills/gacha-advisor/SKILL.md`, com nome `gacha-advisor`; os três arquivos de conhecimento permanecem na raiz. Não é necessário copiá-la para uma pasta global nem criar outro projeto.

Exemplo de pedido:

```text
Use $gacha-advisor para revisar as instruções e as fontes deste workspace.
Preserve os dados da conta, faça apenas as correções necessárias e mostre o diff.
```

O Codex pode selecionar a Skill quando o pedido corresponde à descrição; você também pode invocá-la explicitamente. Se não aparecer entre as Skills disponíveis, reinicie o Codex. Como alternativa, peça para ler `.agents/skills/gacha-advisor/SKILL.md` e seguir o workflow. Consulte a [documentação oficial OpenAI — Build skills](https://learn.chatgpt.com/docs/build-skills), conferida em 2026-10-12.

A Skill orienta pesquisa, manutenção das fontes e revisão da qualidade das recomendações no Codex. As instruções do Advisor continuam sendo o comportamento usado no Projeto ChatGPT. A Skill não executa automaticamente dentro de `gacha`, não fornece acesso à conta e não sincroniza fontes.

## Estado do versionamento

Na inspeção de 2026-10-12, `D:\Repo\gacha-advisor` não foi reconhecido como repositório Git e não havia `.git` neste workspace. O versionamento é parte da arquitetura pretendida, mas ainda não está ativo nesta pasta. Nenhum repositório foi inicializado ou reinicializado, nem foram feitos commits. É necessário esclarecer onde está o repositório existente ou autorizar sua configuração em outra tarefa. Não mova o conhecimento apenas para reproduzir a estrutura de outro starter kit.

## Atualizações manuais

O `AGENTS.md` e a Skill fornecidos no patch incremental foram incorporados. MCP, chatbot próprio, APIs, backend, frontend, banco de dados e aplicação Python continuam fora do escopo.

**Este workspace não sincroniza automaticamente com o Projeto ChatGPT.** Alterar um Markdown aqui não atualiza a cópia enviada. Esta revisão não alterou o Projeto `gacha`.

Ao mudar as instruções, cole novamente o conteúdo atualizado e salve. Ao mudar uma fonte, substitua a cópia antiga pela nova; confira que não ficaram versões concorrentes do mesmo snapshot/referência. Para atualizações da conta, registre o dado e a data do relato no snapshot e reenvie-o. Uma correção feita somente em conversa não atualiza o arquivo local nem o upload.

A pesquisa web pode apoiar respostas atuais quando disponível. Sem ela, o Advisor deve identificar a limitação e trabalhar com as fontes datadas, sem alegar confirmação do patch atual.

## Checklist manual de qualidade

Execute cada pergunta em uma conversa dentro do Projeto. A resposta passa se atender ao critério; se falhar, confira o conteúdo das instruções e as versões das fontes enviadas.

| Pergunta de teste | Critério de aprovação |
|---|---|
| “Em Genshin, posso usar ER como Main Stat em Sands, Goblet e Circlet?” | Aceita Energy Recharge% em Sands; rejeita em Goblet/Circlet. Distingue Main Stat de substat. |
| “Em WuWa, posso usar Fusion DMG como Main Stat de Echo 1-cost e 3-cost?” | Aceita primário Fusion DMG Bonus% em 3-cost; rejeita em 1-cost. |
| “Compare builds de Blackbird e Daffodil em Zankou + Blackbird + Daffodil + Sakiri e Blackbird + Sakiri + Daffodil + Haniel.” | Analisa os dois times separadamente; relaciona builds às funções/interações verificadas. Se kits não forem identificados, explicita a lacuna, sem inventar efeitos ou presumir posse dos demais membros. |
| “Vale puxar Hsin para minha conta? E a Signature?” | Considera integrantes do time, roster/substitutos, Signature, dupes, investimento e recursos. Usa cenários/pergunta focada quando faltar informação; não presume posse nem decide somente por tier list. |
| “Meus 157 Echoes nível zero já têm Main Stats ideais. Devo upar ou usar Data Merge?” | Reconhece substats desconhecidos; considera EXP e tuning para revelar rolls. Não presume double crit, raridade, sets ou distribuição exata; verifica regras atuais de merge antes de afirmar custos/resultados. |
| “PEN Ratio pode ser substat de Drive Disc em ZZZ?” | Distingue PEN fixo como substat de PEN Ratio% como Main Stat do slot 5. |
| “Monte um time só com meus personagens de HSR. Quais Eidolons e signatures tenho?” | Usa os 72 registros possuídos e os Eidolons do snapshot; não presume Light Cones, investimento ou kits não verificados. Não mistura variantes nem aplica E6 a todas as formas de Trailblazer/March 7th. |
| “Qual é minha roster de ZZZ? Tenho as signatures e todos já estão buildados?” | Usa os 47 Agents do snapshot: 34 S-rank M0 e 13 A-rank M6. Separa Soldado N.º0 - Anby de Anby e Lúcia de Lucy; não presume W-Engines ou builds. |
| “Skia C6 no snapshot significa A6?” | Identifica a notação pendente; não a converte apenas por convenção. Uma correção explícita posterior do usuário deve prevalecer. |

## O que foi revisado e o que continua pendente

- Instruções: consulta explícita das fontes, respostas proporcionais à pergunta, times com o tamanho próprio de cada jogo, cenários de pulls e tratamento de fontes inacessíveis/conflitantes.
- Equipamentos: tabelas conferidas em KQM/Prydwen, links e datas registrados; corrigidos PEN fixo e Impact% em ZZZ. Consulta a guia não equivale a confirmação oficial/in-game do patch atual.
- Conta: preservados roster, constelações/dupes, signatures relatadas, composições e inventário. Separados posse, discussão e desconhecidos; origem registrada no snapshot inicial e nas atualizações diretas de ZZZ/HSR desta conversa.
- Pendências: regras de Arc/Console, coincidência de Main Stats/substats em Modules NTE, regras atuais de Data Modify/reroll WuWa e mudanças posteriores aos guias. Notações como `Skia C6` e `Cryo Traveler C2` permanecem como fornecidas, com metadados a verificar.

O checklist acima ainda precisa ser executado no Projeto após a instalação; a revisão local não mede a qualidade de respostas de uma configuração que ainda não foi atualizada no ChatGPT.
