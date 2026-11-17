# Protocolo de extração e verificação

Modelos de linguagem erram mais por **omissão** (tópicos e detalhes que somem, sobretudo no meio de transcrições longas) do que por invenção, e tendem a soar mais decididos do que a reunião foi. Este protocolo compensa as duas falhas.

## Preparar a transcrição

1. Identifique o formato: com timestamps (`[00:12:31]`, `00:12:31`, `12:31`), com falantes (`Nome:`), ou texto corrido.
2. Sem timestamps: use como âncora uma citação curta (≤ 12 palavras) entre aspas.
3. Sem falantes identificados: não atribua falas; trate atribuição como `falante não identificado` e registre em "Pontos a confirmar".
4. Aplique o glossário fornecido para reconhecer termos; não corrija a transcrição: anote suspeitas.
5. Atenção a code-switching PT/EN e a erros típicos de transcrição em siglas, nomes de sistemas, números e unidades.

## Extrair por blocos

Divida a transcrição em blocos sequenciais de tamanho equivalente a cerca de 10 minutos de reunião (ou cerca de 4.000 palavras), sem cortar falas no meio. Para **cada bloco**, nesta ordem, liste internamente:

1. **Decisões**: inclusive negativas ("não vamos", "descartamos", "fica para depois") e tentativas ("acho que vamos de", "provavelmente"). Tentativa sem acordo = `proposta`. Marque o trecho exato.
2. **Ações**: compromisso explícito de alguém fazer algo ("eu vejo isso", "fulano fica com", "vou abrir o ticket"). Sugestão sem compromisso não é ação.
3. **Questões**: perguntas sem resposta na própria reunião.
4. **Itens RAID** (ver `analises.md`).
5. **Itens do módulo** do tipo de reunião.

Depois de todos os blocos:

6. **Deduplicar**: o mesmo item citado em vários blocos vira um só, com a âncora da formulação mais completa; a decisão mais recente prevalece e a anterior vira `revertida` se mudou.
7. **Enriquecer** cada item usando apenas os trechos ancorados dele: responsável, prazo, justificativa. O que não estiver no trecho ou na vizinhança imediata = `não mencionado`.
8. **Reler o meio**: releia os blocos do meio da transcrição procurando decisões e ações não capturadas.

## Verificação única

Faça **uma** passada com este checklist e corrija o que falhar. Não refine a ata em várias rodadas.

- [ ] Toda decisão, ação, questão e item de módulo tem âncora.
- [ ] Todo responsável, prazo e decisor aparece literalmente na transcrição; caso contrário está `não mencionado` ou `(inferido)`.
- [ ] Decisões negativas e tentativas estão presentes com status `descartada` ou `proposta`.
- [ ] Nenhuma sugestão casual virou ação; nenhuma proposta virou `decidida`.
- [ ] Cada bloco da transcrição contribuiu ou foi conscientemente vazio (tópicos do meio não sumiram).
- [ ] O TL;DR não contém informação ausente dos blocos.
- [ ] Vocabulário de status é só o de `nucleo.md` e do módulo.
- [ ] Nenhum dado proibido de `privacidade-atribuicao.md` aparece, inclusive em citações.
- [ ] Atribuição respeita o modo escolhido.
- [ ] Nenhuma análise de pessoa (tempo de fala, sentimento, desempenho).
- [ ] War room: nenhuma causa raiz afirmada; horários em fuso único.
- [ ] Requisitos: todos os itens `não confirmado`; conflitos escalados, não resolvidos.
- [ ] Todo item `não mencionado` ou `(inferido)` relevante está em "Pontos a confirmar".

## Transcrição muito longa ou incompleta

- Se a transcrição parecer cortada (termina no meio de frase, ou o utilizador do chat indicar), registre em "Pontos a confirmar": "Transcrição possivelmente incompleta após [hh:mm:ss]".
- Se houver trechos ininteligíveis relevantes, registre-os em "Pontos a confirmar" com a âncora.
