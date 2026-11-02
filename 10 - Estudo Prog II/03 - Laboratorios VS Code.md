# Laboratórios VS Code — Programação II

## Regras

Todos os laboratórios devem ser feitos na branch:

`estudo/prog2`

Antes de começar:

```bash
git branch --show-current
mvn test
```

O resultado base deve ser 48 testes aprovados.

Não fazer merge para main sem decisão explícita.

## Laboratório 01 — Objetos e construtores

Arquivos:
- Pessoa.java
- Aluno.java
- Professor.java
- Profissional.java

Objetivos:
- identificar atributos;
- identificar parâmetros do construtor;
- entender `super(...)`;
- criar objetos no debugger e observar seus campos.

## Laboratório 02 — Herança

Experimento:
- observar quais métodos de Pessoa podem ser usados por um objeto Aluno;
- localizar onde os atributos herdados são inicializados.

Pergunta central:
Por que Aluno não declara novamente nome, cpf e email?

## Laboratório 03 — Polimorfismo

Exercício de estudo, não de entrega:

- criar temporariamente um método abstrato em Pessoa, por exemplo `descreverPapel()`;
- sobrescrever em Aluno, Professor e Profissional;
- criar uma variável Pessoa apontando para objetos diferentes;
- observar qual implementação é executada.

Depois discutir por que isso é polimorfismo comportamental.

## Laboratório 04 — Encapsulamento

Arquivos:
- Estagio.java
- ValidadorEstagio.java

Objetivos:
- entender por que status não tem setter;
- seguir o fluxo de `iniciar()`;
- colocar breakpoint em `podeIniciar()`;
- observar os dados do objeto.

## Laboratório 05 — List

Arquivos:
- Estagio.java
- ValidadorCargaHoraria.java

Objetivos:
- observar ArrayList;
- adicionar registros;
- iterar;
- calcular horas.

## Laboratório 06 — Enums

Experimentos:
- localizar os quatro enums;
- comparar enum com String;
- explicar por que StatusEstagio é mais seguro que um String livre.

## Laboratório 07 — Interface

Somente na branch de estudo.

Criar:

```java
public interface Vigente {
    boolean estaVigenteEm(LocalDate data);
}
```

Aplicar em Convenio e ApoliceSeguro.

Objetivo:
entender `implements` e contrato de interface.

## Laboratório 08 — JUnit

Executar:

```bash
mvn -Dtest=ValidadorEstagioTest test
```

Depois executar um método específico.

Objetivo:
entender como um teste isola uma regra.

## Debug

Breakpoints recomendados:

- Estagio.iniciar()
- ValidadorEstagio.podeIniciar()
- Estagio.encerrar()
- ValidadorCargaHoraria.respeitaLimiteDiario()

Durante a pausa, observar:
- `this`;
- status;
- aluno;
- concedente;
- convenio;
- listas;
- chamadas na pilha.
