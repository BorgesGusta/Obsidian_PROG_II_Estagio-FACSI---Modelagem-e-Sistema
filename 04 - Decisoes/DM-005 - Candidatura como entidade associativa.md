# DM-005 — Candidatura como entidade associativa

## Status

Adotada e revisada na versão 0.2.

## Contexto

Aluno e Vaga possuem relação muitos-para-muitos quando há processo de seleção.

Essa relação possui informações próprias.

## Decisão

Introduzir a entidade `Candidatura`:

```
Aluno 1 ---- 0..* Candidatura 0..* ---- 1 Vaga
```

## Revisão importante

Candidatura **não é pré-requisito universal para Estágio**.

O regulamento da FACSI prevê que o discente pode encontrar oportunidade por contato direto com a concedente ou por meio da coordenação de estágio.

Também permite estágio por atividades em projetos/programas de extensão, pesquisa e Empresa Júnior.

Portanto:

```
Candidatura 0..1 ---- 0..1 Estagio
```

Uma candidatura pode originar no máximo um estágio e um estágio pode ter zero ou uma candidatura de origem.

## Consequência

O modelo não deve obrigar todo Estágio a possuir Candidatura.

Também será necessário permitir que Estágio tenha origem sem Vaga cadastrada.

## Relação com Orientação a Objetos

Candidatura continua sendo uma **classe associativa**, mas participa apenas do fluxo de seleção quando esse fluxo realmente existe.
