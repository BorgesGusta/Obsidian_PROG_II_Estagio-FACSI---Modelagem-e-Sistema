# Relacionamentos — versão 0.1

## Pessoa, Aluno e Professor

- Pessoa é a abstração base.
- Aluno especializa Pessoa.
- Professor especializa Pessoa.

### Motivo
Aluno e Professor possuem identidade pessoal comum, mas dados institucionais diferentes.

---

## Supervisor e Orientador

Nesta versão, Supervisor e Orientador são tratados como **papéis exercidos por uma Pessoa no contexto de um estágio**, e não como subclasses permanentes de Pessoa.

### Consequência
A mesma pessoa pode:
- atuar apenas como supervisor;
- atuar apenas como orientador;
- atuar nos dois papéis em estágios diferentes;
- em casos permitidos, atuar nos dois papéis no mesmo estágio.

---

## Concedente e Convênio

`Concedente 1 ---- 0..* Convênio`

Uma concedente pode possuir nenhum, um ou vários convênios ao longo do tempo.

Um convênio pertence a exatamente uma concedente.

---

## Concedente e Vaga

`Concedente 1 ---- 0..* Vaga`

Uma concedente pode ofertar várias vagas.

Cada vaga pertence a uma concedente.

---

## Aluno, Vaga e Candidatura

`Aluno 1 ---- 0..* Candidatura`

`Vaga 1 ---- 0..* Candidatura`

Candidatura funciona como entidade associativa entre Aluno e Vaga.

---

## Candidatura e Estágio

Uma candidatura selecionada pode originar um estágio.

### Hipótese atual
`Candidatura 1 ---- 0..1 Estágio`

Nem toda candidatura gera estágio.

### Dúvida aberta
Confirmar se pode existir estágio sem candidatura registrada, por exemplo quando o aluno encontra diretamente a oportunidade.

---

## Aluno e Estágio

`Aluno 1 ---- 0..* Estágio`

Um aluno pode possuir vários estágios ao longo do tempo e, observadas as regras aplicáveis, pode possuir vínculos simultâneos.

Cada estágio pertence a um aluno.

---

## Estágio e Vaga

`Vaga 1 ---- 0..* Estágio`

Uma vaga pode originar um ou mais estágios caso represente mais de uma posição.

### Dúvida aberta
Confirmar se uma Vaga representa uma única posição ou pode possuir quantidade de vagas.

---

## Estágio e Supervisor

`Estágio 1 ---- 1 Pessoa : supervisor`

A pessoa associada deve estar habilitada a exercer o papel de supervisor naquele vínculo.

### Dúvida aberta
Confirmar se deve haver histórico de troca de supervisor.

---

## Estágio e Orientador

`Estágio 1 ---- 1 Pessoa : orientador`

A pessoa associada deve ser apta a exercer o papel de orientação acadêmica.

---

## Estágio e Termo de Compromisso

`Estágio 1 ---- 0..1 TermoCompromisso`

Durante a formalização, o termo pode ainda não existir ou não estar completo.

---

## Estágio e Plano de Atividades

`Estágio 1 ---- 0..1 PlanoAtividades`

O plano torna-se obrigatório para que o estágio possa efetivamente prosseguir.

---

## Estágio e Apólice de Seguro

`ApoliceSeguro 1 ---- 0..* Estágio`

Uma mesma apólice pode cobrir vários estágios quando aplicável.

Cada estágio deve estar vinculado a uma apólice válida antes do início efetivo.
