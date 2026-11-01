# DM-003 — Pessoa, Aluno, Professor, Supervisor e Orientador

## Status

Proposta adotada na versão 0.1.

## Problema

O domínio possui pessoas que podem aparecer como:
- aluno;
- professor;
- supervisor;
- orientador.

Uma mesma pessoa pode exercer mais de um papel dependendo do estágio. Em especial, um professor pode ser orientador em um vínculo e supervisor em outro, e alguns cenários permitem acumular os dois papéis.

## Alternativa 1 — Herança para todos

```
Pessoa
├── Aluno
├── Professor
├── Supervisor
└── Orientador
```

### Problema
Supervisor e Orientador não são necessariamente tipos permanentes de pessoa. São funções exercidas em um contexto.

Essa solução dificulta representar a mesma pessoa em múltiplos papéis.

## Alternativa 2 — Herança apenas para tipos institucionais e papéis no vínculo

```
Pessoa
├── Aluno
└── Professor
```

Supervisor e Orientador são papéis associados ao Estágio.

## Decisão

Adotar a Alternativa 2 na versão 0.1.

### Motivo
- Aluno e Professor possuem características institucionais próprias.
- Supervisor e Orientador dependem do contexto do estágio.
- Evita criar múltiplos objetos para representar a mesma pessoa.
- Permite que uma pessoa exerça mais de um papel.

## Impacto na UML

Estágio possuirá associações com Pessoa para os papéis de supervisor e orientador.

## Ponto para revisão

Se surgirem regras específicas suficientes para Supervisor e Orientador, pode ser criada posteriormente uma entidade de vínculo/papel, por exemplo `ParticipacaoEstagio` ou `PapelNoEstagio`, sem precisar alterar a identidade principal de Pessoa.
