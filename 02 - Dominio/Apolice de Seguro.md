# Apólice de Seguro — versão 0.2

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
ApoliceSeguro 1 -------- 0..* Estagio
```

Uma mesma apólice pode cobrir mais de um estágio quando isso for aplicável.

Todo Estágio ativo deve estar coberto por seguro válido.

## Regras

- a cobertura deve estar vigente no período do estágio;
- o estágio não deve iniciar sem cobertura válida;
- a apólice não deve ser apagada do histórico quando vencer;
- a responsabilidade pela contratação pode variar conforme modalidade e arranjo institucional.

## Questões abertas

- Quem fornece o seguro em cada modalidade?
- Uma apólice institucional pode cobrir vários alunos simultaneamente?
- Como registrar substituição de apólice durante um estágio?
