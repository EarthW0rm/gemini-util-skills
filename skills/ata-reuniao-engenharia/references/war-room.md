# Módulo — War room (incidente)

A ata de war room é um **documento de estado** do incidente, não um resumo da conversa. Ela alimenta o postmortem, mas não é o postmortem.

## Regras específicas

1. **Não conclua causa raiz.** Registre hipóteses com status e evidência. Causas são plurais e definidas no postmortem.
2. **Linguagem sem culpa.** Descreva fatos ("X executou Y às 14:32"). Proibido: "deveria ter", "erro de", "falha de <pessoa>", contrafactuais.
3. **Timeline não é transcrição.** Registre eventos (decisão, ação, observação, hipótese, comunicação), não falas. Deduplique eventos repetidos em status updates.
4. **Separe o horário em que algo foi dito do horário em que aconteceu.** "O deploy foi às 13h" dito às 14:10 gera evento às 13:00 com nota `relatado às 14:10`.
5. **Horário absoluto.** Converta offsets da transcrição para hora do relógio se houver âncora (ex.: início da chamada). Use um único fuso, preferencialmente UTC, e declare-o. Sem âncora, marque `horário aproximado`.
6. **Incerteza explícita.** Marque `confirmado`, `relatado` ou `suposto` em eventos e impacto.

## O que extrair

- severidade (SEV/P) e status atual: `ativo`, `mitigado`, `resolvido`;
- papéis: Incident Commander, operações, comunicação, escriba; handoffs com horário;
- impacto: quem/o quê foi afetado, escala, SLO/SLA, medido ou estimado;
- marcos em ordem cronológica: Detectado, Reconhecido, Mitigado, Resolvido; fonte da detecção (alerta, cliente, time interno);
- hipóteses: testada, confirmada, descartada, com evidência;
- mitigações e rollbacks, com quem decidiu;
- divergências do normal a desfazer (flags, configs, escalas manuais, bypasses);
- comunicações enviadas (canal, público, horário) e próximo update prometido;
- critérios de saída e próximo checkpoint;
- TODOs para o postmortem.

## Seção a inserir na ata

```markdown
## Estado do incidente

| Campo | Valor |
|---|---|
| Severidade | <SEV-x ou não mencionado> |
| Status | <ativo \| mitigado \| resolvido> |
| Fuso da timeline | <UTC ou fuso declarado> |
| Incident Commander | <nome/papel; handoffs: hh:mm → nome> |
| Comunicação / Escriba | <...> |
| Impacto | <descrição — escala — medido \| estimado> |
| Fonte da detecção | <alerta \| cliente \| interno \| não mencionado> |
| Próximo checkpoint | <hh:mm ou não mencionado> |

### Marcos

| Marco | Horário | Certeza |
|---|---|---|
| Detectado | <hh:mm> | <confirmado \| relatado \| aproximado> |
| Reconhecido | | |
| Mitigado | | |
| Resolvido | | |

### Timeline

| Horário | Tipo | Evento | Quem | Certeza |
|---|---|---|---|---|
| <hh:mm> | <decisão \| ação \| observação \| hipótese \| comunicação> | <fato> | <papel/nome> | <...> |

### Hipóteses

| ID | Hipótese | Status | Evidência | Âncora |
|---|---|---|---|---|
| H-01 | <...> | <em teste \| confirmada \| descartada> | <...> | [hh:mm:ss] |

### Mitigações e divergências a reverter

| Mitigação/divergência | Decidida por | Reverter? | Responsável pela reversão |
|---|---|---|---|

### Comunicações

| Horário | Canal | Público | Conteúdo resumido |
|---|---|---|---|

### Critérios de saída

- [ ] <critério> (TODO \| DONE)

### TODOs para o postmortem

| ID | TODO | Categoria | Responsável |
|---|---|---|---|
| P-01 | <...> | <prevenir \| detectar \| mitigar \| reparar \| investigar \| processo> | <nome ou não mencionado> |
```
