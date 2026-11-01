# Plano de Atividades — versão 0.3

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

## Evolução do plano

A Lei nº 11.788/2008 determina que o Plano de Atividades seja incorporado ao Termo de Compromisso por meio de **aditivos**, à medida que o desempenho do estudante é avaliado progressivamente.

### Consequência de modelagem

O plano pode mudar ao longo do estágio e o sistema deve preservar histórico dessas alterações.

Na v0.3, mantemos `PlanoAtividades` como entidade principal e registramos como requisito futuro o versionamento/aditivos, sem ainda criar uma classe extra.

## Responsabilidade

O Plano não deve ser apenas um anexo.

O sistema deve conseguir representar suas atividades, situação de aprovação e evolução ao longo do vínculo.

## Questão ainda aberta

- Quem aprova formalmente cada alteração no fluxo da FACSI?
