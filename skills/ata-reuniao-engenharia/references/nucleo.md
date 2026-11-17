# Núcleo da ata

Formato fixo para todo tipo de reunião. Mantenha a ordem dos blocos e os títulos exatos, para que atas sucessivas sejam comparáveis. Bloco sem conteúdo: escreva `Nenhum item identificado na transcrição.` — nunca remova o bloco.

## Vocabulário fechado

| Uso | Valores permitidos |
|---|---|
| Status de decisão | `decidida`, `proposta` (sugerida, sem acordo), `descartada` (decidiu-se NÃO fazer), `em aberto` (discutida sem conclusão), `revertida` (substitui decisão anterior) |
| Status de ação | `nova`, `em andamento` (só se dito), `bloqueada` |
| Lacuna | `não mencionado` (não aparece na transcrição) |
| Inferência | sufixo `(inferido)` |
| Confirmação | `não confirmado` (padrão de toda ata gerada), `confirmado` (só se o utilizador do chat confirmar) |
| Link | `[link pendente]` quando o artefato foi citado sem URL |

IDs sequenciais por ata: decisões `D-01`, ações `A-01`, questões `Q-01`, itens RAID `R-01`, pontos a confirmar `C-01`. Módulos usam prefixos próprios definidos neles.

## Regras dos blocos

**Decisão.** Enunciado em voz ativa começando pelo efeito ("Adotar fila dedicada para...", "Não migrar o serviço X neste trimestre"). Um único decisor: se mais de uma pessoa decidiu, registre quem deu a palavra final; se ninguém, `decisor não identificado`. Justificativa curta (1 frase) apenas se dita. Alternativas só se citadas. Decisão arquiteturalmente significativa (muda estrutura, tecnologia, contrato entre sistemas, NFR) gera a ação "Redigir ADR sobre D-xx".

**Ação.** Verbo no infinitivo + entregável verificável ("Abrir ticket para...", "Medir latência p95 de..."). Exatamente um responsável; se a transcrição cita um time, use o time e registre em "Pontos a confirmar" a pessoa responsável. Prazo como data ou marco ("até a próxima review") somente se dito. Coluna Origem aponta o D-xx ou Q-xx que gerou a ação, ou `—`. Sugestão casual ("seria bom olhar isso") não é ação: registre como questão ou ignore.

**Questão em aberto.** Pergunta objetiva, quem pode responder (papel), o que ela bloqueia.

**Ponto a confirmar.** Tudo que o revisor humano precisa validar: lacunas `não mencionado` relevantes, inferências, termos possivelmente transcritos errado, falantes não identificados, conflitos não resolvidos, suposições feitas na etapa 1.

## Template

```markdown
# Ata — <Tipo da reunião>: <tema em até 8 palavras>

> **Rascunho gerado por IA a partir de transcrição — não confirmado.** Validar com: <papel/pessoa>.

| Campo | Valor |
|---|---|
| Tipo | <Refinamento técnico \| Review técnica \| War room \| Levantamento de requisitos \| Genérica> |
| Data | <AAAA-MM-DD ou não mencionado> |
| Horário | <hh:mm–hh:mm (fuso) ou não mencionado> |
| Facilitador | <nome/papel ou não mencionado> |
| Fonte | Transcrição <nome do arquivo ou "colada no chat"> |
| Modo de atribuição | <padrão \| completo \| chatham> |

## Participantes

| Nome | Papel |
|---|---|
| <nome> | <papel ou papel (inferido)> |

Ausentes citados: <lista ou nenhum mencionado>.

## TL;DR

<3 a 5 linhas: decisões-chave, ações críticas e o principal bloqueio. Sem informação nova que não esteja nos blocos abaixo.>

## Pontos a confirmar

| ID | Ponto | Por quê | Quem confirma |
|---|---|---|---|
| C-01 | <...> | <não mencionado / inferido / termo suspeito / conflito> | <papel> |

## Decisões

| ID | Decisão | Status | Decisor | Justificativa | Âncora |
|---|---|---|---|---|---|
| D-01 | <...> | <status> | <nome/papel ou decisor não identificado> | <1 frase ou não mencionado> | [hh:mm:ss] |

Alternativas consideradas (só as citadas): <D-xx: alternativa — motivo do descarte>.

## Ações

| ID | Ação | Responsável | Prazo | Origem | Ticket | Âncora |
|---|---|---|---|---|---|---|
| A-01 | <verbo + entregável> | <nome ou não mencionado> | <data/marco ou não mencionado> | <D-xx/Q-xx/—> | <ID, a criar, ou —> | [hh:mm:ss] |

## Questões em aberto

| ID | Questão | Quem responde | Bloqueia | Âncora |
|---|---|---|---|---|
| Q-01 | <...> | <papel> | <o quê ou nada> | [hh:mm:ss] |

<SEÇÃO DO MÓDULO — inserir aqui, conforme references/<tipo>.md; omitir em reunião genérica>

## RAID

<conforme references/analises.md>

## Artefatos

| Artefato | Tipo | Situação | Link |
|---|---|---|---|
| <nome> | <story, ADR, RFC, ticket, diagrama, doc> | <citado \| a criar \| a atualizar> | <URL ou [link pendente]> |

Artefatos derivados sugeridos: <conforme references/analises.md>.

## Próximos passos

<Próxima reunião/checkpoint se mencionado; senão "não mencionado".>
```
