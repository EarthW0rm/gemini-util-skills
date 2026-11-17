# Módulo — Refinamento técnico

Objetivo da reunião: quebrar e detalhar itens do backlog até ficarem prontos para seleção numa sprint. Estimar não é o mesmo que deixar pronto. A Definition of Ready é orientação, não portão: sinalize lacunas, não reprove itens.

## O que extrair por item discutido

- identificador e título da story (ou `sem ID` + título dito);
- entendimento consolidado em 1–2 frases (o problema, não a solução);
- critérios de aceitação **adicionados, alterados ou removidos** na reunião, como diff a aplicar no ticket; AC ditos em voz alta e não registrados contam;
- estimativa final, técnica usada (story points, t-shirt, planning poker) e, se houve, a divergência inicial (ex.: "votos 3 e 13");
- decisão de split: novas stories com títulos;
- dependências (time, sistema, API, dado) com responsável;
- spikes ou enablers criados, com pergunta a responder e timebox se dito;
- NFRs e restrições citados (performance, segurança, observabilidade, compatibilidade);
- decisões tomadas pelo PO na ausência de consenso, com o motivo;
- status final do item.

Status do item (vocabulário fechado): `Ready`, `Needs work`, `Blocked`. Se não houve conclusão explícita, use o status mais conservador compatível e registre em "Pontos a confirmar".

## Checagem INVEST

Para cada item, liste **só as letras que falham**, com evidência: I (dependente de outro item), N (detalhe fechado demais), V (valor ao utilizador não explicado), E (time não conseguiu estimar), S (grande demais para a sprint), T (sem forma de testar). Se nenhuma falha aparece na transcrição, escreva `sem falhas evidentes`.

## Análises características

- **Divergência de estimativa**: votos distantes indicam entendimento desigual; registre a causa dita ou crie questão.
- **AC implícitos**: regras faladas que não viraram critério.
- **Itens sem conclusão**: discutidos e abandonados sem status.

## Seção a inserir na ata

```markdown
## Itens refinados

### <ID> — <título>

| Campo | Valor |
|---|---|
| Status | <Ready \| Needs work \| Blocked> |
| Entendimento | <1–2 frases> |
| Estimativa | <valor (técnica); divergência inicial: ... ou não mencionado> |
| Split | <novas stories ou não houve> |
| Dependências | <item — responsável, ou nenhuma mencionada> |
| Spikes/enablers | <pergunta — timebox, ou nenhum> |
| NFRs/restrições | <...ou nenhum mencionado> |
| INVEST | <letras que falham + evidência, ou sem falhas evidentes> |
| Âncora | [hh:mm:ss] |

Critérios de aceitação (diff para o ticket):
- **+** <AC adicionado>
- **~** <AC alterado: antes → depois>
- **−** <AC removido>

## Resumo do refinamento

| Ready | Needs work | Blocked | Divergências de estimativa |
|---|---|---|---|
| <n> | <n> | <n> | <IDs> |
```
