# Privacidade e atribuição

## Modos de atribuição

| Modo | Quem é nomeado | Discussão | Quando usar |
|---|---|---|---|
| `padrão` | Só decisores e responsáveis de ações | Sem atribuição ("foi levantada a preocupação de que..."); em requisitos, fonte por papel | Default de toda reunião |
| `completo` | Cada posição, decisão e ação | Atribuída nominalmente | Reuniões formais com registro de posição (rodada de aprovação de review, comitês) |
| `chatham` | Ninguém, nem decisores | Sem atribuição; responsável de ação por papel ou time | Discussões sensíveis, retrospectivas, temas organizacionais |

Em qualquer modo:

- War room: linguagem descritiva e sem culpa; nomes só em papéis do incidente, decisões e ações.
- Dissenso registrado como posição ("houve posição contrária, por <motivo>"), nunca como característica da pessoa.
- Na dúvida sobre quem falou, escreva `falante não identificado` e crie ponto a confirmar; nunca adivinhe.

## Dados que nunca entram na ata

Substitua por placeholder e avise no fim da ata:

| Dado dito na reunião | Tratamento |
|---|---|
| Senha, token, chave de API, connection string, segredo | `[CREDENCIAL REMOVIDA]` + aviso: "Credencial exposta na reunião — recomenda-se rotacioná-la." |
| Dados pessoais de clientes ou usuários finais (nome, CPF, e-mail, telefone, endereço, dados de pagamento) | `[DADO DE CLIENTE REMOVIDO]`; mantenha só o necessário ao contexto técnico (ex.: "um cliente do plano X") |
| Saúde, afastamentos, gravidez, religião, opinião política, vida sexual, origem racial, filiação sindical | Omita; se relevante para planejamento, generalize ("ausência prevista de um membro do time") |
| Questões disciplinares, desempenho individual, conflitos pessoais | Omita; não pertencem à ata técnica |
| URLs internas com tokens ou parâmetros sensíveis | Mantenha o domínio, remova parâmetros |

## Princípios LGPD aplicados

- **Finalidade e necessidade**: a ata registra só o necessário para decisões, ações e rastreabilidade técnica.
- **Transparência**: o selo "Rascunho gerado por IA a partir de transcrição" fica no cabeçalho.
- **Minimização**: prefira papel a nome quando o nome não traz responsabilidade.
- **Segurança**: dados removidos não reaparecem em nenhum bloco, inclusive em citações e âncoras.

Ao final da ata, se algo foi removido, inclua:

```markdown
> Dados removidos desta ata: <n> credenciais, <n> dados de cliente, <n> menções pessoais. Recomenda-se não reter a transcrição bruta além do necessário.
```
