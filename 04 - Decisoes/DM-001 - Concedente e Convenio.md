# DM-001 — Separar Concedente de Convênio

## Status

Adotada na versão 0.2.

## Contexto

Uma concedente não deixa de existir quando seu convênio termina.

Além disso, uma mesma concedente pode possuir diferentes períodos de vigência e pode existir uma lacuna entre o fim de um convênio e o início de outro.

## Problema da alternativa simples

```
Concedente
- ativa
- dataInicio
- dataFim
```

Essa estrutura não representa corretamente o histórico.

Se o convênio for renovado, seria necessário sobrescrever as datas anteriores ou criar campos adicionais.

## Decisão

Separar os conceitos:

```
Concedente
    1
    |
    | possui
    |
    0..*
Convenio
```

## Consequências positivas

- preserva histórico;
- permite identificar lacunas entre vigências;
- facilita consulta de concedentes aptas;
- permite registrar renovação sem sobrescrever dados anteriores;
- reduz dependência de controles manuais.

## Consequências a observar

- será necessário validar se podem existir períodos sobrepostos;
- será necessário definir como tratar cancelamento antecipado;
- será necessário confirmar se o convênio possui restrições por curso, campus ou modalidade.

## Relação com Orientação a Objetos

Este caso é um exemplo de **associação entre classes**.

Não existe relação de herança:

```
Convenio NÃO É uma Concedente.
```

Existe uma relação de pertencimento:

```
Uma Concedente POSSUI Convênios.
```
