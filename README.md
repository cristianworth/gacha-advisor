# Gacha Advisor

Base de conhecimento para recomendações de **Genshin Impact, Wuthering Waves, Honkai: Star Rail, Zenless Zone Zero e Neverness to Everness**, com contexto da sua conta e fontes datadas. Repositório público: [cristianworth/gacha-advisor](https://github.com/cristianworth/gacha-advisor).

## Objetivo e funcionamento

O Advisor combina instruções de resposta, regras de equipamentos e fatos da conta para avaliar builds, times, rotações e pulls. Os documentos versionados são o contexto durável; uma conversa serve para discutir a decisão e informar mudanças.

Você pode usar o Codex neste repositório ou o Projeto ChatGPT **`gacha`**. A configuração atual é documental, com uma Skill de manutenção. Não há aplicativo, servidor ou sincronização automática. A importação autenticada do HoYoLAB está [em estudo](docs/hoyolab-import.md), ainda sem implementação ou teste autenticado da conta.

## Divisão dos chats

| Chat | Assunto |
|---|---|
| Gacha Advisor — repositório | Organização dos documentos, qualidade das instruções, pesquisa de importação e evolução do projeto |
| Genshin / WuWa / HSR / ZZZ / NTE | Um chat por jogo para builds, times, pulls e atualizações daquela conta |

No Codex, abra os chats de jogo neste mesmo projeto/pasta. No ChatGPT, abra-os dentro de `gacha` para utilizar as fontes enviadas. A organização dos chats não substitui o registro em arquivo: não presuma que outro chat conhece uma conversa anterior. Registre fatos novos no snapshot; preserve conclusões de pesquisa na referência quando forem regras de equipamento relevantes.

Exemplo para iniciar um chat no Codex:

```text
Este chat é dedicado a ZZZ. Leia advisor/gacha-game-advisor.md e as seções de ZZZ
em advisor/account-snapshots.md e advisor/equipment-stat-reference.md.
Use esse contexto para as recomendações. Não presuma dados não informados.
```

Se houver uma aquisição ou correção, peça explicitamente para atualizar a seção do jogo em `advisor/account-snapshots.md`. Evite editar o mesmo arquivo simultaneamente em dois chats.

Esse fluxo segue a [documentação oficial sobre projetos e chats](https://learn.chatgpt.com/docs/projects), consultada em 2026-10-13: chats locais usam arquivos do workspace; chats do Projeto ChatGPT usam as fontes e instruções configuradas nele.

## Estrutura do repositório

```text
gacha-advisor/
├── README.md
├── AGENTS.md
├── .gitignore
├── advisor/
│   ├── gacha-game-advisor.md
│   ├── equipment-stat-reference.md
│   └── account-snapshots.md
├── docs/
│   ├── ROADMAP.md
│   ├── quality-checks.md
│   └── hoyolab-import.md
└── .agents/skills/gacha-advisor/SKILL.md
```

A raiz contém os pontos de entrada. `advisor/` reúne os arquivos usados nas recomendações e na instalação do Projeto; `docs/` reúne manutenção e planejamento. A Skill mantém o caminho necessário à descoberta pelo Codex.

## Responsabilidade dos documentos

| Arquivo | Conteúdo | Uso |
|---|---|---|
| [gacha-game-advisor.md](advisor/gacha-game-advisor.md) | Comportamento, pesquisa e critérios de recomendação; menos de 8.000 caracteres | Instruções do ChatGPT; contexto para recomendações no Codex |
| [equipment-stat-reference.md](advisor/equipment-stat-reference.md) | Regras de stats por jogo/slot, fontes e incertezas | Fonte do Projeto |
| [account-snapshots.md](advisor/account-snapshots.md) | Roster, dupes, equipamentos, times e desconhecidos, separados por jogo | Fonte do Projeto |
| [AGENTS.md](AGENTS.md) | Regras para trabalhar neste repositório | Codex |
| [Skill gacha-advisor](.agents/skills/gacha-advisor/SKILL.md) | Workflow de manutenção e revisão | Codex |
| [ROADMAP.md](docs/ROADMAP.md) | Prioridades propostas | Manutenção |
| [docs/quality-checks.md](docs/quality-checks.md) | Exemplos opcionais para investigar respostas erradas | Manutenção |
| [docs/hoyolab-import.md](docs/hoyolab-import.md) | Evidências, limites e proposta de importação HoYoLAB | Manutenção |

As regras de equipamentos e os snapshots já têm seções por jogo. Mantenha uma única cópia de cada dado; separar fisicamente por jogo só será necessário se esses documentos ficarem difíceis de manter. Recomendações propostas não viram fatos da conta sem confirmação.

## Instalar e atualizar no ChatGPT

1. Abra o Projeto existente **`gacha`**.
2. Em **Configurações do projeto → Instruções**, cole todo o conteúdo de `advisor/gacha-game-advisor.md`.
3. Em **Fontes do projeto**, adicione os arquivos `advisor/equipment-stat-reference.md` e `advisor/account-snapshots.md`. No Projeto, mantenha os nomes dos arquivos sem o prefixo da pasta.
4. Ao atualizar as instruções, cole novamente. Ao atualizar uma fonte, remova a versão anterior da lista de fontes e envie o arquivo atual. Confira que ficou apenas uma cópia de cada: enviar outro arquivo com o mesmo nome pode adicionar uma segunda versão.

Envie somente esses três documentos, nos destinos acima. README, AGENTS, Skill e o conteúdo de `docs/` orientam manutenção e não precisam ser enviados.

**Alterar arquivos ou enviar commits ao GitHub não atualiza o Projeto ChatGPT.** Você escolhe quando atualizar suas cópias. O [checklist](docs/quality-checks.md) é opcional; não exige testes recorrentes nem comparação entre Codex e ChatGPT.

### Limite das instruções e limites das fontes

O teto de **8.000 caracteres aplica-se somente a `advisor/gacha-game-advisor.md`**, porque seu conteúdo é colado no campo **Instruções**. Mantemos esse teto com base no limite informado por Cristian para sua interface; a [documentação oficial de Projetos](https://help.openai.com/en/articles/10169521-projects-in-chatgpt) consultada em **2026-10-14** não publica um número de caracteres para esse campo. Conte todo o arquivo, incluindo espaços e quebras de linha, e mantenha-o abaixo desse teto.

Os arquivos **`account-snapshots.md` e `equipment-stat-reference.md` são fontes anexadas** e podem ultrapassar 8.000 caracteres. A [documentação oficial de uploads](https://help.openai.com/en/articles/8555545-uploading-files-and-audio-to-chatgpt), consultada em **2026-10-14**, informa até **512 MB por documento** e **2 milhões de tokens por arquivo de texto/documento**. Tokens não equivalem a caracteres. O número de arquivos por Projeto depende do plano: Free, 5; Go/Plus, 25; Edu/Pro/Business/Enterprise, 40. Esses são limites de upload, não garantia de que todo o conteúdo será usado em cada resposta; não é necessário encurtar ou dividir nossas fontes apenas por passarem de 8.000 caracteres.

A separação permanece: comportamento nas instruções; regras e dados detalhados nas duas fontes. Limites do produto podem mudar; consulte os links ao enfrentar um erro de upload ou de tamanho. Não use limites da API ou de GPTs personalizados como limites de Projetos ChatGPT.

## Usar a Skill no Codex

A Skill está em `.agents/skills/gacha-advisor/SKILL.md`. Abra o repositório e peça:

```text
Use $gacha-advisor para revisar os documentos e atualizar os dados de ZZZ
que eu informar. Preserve as outras seções e mostre o diff.
```

A Skill orienta manutenção e revisão; não executa automaticamente no Projeto ChatGPT. Veja a [documentação oficial de Skills](https://learn.chatgpt.com/docs/build-skills), consultada em 2026-10-13.

## Manutenção

Atualize somente os campos afetados, com data e origem. Diferencie posse, discussão, hipóteses e dados desconhecidos. Verifique informações de jogo que dependem do patch antes de tratá-las como atuais; consulta recente não certifica uma tabela antiga.

O repositório é público, na branch `main`. Cookies, tokens, exports brutos e configurações pessoais de autenticação não pertencem aos documentos públicos. O histórico Git preserva revisões concluídas; evite guardar patches e diffs temporários na raiz.

Nos inventários de armas de WuWa e NTE, o padrão autorizado é **uma cópia em R1**, salvo exceções explícitas. Registre quantidade/refino junto ao nome somente nas exceções; esse padrão não estabelece posse de armas não listadas nem se estende aos outros jogos.

Mantenha a origem dos dados junto à seção afetada. Handoffs só são úteis para uma investigação interrompida com próximos passos próprios; remova-os quando concluídos. Evite logs de manutenção nas fontes do Projeto: histórico de edições fica no Git.
