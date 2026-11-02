# Mapa do Código — Conceitos de Programação II

## Pessoa

`Pessoa` é uma classe abstrata que concentra dados comuns.

Conceitos:
- abstração;
- encapsulamento;
- herança;
- construtor protegido.

## Aluno, Professor e Profissional

As três classes usam `extends Pessoa`.

Conceitos:
- herança;
- especialização;
- uso de `super(...)`;
- reutilização de atributos e comportamento.

## Estagio

É a principal classe de domínio.

Conceitos:
- objeto com estado;
- encapsulamento;
- associações;
- listas;
- enums;
- métodos de negócio;
- constantes static;
- datas;
- mudança controlada de status.

Ponto importante:
o status não possui setter público. A mudança ocorre por `iniciar()` e `encerrar(...)`.

## Supervisor

O campo supervisor é do tipo `Pessoa`.

Isso permite que diferentes subclasses de Pessoa sejam usadas no mesmo papel.

Exemplo conceitual:

```java
Pessoa supervisor = professor;
Pessoa supervisor = profissional;
```

Isso demonstra substituição polimórfica.

## Concedente e Convenio

Conceitos:
- associação;
- coleção;
- regra de vigência;
- objeto com identidade própria.

## Vaga e Candidatura

Conceitos:
- associação entre entidades;
- separação entre oportunidade e vínculo;
- entidade associativa representando uma candidatura.

## PlanoAtividades

Um Estagio pode possuir vários planos.

Conceitos:
- relação 1:N;
- List;
- histórico.

## ApoliceSeguro

Uma apólice pode cobrir vários estágios, e um estágio pode ter várias apólices.

Conceitos:
- relação N:N;
- List;
- vigência.

## RegistroFrequencia

Representa uma ocorrência vinculada ao estágio.

Conceitos:
- 1:N;
- agregação de valores;
- iteração sobre lista;
- cálculo por data e por semana.

## RelatorioFinal e AvaliacaoEstagio

Conceitos:
- relações opcionais 1:1;
- estado de encerramento;
- composição de regras de negócio.

## ValidadorEstagio

Classe utilitária de regras.

Conceitos:
- métodos static;
- constantes;
- separação de responsabilidades;
- composição de condições booleanas.

## ValidadorCargaHoraria

Recebe Aluno e lista de Estagio para validar regras que dependem de vários objetos.

Conceitos:
- collections;
- filtros;
- iteração;
- comparação de períodos;
- métodos auxiliares;
- static.

## Testes JUnit

Os testes são parte importante da aprendizagem.

Conceitos:
- cenário;
- preparação;
- execução;
- asserção;
- regressão.

O projeto possui atualmente 48 testes automatizados.
