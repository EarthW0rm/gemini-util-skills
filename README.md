# gemini-util-skills

Coleção de skills de propósito diverso para uso no Chat do Google Gemini (Gemini Enterprise), com o objetivo de facilitar e padronizar tarefas recorrentes.

## Estrutura

Cada skill fica em sua própria pasta dentro de `skills/`:

```
skills/
  <nome-da-skill>/
    SKILL.md       # obrigatório: frontmatter (name, description) + instruções
    references/    # opcional: documentos Markdown carregados sob demanda
    assets/        # opcional: templates e dados
```

As skills não contêm arquivos de código: o Gemini Chat recusa carregar skills com scripts. Quando uma skill precisa de uma operação determinística, o script é apresentado ao utilizador para execução no próprio terminal.

## Como usar

1. Baixe o ZIP da skill (ou compacte a pasta `skills/<nome-da-skill>/`, mantendo-a como única pasta de topo).
2. No Gemini Enterprise: Skills → Upload skill → selecione o ZIP.
3. No chat, acione a skill por `@<nome-da-skill>`, `/<nome-da-skill>` ou por um pedido que corresponda à sua descrição.

## Skills disponíveis

| Skill | Descrição |
|---|---|
| [`ata-reuniao-engenharia`](skills/ata-reuniao-engenharia/) | Gera ata em PT-BR a partir da transcrição de reuniões de engenharia de software (refinamento técnico, review técnica, war room e levantamento de requisitos), com decisões, ações, questões em aberto, RAID, pontos a confirmar e artefatos derivados, ancorados na transcrição. |
