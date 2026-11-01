# Relacionamentos — versão 0.2

## Pessoa, Aluno e Professor

- Pessoa é a abstração base.
- Aluno especializa Pessoa.
- Professor especializa Pessoa.

---

## Supervisor e Orientador

Supervisor e Orientador são tratados como papéis exercidos por uma Pessoa no contexto de um estágio.

---

## Concedente e Convênio

`Concedente 1 ---- 0..* Convênio`

---

## Concedente e Vaga

`Concedente 1 ---- 0..* Vaga`

---

## Aluno, Vaga e Candidatura

`Aluno 1 ---- 0..* Candidatura`

`Vaga 1 ---- 0..* Candidatura`

Candidatura funciona como entidade associativa entre Aluno e Vaga.

---

## Candidatura e Estágio

`Candidatura 0..1 ---- 0..1 Estágio`

Uma candidatura selecionada pode originar no máximo um estágio.

Um estágio, porém, pode existir sem candidatura.

Isso cobre casos de contato direto com concedente e atividades de extensão/pesquisa.

---

## Aluno e Estágio

`Aluno 1 ---- 0..* Estágio`

Cada estágio pertence a um aluno.

---

## Estágio e Vaga

### Versão revisada

`Vaga 1 ---- 0..* Estágio`

Do ponto de vista do Estágio:

`Estágio ---- 0..1 Vaga`

Ou seja, uma vaga pode originar vários estágios quando houver mais de uma posição, mas um estágio pode não ter origem em uma vaga cadastrada.

Casos possíveis sem Vaga cadastrada:
- contato direto com concedente;
- projeto/programa de extensão;
- projeto/programa de pesquisa;
- Empresa Júnior;
- outros fluxos institucionais permitidos.

---

## Estágio e Supervisor

`Estágio 1 ---- 1 Pessoa : supervisor`

---

## Estágio e Orientador

`Estágio 1 ---- 1 Pessoa : orientador`

---

## Estágio e Termo de Compromisso

`Estágio 1 ---- 0..1 TermoCompromisso`

---

## Estágio e Plano de Atividades

`Estágio 1 ---- 0..1 PlanoAtividades`

---

## Estágio e Apólice de Seguro

`ApoliceSeguro 1 ---- 0..* Estágio`
