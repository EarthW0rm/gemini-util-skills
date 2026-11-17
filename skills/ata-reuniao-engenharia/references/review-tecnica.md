# Módulo — Review técnica

Cobre design review, RFC review, review de arquitetura e de solução. Objetivo: decidir se uma proposta segue, segue com condições ou volta para ajuste, registrando riscos e trade-offs.

## O que extrair

- artefato revisado (título, autor, versão ou data, link);
- escopo: goals e non-goals citados;
- objeções e preocupações, com quem as levantou (respeitando o modo de atribuição);
- alternativas consideradas e motivo de descarte; ideias abandonadas;
- trade-offs no formato "ganha X às custas de Y, afetando o atributo Z";
- NFRs e preocupações transversais: performance, escalabilidade, disponibilidade, segurança, privacidade, observabilidade, custo, rollout e rollback, migração de dados;
- **posição de cada approver** na rodada final;
- conselho (advice) recebido, separado de aprovação;
- dívida técnica aceita ou criada;
- candidatos a ADR.

## Posição de approver

Vocabulário fechado: `Sim`, `Sim, se` (aprovação condicional: registre a condição), `Ainda não` (registre o que falta), `Não declarado` (approver presente sem posição explícita).

Cada condição de `Sim, se` vira ação no núcleo, com responsável. Se a reunião terminou sem rodada de posição, registre `Não declarado` para os approvers e crie ponto a confirmar: "Review sem decisão explícita de aprovação".

Advice ≠ approval: "acho que deveriam considerar X" é conselho. Registre em Conselhos, não como posição.

## Classificação de riscos (ATAM)

| Classe | Significado |
|---|---|
| Risco | Decisão ou lacuna que pode comprometer um atributo de qualidade |
| Não risco | Decisão analisada e considerada segura (registre só se discutida) |
| Ponto de sensibilidade | Parâmetro que afeta fortemente um atributo (ex.: tamanho do pool) |
| Ponto de trade-off | Parâmetro que afeta dois ou mais atributos em sentidos opostos |

Severidade: `alto` ou `médio` somente se dita ou claramente consensual; senão `(inferido)`.

## Dívida técnica

Classifique no quadrante de Fowler apenas com evidência na fala: `prudente-deliberada` ("sabemos, vamos pagar depois"), `imprudente-deliberada` ("não temos tempo para design"), `prudente-inadvertida` ("agora sabemos como deveria ser"), `imprudente-inadvertida`. Registre a decisão: pagar (com ação) ou aceitar.

## Seção a inserir na ata

```markdown
## Review técnica

| Campo | Valor |
|---|---|
| Artefato | <título — autor — versão/data — link ou [link pendente]> |
| Resultado | <Aprovado \| Aprovado com condições \| Não aprovado \| Sem decisão> |
| Goals / non-goals | <citados ou não mencionado> |

### Posição dos approvers

| Approver | Posição | Condição ou o que falta | Âncora |
|---|---|---|---|
| <nome/papel> | <Sim \| Sim, se \| Ainda não \| Não declarado> | <...> | [hh:mm:ss] |

### Riscos e trade-offs

| ID | Classe | Descrição | Atributo afetado | Severidade | Âncora |
|---|---|---|---|---|---|
| T-01 | <Risco \| Ponto de sensibilidade \| Ponto de trade-off \| Não risco> | <...> | <performance, segurança...> | <alto \| médio \| (inferido)> | [hh:mm:ss] |

### Alternativas e ideias abandonadas

- <alternativa> — <motivo do descarte> [hh:mm:ss]

### Conselhos recebidos

- <conselho> — <papel> [hh:mm:ss]

### Dívida técnica

| Descrição | Quadrante | Decisão | Âncora |
|---|---|---|---|

### Candidatos a ADR

- <título do ADR> — origem D-xx — contexto em 1 frase
```
