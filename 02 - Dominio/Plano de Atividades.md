# Plano de Atividades — versão 0.2

## Definição

Representa o planejamento das atividades que o aluno realizará durante o estágio.

É a peça que conecta o vínculo profissional à formação acadêmica.

## Atributos iniciais

- id
- objetivo
- descricaoAtividades
- justificativa
- adequacaoPedagogica
- status

## Estados candidatos

- RASCUNHO
- EM_ANALISE
- APROVADO
- REJEITADO
- SUBSTITUIDO

## Relação com Estágio

```
Estagio 1 -------- 0..1 PlanoAtividades
```

Na formalização, o plano pode ainda estar sendo elaborado.

Para o estágio prosseguir, deve existir Plano de Atividades compatível com a formação do aluno.

## Participantes

O plano envolve, no mínimo:
- aluno;
- supervisor;
- orientador.

## Responsabilidade

O Plano não deve ser apenas um anexo.

O sistema deve conseguir representar suas atividades e situação de aprovação.

## Questões abertas

- Pode ser alterado durante o estágio?
- Se alterado, devemos guardar versões anteriores?
- Quem aprova formalmente cada versão?
