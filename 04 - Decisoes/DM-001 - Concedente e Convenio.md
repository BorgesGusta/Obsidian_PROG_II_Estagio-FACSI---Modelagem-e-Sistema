# DM-001 — Separar Concedente de Convênio

## Status

Adotada na versão 0.2 e respaldada pela Resolução CONSEPE nº 016/2014 da Unifesspa.

## Contexto

A norma institucional trata a concedente e o convênio como conceitos distintos.

A concedente é a organização, instituição, unidade ou profissional que recebe o estagiário. Para entidades externas, a Unifesspa firma um convênio que estabelece as condições de realização do estágio.

O convênio possui prazo próprio de vigência e pode ser renovado.

## Base normativa

O art. 14 da Resolução CONSEPE nº 016/2014 determina convênio para entidades externas concedentes.

O instrumento deve informar, entre outros pontos:

- cursos contemplados;
- carga horária;
- supervisor da área;
- condições de supervisão;
- seguro;
- prazo de vigência entre **1 e 5 anos**.

A Resolução também prevê que a PROEG mantenha atualizado o cadastro de convênios e oriente sobre suas renovações.

## Problema da alternativa simples

```
Concedente
- ativa
- dataInicio
- dataFim
```

Essa estrutura não representa corretamente o histórico institucional.

Em uma renovação, datas anteriores seriam sobrescritas ou seria necessário criar campos improvisados.

## Decisão

Separar:

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
- representa renovações;
- permite identificar lacunas entre vigências;
- facilita validar se o convênio é válido para o curso;
- permite consultar concedentes aptas em determinado período;
- reflete diretamente a estrutura prevista na norma institucional.

## Consequências a observar

- verificar se podem existir convênios vigentes sobrepostos para uma mesma concedente;
- definir tratamento de cancelamento antecipado;
- confirmar eventuais restrições por campus, unidade acadêmica ou modalidade.

## Relação com Orientação a Objetos

É uma **associação entre classes**.

```
Convenio NÃO É uma Concedente.
```

Uma concedente **possui** convênios ao longo do tempo.
