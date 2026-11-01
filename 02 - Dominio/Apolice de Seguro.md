# Apólice de Seguro — versão 0.4

## Definição

Representa a cobertura contra acidentes pessoais vinculada ao Estágio.

## Atributos

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

A relação muitos-para-muitos é mantida porque:
- uma apólice institucional pode cobrir muitos estagiários/estágios;
- um estágio pode ter substituição ou renovação de cobertura ao longo do tempo.

## Evidência documental

A apólice institucional analisada:
- tem a Unifesspa como estipulante;
- é de acidentes pessoais coletivos;
- inclui estagiários entre os segurados;
- possui milhares de segurados;
- possui vigência própria.

Isso confirma que não devemos criar uma apólice individual obrigatória para cada Estágio.

## Regras vigentes

- cobertura deve existir antes do início;
- número da apólice deve constar no Termo;
- estágio não obrigatório: seguro é responsabilidade da Concedente;
- estágio obrigatório: seguro é responsabilidade da Unifesspa, conforme Resolução CONSEPE nº 921/2025;
- histórico de apólices deve ser preservado.
