# Relacionamentos — versão 0.3

## Pessoa, Aluno e Professor

- Pessoa é a abstração base.
- Aluno especializa Pessoa.
- Professor especializa Pessoa.

## Supervisor e Orientador

Supervisor continua sendo um **papel exercido por uma Pessoa**, pois pode ser profissional externo ou, em estágio interno, um professor.

Orientador acadêmico é um **Professor da instituição** no modelo atual.

```
Estagio --> Pessoa : supervisor
Estagio --> Professor : orientador
```

Uma mesma pessoa pode acumular os papéis quando a regra institucional permitir.

## Concedente e Convênio

`Concedente 1 ---- 0..* Convênio`

Uma concedente externa pode possuir vários convênios ao longo do tempo.

## Concedente e Vaga

`Concedente 1 ---- 0..* Vaga`

## Concedente e Estágio

`Concedente 1 ---- 0..* Estágio`

Todo Estágio possui uma concedente responsável.

## Convênio e Estágio

`Convênio 0..1 ---- 0..* Estágio`

Do ponto de vista do Estágio, o Convênio é:
- obrigatório quando se tratar de estágio externo que depende de convênio;
- ausente quando o vínculo institucional não exigir convênio, como determinados estágios internos.

Guardar o Convênio utilizado preserva o histórico mesmo depois que ele vence ou é renovado.

## Aluno, Vaga e Candidatura

`Aluno 1 ---- 0..* Candidatura`

`Vaga 1 ---- 0..* Candidatura`

Candidatura é entidade associativa entre Aluno e Vaga.

## Candidatura e Estágio

`Candidatura 0..1 ---- 0..1 Estágio`

Um Estágio pode existir sem Candidatura.

## Aluno e Estágio

`Aluno 1 ---- 0..* Estágio`

Cada estágio pertence a exatamente um aluno.

## Estágio e Vaga

Do ponto de vista do Estágio:

`Estágio ---- 0..1 Vaga`

Vaga é origem opcional.

## Estágio e Termo de Compromisso

`Estágio 1 ---- 0..1 TermoCompromisso`

Na v0.3 mantemos um Termo principal por Estágio. Aditivos/versionamento ficam como evolução pendente.

## Estágio e Plano de Atividades

`Estágio 1 ---- 0..1 PlanoAtividades`

Na v0.3 mantemos um Plano principal. Versionamento fica pendente.

## Estágio e Apólice de Seguro

`Estágio 0..* ---- 0..* ApoliceSeguro`

A relação é muitos-para-muitos porque:
- uma apólice institucional pode cobrir vários estágios;
- um estágio pode precisar de mais de uma apólice ao longo do tempo em caso de substituição/renovação.

Regra de ativação: deve existir pelo menos uma cobertura válida para o período correspondente.
