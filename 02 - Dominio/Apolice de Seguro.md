# Apólice de Seguro — versão 0.3

## Definição

Representa a cobertura contra acidentes pessoais associada ao estágio.

## Atributos iniciais

- id
- numero
- seguradora
- dataInicio
- dataFim
- documentoReferencia

## Relação com Estágio

```
Estagio 0..* -------- 0..* ApoliceSeguro
```

Uma mesma apólice pode cobrir vários estágios e um estágio pode possuir mais de uma cobertura ao longo do tempo.

## Regras confirmadas

- o estágio não deve iniciar sem cobertura válida;
- a cobertura deve permanecer válida durante o período correspondente;
- a concedente é, como regra, responsável pela contratação do seguro;
- no estágio obrigatório, a instituição de ensino pode assumir essa responsabilidade;
- a apólice e suas substituições devem permanecer no histórico.

## Consequência de modelagem

Não fixar a responsabilidade pelo seguro diretamente em `Estagio`, pois ela depende da modalidade e do arranjo institucional.

## Questões ainda abertas

- Como a FACSI registra uma apólice institucional que cobre vários alunos?
- Qual é o fluxo quando a apólice é substituída durante um vínculo?
