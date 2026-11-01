# UML Final — Decisões de Modelagem

## Arquivos

- `dominio-final-sprint-05.puml` — diagrama principal para apresentação do domínio.
- `diagrama-tecnico-final-sprint-05.puml` — complemento com as classes de regras.

## Decisões

### Diagrama principal

O diagrama principal prioriza o domínio e evita poluição visual com detalhes de infraestrutura ou todos os getters/setters.

Foram incorporadas as evoluções posteriores à Sprint 01:

- Profissional como subclasse de Pessoa;
- AmbitoEstagio;
- RegistroFrequencia;
- RelatorioFinal;
- AvaliacaoEstagio;
- iniciar() e encerrar(LocalDate);
- métodos centrais de cálculo e vigência;
- vigência em Convenio e ApoliceSeguro.

### Supervisor e Orientador

No código atual, supervisor e orientador podem estar nulos. Por isso a multiplicidade do lado de Estagio foi representada como 0..1.

A obrigatoriedade operacional e o momento de definição desses papéis continuam como pontos a validar com o professor.

### Resultado da avaliação

AvaliacaoEstagio.resultado permanece String, refletindo o código atual.

Não foi criado enum de conceitos porque os valores acadêmicos oficiais ainda precisam ser confirmados.

### Status textuais

Convenio, Vaga, Candidatura, TermoCompromisso e PlanoAtividades continuam com status String porque os estados formais ainda não foram definidos no escopo atual.

### Classes de regras

ValidadorEstagio e ValidadorCargaHoraria foram mantidos fora do diagrama principal para preservar a leitura do domínio.

O diagrama técnico complementar registra essas classes, seus principais métodos e a dependência atual com Estagio.

## Cardinalidades principais

- Aluno 1 ↔ 0..* Estagio
- Concedente 1 ↔ 0..* Estagio
- Convenio 0..1 ↔ 0..* Estagio
- Estagio 1 ↔ 0..1 TermoCompromisso
- Estagio 1 ↔ 0..* PlanoAtividades
- Estagio 0..* ↔ 0..* ApoliceSeguro
- Estagio 1 ↔ 0..* RegistroFrequencia
- Estagio 1 ↔ 0..1 RelatorioFinal
- Estagio 1 ↔ 0..1 AvaliacaoEstagio
- Estagio 0..* → 0..1 Pessoa como supervisor
- Estagio 0..* → 0..1 Professor como orientador

## Situação

O diagrama reflete o código consolidado após o commit Java `da97610`, com 48 testes automatizados passando.
