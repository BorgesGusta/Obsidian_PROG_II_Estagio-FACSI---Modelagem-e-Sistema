# Formação Programação II — Guia de Estudo

## Objetivo

Usar o próprio projeto Estágio FACSI como laboratório para revisar Java e Programação II, com foco em orientação a objetos.

A versão de entrega permanece protegida na branch main. Os exercícios são feitos na branch estudo/prog2.

## Ciclo de cada módulo

1. Estudar o conceito no NotebookLM.
2. Relacionar o conceito com classes reais do projeto.
3. Responder perguntas sem olhar o código.
4. Abrir o projeto no VS Code.
5. Executar um pequeno laboratório.
6. Rodar os testes.
7. Explicar com as próprias palavras o que aconteceu.
8. Fazer uma revisão rápida antes de avançar.

## Baseline do projeto

- Java: projeto Maven
- Branch de entrega: main
- Branch de estudo: estudo/prog2
- Testes automatizados atuais: 48
- Resultado esperado: 48 testes, 0 falhas, 0 erros
- Main executável pelo terminal

Comandos de referência:

```bash
git branch --show-current
mvn test
mvn compile
java -cp target/classes br.edu.unifesspa.facsi.estagio.Main
```

## Trilha

### Módulo 01 — Fundamentos de OO
- classe
- objeto
- atributo
- método
- construtor
- instância
- referência

Classes-base:
- Pessoa
- Aluno
- Professor
- Profissional

### Módulo 02 — Encapsulamento
- private
- getters/setters
- proteção do estado
- métodos de negócio
- por que Estagio não possui setStatus()

Classes-base:
- Estagio
- ValidadorEstagio

### Módulo 03 — Herança e abstração
- extends
- super
- classe abstrata
- relação é-um

Classes-base:
- Pessoa
- Aluno
- Professor
- Profissional

### Módulo 04 — Polimorfismo
- substituição polimórfica
- tipo da referência x tipo do objeto
- sobrescrita
- @Override

Ponto atual:
- Estagio.supervisor é Pessoa e pode receber Professor ou Profissional.
- O projeto usa polimorfismo de tipo, mas explora pouco polimorfismo comportamental.

Laboratório:
- criar comportamento polimórfico apenas na branch estudo/prog2.

### Módulo 05 — Associações e cardinalidades
- 1:1
- 1:N
- N:N
- composição/agregação em nível conceitual

Classes-base:
- Estagio
- Aluno
- Concedente
- PlanoAtividades
- ApoliceSeguro
- RegistroFrequencia

### Módulo 06 — Collections
- List
- ArrayList
- iteração
- filtros
- soma

Classes-base:
- Estagio
- ValidadorCargaHoraria

### Módulo 07 — Enums
- ModalidadeEstagio
- OrigemEstagio
- AmbitoEstagio
- StatusEstagio

### Módulo 08 — static e classes utilitárias
- constantes
- métodos static
- estado de instância x comportamento utilitário

Classes-base:
- ValidadorEstagio
- ValidadorCargaHoraria

### Módulo 09 — Interfaces
O projeto de entrega não explora interfaces Java.

Laboratório sugerido:
- criar uma interface Vigente na branch de estudo;
- aplicar em Convenio e ApoliceSeguro;
- comparar com a implementação atual.

### Módulo 10 — Exceções
O projeto de entrega usa retorno boolean para regras principais.

Laboratório sugerido:
- estudar diferença entre retornar false e lançar exceção;
- criar exercício isolado sem alterar a main.

### Módulo 11 — JUnit
- @Test
- asserts
- cenários válidos e inválidos
- testes de regressão

Classes:
- EstagioTest
- ValidadorEstagioTest
- ValidadorCargaHorariaTest

### Módulo 12 — Leitura completa do sistema
Explicar o fluxo:

Aluno -> oportunidade -> candidatura -> estágio -> formalização -> acompanhamento -> encerramento

### Módulo 13 — Defesa oral
Responder perguntas sem consultar material.

### Módulo 14 — Simulação com professor
Bateria de perguntas sobre Java, OO, modelagem e decisões do projeto.
