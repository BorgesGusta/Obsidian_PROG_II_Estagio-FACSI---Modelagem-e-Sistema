# UML Final — Decisões de Modelagem

## Arquivos

- `dominio-final-sprint-05.puml` — diagrama principal para apresentação do domínio.
- `diagrama-tecnico-final-sprint-05.puml` — complemento com as classes de regras.

## Decisões

### Diagrama principal

O diagrama principal prioriza o domínio e evita poluição visual com detalhes de infraestrutura, getters/setters e atributos secundários. Após a primeira renderização, a composição foi compactada para melhorar leitura em tela e apresentação, sem alterar relações ou cardinalidades.

Foram incorporadas as evoluções posteriores à Sprint 01:

- Profissional como subclasse de Pessoa;
- AmbitoEstagio;
- RegistroFrequencia;
- RelatorioFinal;
- AvaliacaoEstagio;
- iniciar() e encerrar(LocalDate);
- métodos centrais de cálculo, vigência e verificação dos limites diário/semanal;
- vigência em Convenio e ApoliceSeguro.

### Supervisor e Orientador

No código atual, supervisor e orientador podem estar nulos. Por isso cada Estagio possui 0..1 supervisor e 0..1 orientador. Uma Pessoa/Professor pode estar associada a 0..* estágios.

A obrigatoriedade operacional e o momento de definição desses papéis continuam como pontos a validar com o professor.

### Resultado da avaliação

AvaliacaoEstagio.resultado permanece String, refletindo o código atual.

Não foi criado enum de conceitos porque os valores acadêmicos oficiais ainda precisam ser confirmados.

### Status textuais

Convenio, Vaga, Candidatura, TermoCompromisso e PlanoAtividades continuam com status String porque os estados formais ainda não foram definidos no escopo atual.

### Classes de regras

ValidadorEstagio e ValidadorCargaHoraria foram mantidos fora do diagrama principal para preservar a leitura do domínio.

O diagrama técnico complementar registra essas classes, seus principais métodos e a dependência atual com Estagio.

### Encerramento e limites de carga horária

O registro de frequência pode ser preservado mesmo quando identifica uma irregularidade de carga horária. O encerramento, porém, só é permitido quando os limites de 6h/dia e 30h/semana estão regulares.

Essa decisão permite manter evidência do registro realizado sem tratar uma carga irregular como válida para conclusão do estágio.

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

O diagrama reflete o código consolidado após o commit Java `2665ff2`, com 72 testes automatizados passando (0 falhas e 0 erros na validação de 17/11/2026).
