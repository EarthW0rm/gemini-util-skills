# Módulo — Levantamento de requisitos

Cobre sessões de descoberta, workshops de requisitos e entrevistas com produto e stakeholders. Todo resultado de sessão de elicitação nasce **não confirmado**: a confirmação é uma etapa posterior, e silêncio dos stakeholders não é confirmação.

## Regras específicas

1. Cada item recebe ID, tipo, enunciado singular (uma necessidade por item), fonte e status `não confirmado`.
2. **Fonte** = papel + âncora + citação curta (≤ 15 palavras). Em modo `padrão`, use o papel, não o nome.
3. **Conflitos não são resolvidos por você.** Registre as posições, a natureza do conflito e escale ao decisor (PO/PM), com as opções.
4. **Termos vagos viram pergunta**: "rápido", "normalmente", "muitos", "fácil", "em tempo real", "seguro" sem métrica.
5. **Exemplos concretos são preservados** literalmente: viram cenários Given/When/Then. Exemplo sem resultado claro ("então...") é pergunta, não exemplo.
6. Ideia de solução dita por produto é registrada como `ideia de solução`, não como requisito.

## Taxonomia (vocabulário fechado)

| Tipo | Prefixo | Definição |
|---|---|---|
| Objetivo de negócio | OBJ | Resultado mensurável buscado |
| Requisito funcional | RF | Comportamento que o sistema deve ter |
| Requisito não funcional | RNF | Atributo de qualidade (desempenho, segurança, disponibilidade...) |
| Regra de negócio | RN | Política ou norma do domínio, independente do sistema |
| Restrição | RES | Limite imposto (tecnologia, prazo, legal, orçamento) |
| Premissa | PRE | Algo tido como verdadeiro sem validação |
| Fora de escopo | FE | Explicitamente excluído |
| Exemplo/cenário | EX | Caso concreto com entrada e resultado |
| Ideia de solução | SOL | Proposta de como fazer |
| Termo de glossário | GL | Termo do domínio e seu significado |
| Conflito | CF | Posições incompatíveis entre stakeholders |

Perguntas (TBD) vão para "Questões em aberto" do núcleo; riscos para o RAID.

## Análises características

- **Ambiguidades**: termos vagos e enunciados com mais de uma leitura.
- **Premissas não validadas**: quem pode validar.
- **Scope creep**: item novo sem decisão explícita de inclusão.
- **Prontidão para spec**: contagem de questões e conflitos abertos; alta contagem indica que o tema ainda não está pronto para especificação.

## Seção a inserir na ata

```markdown
## Requisitos levantados

> Todos os itens estão **não confirmados** até validação do <PO/PM>.

| ID | Tipo | Enunciado | Fonte (papel — âncora — citação) | Status |
|---|---|---|---|---|
| RF-01 | Requisito funcional | <...> | <papel> — [hh:mm:ss] — "<...>" | não confirmado |

### Exemplos para cenários

| ID | Dado | Quando | Então | Origem |
|---|---|---|---|---|
| EX-01 | <...> | <...> | <...> | RN-xx/RF-xx |

### Conflitos

| ID | Tema | Posição A (papel) | Posição B (papel) | Natureza | Escalar para | Âncora |
|---|---|---|---|---|---|---|
| CF-01 | <...> | <...> | <...> | <termo \| prioridade \| regra \| escopo> | <PO/PM> | [hh:mm:ss] |

### Ambiguidades

- <termo/enunciado> — por que é ambíguo — pergunta proposta

### Glossário

| Termo | Significado dito | Âncora |
|---|---|---|

### Prontidão para spec

| Questões abertas | Conflitos | Premissas não validadas | Avaliação |
|---|---|---|---|
| <n> | <n> | <n> | <pronto para spec \| precisa de nova sessão> (inferido) |
```
