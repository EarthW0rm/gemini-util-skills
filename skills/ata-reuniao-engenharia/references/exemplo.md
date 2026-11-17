# Exemplo (few-shot)

Use este exemplo como referência de **formato, tom e rigor**, não de conteúdo. A transcrição é fictícia e curta; atas reais terão mais itens.

## Entrada

Pedido: "Gera a ata do refinamento. Modo padrão. Ana é PO, Bruno tech lead, Carla e Diego devs."

```
[00:00:05] Ana: Bom dia. Hoje é a PAG-412, estorno parcial no checkout.
[00:01:10] Bruno: Antes, uma coisa: a API do gateway aceita estorno parcial ou só total?
[00:01:25] Ana: Não sei, preciso confirmar com o time de pagamentos.
[00:02:40] Carla: Se aceitar, o fluxo é tranquilo. Eu chutaria 5.
[00:02:45] Diego: Eu dei 13, porque tem a conciliação com o ERP.
[00:03:30] Bruno: Bom ponto. Vamos separar: PAG-412 só o estorno, e uma story nova pra conciliação.
[00:03:50] Ana: Fechado. Ah, e o estorno não pode passar do valor original, óbvio.
[00:04:20] Bruno: Revotando o estorno sozinho... deu 5 pra todo mundo.
[00:05:00] Diego: Usa o token sk_live_9f3a pra testar no sandbox.
[00:05:30] Bruno: Kafka pra notificar a conciliação a gente não vai usar agora, fica no SQS mesmo.
[00:06:10] Carla: Eu abro a story da conciliação.
[00:06:40] Ana: Mas a PAG-412 fica bloqueada até eu saber do gateway.
```

## Saída

```markdown
# Ata — Refinamento técnico: estorno parcial no checkout

> **Rascunho gerado por IA a partir de transcrição — não confirmado.** Validar com: Ana (PO).

| Campo | Valor |
|---|---|
| Tipo | Refinamento técnico |
| Data | não mencionado |
| Horário | não mencionado |
| Facilitador | Ana (PO) (inferido) |
| Fonte | Transcrição colada no chat |
| Modo de atribuição | padrão |

## Participantes

| Nome | Papel |
|---|---|
| Ana | PO |
| Bruno | Tech Lead |
| Carla | Dev |
| Diego | Dev |

Ausentes citados: nenhum mencionado.

## TL;DR

- PAG-412 dividida: estorno parcial (5 pontos) e nova story de conciliação com o ERP.
- PAG-412 bloqueada até confirmar se o gateway aceita estorno parcial.
- Notificação da conciliação segue em SQS; Kafka descartado por ora.

## Pontos a confirmar

| ID | Ponto | Por quê | Quem confirma |
|---|---|---|---|
| C-01 | Gateway aceita estorno parcial? | Bloqueia PAG-412 (Q-01) | Ana (PO) |
| C-02 | Prazo para a resposta do time de pagamentos | não mencionado | Ana (PO) |
| C-03 | Credencial dita na reunião deve ser rotacionada | Credencial exposta | Bruno (Tech Lead) |
| C-04 | Decisor do descarte do Kafka | Dito por Bruno sem confirmação do grupo (inferido) | Bruno (Tech Lead) |

## Decisões

| ID | Decisão | Status | Decisor | Justificativa | Âncora |
|---|---|---|---|---|---|
| D-01 | Separar a PAG-412 em estorno parcial e nova story de conciliação com o ERP | decidida | Bruno | Conciliação elevava a estimativa | [00:03:30] |
| D-02 | Usar Kafka para notificar a conciliação (mantido SQS por ora) | descartada | Bruno | não mencionado | [00:05:30] |

Alternativas consideradas: D-02: Kafka — descartado "agora", motivo não mencionado.

## Ações

| ID | Ação | Responsável | Prazo | Origem | Ticket | Âncora |
|---|---|---|---|---|---|---|
| A-01 | Confirmar com o time de pagamentos se o gateway aceita estorno parcial | Ana | não mencionado | Q-01 | — | [00:01:25] |
| A-02 | Abrir story de conciliação do estorno com o ERP | Carla | não mencionado | D-01 | a criar | [00:06:10] |
| A-03 | Rotacionar a credencial exposta na reunião | não mencionado | não mencionado | — | — | [00:05:00] |

## Questões em aberto

| ID | Questão | Quem responde | Bloqueia | Âncora |
|---|---|---|---|---|
| Q-01 | A API do gateway aceita estorno parcial ou só total? | Time de pagamentos | PAG-412 | [00:01:10] |

## Itens refinados

### PAG-412 — Estorno parcial no checkout

| Campo | Valor |
|---|---|
| Status | Blocked |
| Entendimento | Permitir estorno de parte do valor de uma compra no checkout. |
| Estimativa | 5 (votação); divergência inicial: 5 e 13 |
| Split | Nova story: conciliação do estorno com o ERP |
| Dependências | Confirmação do gateway — Ana |
| Spikes/enablers | nenhum |
| NFRs/restrições | nenhum mencionado |
| INVEST | I: depende da capacidade do gateway [00:01:10] |
| Âncora | [00:00:05] |

Critérios de aceitação (diff para o ticket):
- **+** O valor estornado não pode exceder o valor original da compra. [00:03:50]

## Resumo do refinamento

| Ready | Needs work | Blocked | Divergências de estimativa |
|---|---|---|---|
| 0 | 0 | 1 | PAG-412 (5 vs 13: conciliação com ERP) |

## RAID

| ID | Tipo | Descrição | Probabilidade / Impacto | Responsável | Ação | Âncora |
|---|---|---|---|---|---|---|
| R-01 | Dependência | Capacidade de estorno parcial do gateway | não mencionado | Ana | A-01 | [00:01:10] |
| R-02 | Risco | Se o gateway só aceitar estorno total, o escopo da PAG-412 muda | (inferido) | não mencionado | A-01 | [00:02:40] |

## Artefatos

| Artefato | Tipo | Situação | Link |
|---|---|---|---|
| PAG-412 | story | a atualizar | [link pendente] |
| Conciliação do estorno com ERP | story | a criar | [link pendente] |

Artefatos derivados sugeridos:
- **Story**: Conciliação do estorno parcial com o ERP — origem D-01

## Próximos passos

não mencionado

> Dados removidos desta ata: 1 credencial. Recomenda-se não reter a transcrição bruta além do necessário.
```

Observe no exemplo: o token não aparece; "fica no SQS" virou decisão `descartada` sobre Kafka; "eu chutaria 5" não virou decisão; o AC dito de passagem entrou no diff; a ação sem dono ficou `não mencionado` e foi para "Pontos a confirmar".
