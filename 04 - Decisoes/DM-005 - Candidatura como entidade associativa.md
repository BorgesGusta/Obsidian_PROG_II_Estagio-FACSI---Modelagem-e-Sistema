# DM-005 — Candidatura como entidade associativa

## Status

Adotada na versão 0.2.

## Contexto

Aluno e Vaga possuem uma relação muitos-para-muitos ao longo do tempo:

- um aluno pode concorrer a várias vagas;
- uma vaga pode receber vários alunos.

Essa relação possui informações próprias.

## Alternativa descartada

```
Aluno * -------- * Vaga
```

Essa representação não permite guardar adequadamente estado, data e histórico do processo seletivo.

## Decisão

Introduzir a entidade `Candidatura`:

```
Aluno 1 ---- 0..* Candidatura 0..* ---- 1 Vaga
```

## Motivos

- guarda data da candidatura;
- guarda status;
- separa processo seletivo de vínculo de estágio;
- permite histórico;
- prepara o fluxo de seleção e formalização.

## Relação com Orientação a Objetos

Este é um exemplo de **classe associativa**.

A relação entre dois objetos ganhou identidade e comportamento próprios.

## Relação com Estágio

Uma Candidatura selecionada pode originar no máximo um Estágio.

```
Candidatura 1 ---- 0..1 Estagio
```

Essa cardinalidade ainda depende da validação do caso de estágio iniciado sem candidatura registrada.
