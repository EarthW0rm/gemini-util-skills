---
name: ata-reuniao-engenharia
description: Gera ata de reunião de engenharia de software em PT-BR a partir de transcrição colada ou anexada (.txt, .docx, .md), para refinamento técnico, review técnica (design review, RFC, arquitetura), war room de incidente e levantamento de requisitos com produto. Registra decisões com status e decisor, ações com responsável e prazo, questões em aberto, RAID, pontos a confirmar e artefatos derivados (ADR, histórias, TODOs de postmortem), sempre ancorados em trechos da transcrição e sem inventar dados. Use quando o utilizador pedir "gerar ata", "ata da reunião", "resumir a transcrição da reunião", "ata do refinamento", "registro do war room", "ata da review técnica" ou "ata do levantamento de requisitos". Não use para redigir postmortem completo, spec ou PRD, resumir documentos que não sejam reunião, nem para avaliar desempenho, engajamento ou sentimento de participantes.
metadata:
  version: "1.0.0"
  language: pt-BR
---

# Ata de reunião de engenharia

Transforme a transcrição de uma reunião de engenharia de software numa ata em PT-BR que registra **o que foi decidido e feito, não o que foi dito**. A ata é um rascunho para revisão humana: nunca a apresente como registro final.

## Regras invioláveis

1. **Não invente.** Responsável, prazo, decisor, justificativa, número ou causa que não aparece na transcrição vira `não mencionado`. Inferência sua é marcada `(inferido)`.
2. **Ancore tudo.** Cada decisão, ação, questão e item de módulo leva a âncora `[hh:mm:ss]` ou, sem timestamps, uma citação curta entre aspas.
3. **Extraia antes de redigir.** Siga as etapas abaixo na ordem; não escreva a ata numa passada única.
4. **Omissão é o erro mais comum.** Percorra a transcrição inteira, inclusive o meio. Decisões negativas ("não vamos fazer X") e tentativas ("acho que vamos de X") são decisões e precisam aparecer com o status correto.
5. **Não avalie pessoas.** Nada de tempo de fala, sentimento, engajamento ou desempenho individual.
6. **Proteja dados.** Aplique `references/privacidade-atribuicao.md` antes de entregar.
7. **Use só o vocabulário de status** definido em `references/nucleo.md`.

## Fluxo

### 1. Coletar contexto

Confirme que há uma transcrição (texto colado ou arquivo anexado). Sem transcrição, peça-a e pare.

Em uma única mensagem, pergunte apenas o que não estiver claro no pedido ou na transcrição:

- tipo da reunião (refinamento técnico, review técnica, war room, levantamento de requisitos ou outra);
- participantes e papéis (PO, PM, Tech Lead, IC, QA, Dev...);
- glossário de siglas, sistemas e nomes próprios do time;
- modo de atribuição: `padrão`, `completo` ou `chatham` (ver `references/privacidade-atribuicao.md`);
- data, horário e fuso, se não constarem na transcrição;
- ata anterior ou decisões anteriores (opcional; sem elas, não compare com o histórico).

Se o utilizador do chat pedir para seguir sem responder, use: tipo classificado por você, modo `padrão`, papéis inferidos marcados `(inferido)`, e registre cada suposição em "Pontos a confirmar".

### 2. Classificar a reunião e carregar o módulo

Classifique pelo conteúdo e leia o módulo correspondente:

| Sinais na transcrição | Tipo | Módulo |
|---|---|---|
| Stories, estimativa, pontos, critérios de aceitação, split, "pronto para a sprint" | Refinamento técnico | `references/refinamento.md` |
| Design doc, RFC, proposta de arquitetura, trade-offs, aprovação | Review técnica | `references/review-tecnica.md` |
| Incidente, alerta, impacto em produção, rollback, mitigação, severidade | War room | `references/war-room.md` |
| Necessidades do negócio, regras, cenários, escopo, stakeholders de produto | Levantamento de requisitos | `references/levantamento-requisitos.md` |
| Nenhum dos anteriores ou mistura sem predominância | Genérica | só o núcleo |

Leia também, sempre: `references/nucleo.md`, `references/extracao-verificacao.md`, `references/analises.md`, `references/privacidade-atribuicao.md` e `references/exemplo.md`.

Se a reunião mistura tipos (ex.: refinamento que vira discussão de arquitetura), use o módulo predominante e registre os itens do outro tipo no núcleo.

### 3. Extrair

Siga o protocolo de `references/extracao-verificacao.md`: percorra a transcrição em blocos e monte listas brutas internas de decisões, ações, questões, itens RAID e itens do módulo, cada uma com âncora. Não mostre as listas brutas ao utilizador do chat, a menos que ele peça.

### 4. Redigir

Monte a ata no formato exato de `references/nucleo.md`, inserindo a seção do módulo no lugar indicado. Use `references/exemplo.md` como referência de formato e tom. Escreva em voz ativa, impessoal, sem adjetivos de juízo e sem opiniões.

### 5. Verificar

Faça **uma única** rodada do checklist de `references/extracao-verificacao.md`. Corrija o que falhar. Não reescreva a ata em várias rodadas: refinamentos sucessivos aumentam erros.

### 6. Entregar

Entregue a ata em Markdown, com o selo de rascunho no cabeçalho e "Pontos a confirmar" logo após o TL;DR. Depois da ata, uma linha: quem deve validar o rascunho (facilitador da reunião ou o papel indicado) e que itens marcados `não mencionado` ou `(inferido)` exigem resposta.

Se o utilizador do chat pedir ajustes, altere só o pedido e mantenha as âncoras.
