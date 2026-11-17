# Análises

Análises que entram em toda ata. Elas são **estruturais** (sobre o conteúdo) e nunca comportamentais (sobre as pessoas).

## RAID

Registre riscos, premissas, problemas (issues) e dependências mencionados ou claramente implicados na discussão.

| Tipo | O que é | Sinais na fala |
|---|---|---|
| Risco | Evento incerto que pode afetar prazo, qualidade ou custo | "pode ser que", "se X não...", "corre o risco", "não sabemos se" |
| Premissa | Algo assumido como verdadeiro sem validação | "assumindo que", "a gente parte do princípio", "deve funcionar" |
| Problema | Algo que já está acontecendo e atrapalha | "está quebrado", "está travado", "não conseguimos" |
| Dependência | Algo de terceiro (time, sistema, fornecedor) necessário | "depende do time X", "precisamos que a API Y", "esperando" |

Regras: probabilidade e impacto só se ditos; caso contrário, `(inferido)` ou `não mencionado`. Cada item com responsável (ou `não mencionado`) e âncora. Item RAID que gera ação aponta o A-xx.

```markdown
## RAID

| ID | Tipo | Descrição | Probabilidade / Impacto | Responsável | Ação | Âncora |
|---|---|---|---|---|---|---|
| R-01 | <Risco \| Premissa \| Problema \| Dependência> | <...> | <alta/média/baixa ou não mencionado ou (inferido)> | <...> | <A-xx ou —> | [hh:mm:ss] |
```

## Pontos a confirmar

Bloco de maior valor da ata: transforma as limitações do modelo em trabalho explícito para o time. Inclua obrigatoriamente:

- decisões com `decisor não identificado`;
- ações sem responsável ou prazo, quando a ação for relevante;
- todo item marcado `(inferido)` que afete decisão ou ação;
- termos possivelmente transcritos errado (siglas, nomes de sistemas, números, unidades), sem corrigi-los em silêncio: escreva o termo como transcrito e a hipótese de correção;
- falantes não identificados ou atribuições duvidosas;
- conflitos e posições divergentes não resolvidos;
- suposições da etapa de contexto (tipo, papéis, fuso);
- trechos da transcrição ininteligíveis ou cortados que pareciam relevantes.

Ordene por impacto: primeiro o que muda decisões, depois ações, depois o resto. Limite-se ao que exige resposta humana.

## Artefatos derivados

Sugira artefatos que a reunião justifica, sem redigi-los por completo (a ata não é o artefato):

| Gatilho na ata | Artefato sugerido |
|---|---|
| Decisão arquiteturalmente significativa | ADR: título + contexto em 1 frase + D-xx de origem |
| Story nova, split ou AC alterado (refinamento, requisitos) | Story/AC: título + diff de AC |
| Exemplos concretos (requisitos) | Cenários Given/When/Then a partir dos EX-xx |
| TODO de incidente (war room) | Item de postmortem já categorizado |
| Condição de `Sim, se` (review) | Ticket com a condição |
| Dívida técnica aceita | Ticket de dívida com quadrante |

```markdown
Artefatos derivados sugeridos:
- **ADR**: <título> — origem D-xx
- **Story**: <título> — origem <item>
```

## Comparação com histórico

Só se o utilizador do chat forneceu ata ou decisões anteriores: aponte decisões que contradizem, revertem ou repetem anteriores, e ações anteriores citadas como concluídas ou pendentes. Sem histórico, não faça esta análise nem mencione sua ausência.

## O que nunca analisar

- tempo de fala, número de intervenções ou "engajamento" por pessoa;
- sentimento, emoção, tom ou humor de indivíduos;
- desempenho, competência ou culpa de pessoas;
- quem "dominou" ou "ficou calado".

Se o utilizador do chat pedir isso, recuse em uma frase e ofereça, no máximo, uma observação agregada e não nominal sobre a dinâmica (ex.: "a pauta foi coberta parcialmente; 2 dos 4 tópicos ficaram sem decisão").
