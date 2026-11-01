# DM-004 — Separar Vaga de Estágio

## Status

Adotada na versão 0.2.

## Contexto

Uma oportunidade pode existir antes de qualquer aluno ser selecionado.

Vários alunos podem se candidatar à mesma oportunidade, enquanto apenas os selecionados poderão gerar vínculos de estágio.

## Decisão

Modelar `Vaga` e `Estagio` como entidades distintas.

```
Concedente
    |
    v
Vaga
    |
    v
Candidatura
    |
    | seleção + formalização
    v
Estagio
```

## Motivos

- uma vaga pode existir sem estágio;
- uma vaga pode receber várias candidaturas;
- candidatura não significa contratação/estágio;
- o estágio possui dados próprios de vigência, formalização, plano, seguro e acompanhamento;
- evita misturar processo seletivo com vínculo efetivo.

## Impacto

A entidade `Vaga` contém as condições da oportunidade.

A entidade `Estagio` contém as condições efetivamente formalizadas para um aluno selecionado.

## Ponto de atenção

Alguns dados podem aparecer nos dois momentos, como carga horária e supervisor.

Quando isso ocorrer, a modelagem deverá decidir se:
- o Estágio referencia os dados da Vaga;
- copia um valor consolidado no momento da formalização; ou
- utiliza objeto próprio para preservar histórico.
