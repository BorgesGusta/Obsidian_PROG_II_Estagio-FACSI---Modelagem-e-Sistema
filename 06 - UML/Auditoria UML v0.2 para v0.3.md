# Auditoria da UML v0.2 → v0.3

## Objetivo

Revisar cardinalidades, responsabilidades, duplicações e dependências antes de apresentar a modelagem ao professor.

## Ajustes feitos

### 1. Orientador passa a ser Professor

Antes:
```
Estagio --> Pessoa : orientador
```

Agora:
```
Estagio --> Professor : orientador
```

Motivo: orientação acadêmica é papel docente no contexto levantado com a FACSI.

### 2. Estágio passa a referenciar o Convênio utilizado

Adicionado:

```
Convenio 0..1 ---- 0..* Estagio
```

Motivo: somente relacionar Estágio à Concedente não preserva qual período de convênio sustentou aquele vínculo.

Para estágio externo, o convênio aplicável deve ser identificado. Em cenários internos em que não seja necessário convênio, a associação pode ser nula.

### 3. Seguro passa a admitir histórico

Antes:
```
ApoliceSeguro 1 ---- 0..* Estagio
```

Agora:
```
Estagio 0..* ---- 0..* ApoliceSeguro
```

Motivo: uma apólice pode cobrir vários vínculos e um estágio pode trocar/renovar cobertura durante sua duração.

## Decisões mantidas

- Pessoa é superclasse de Aluno e Professor.
- Supervisor é papel de Pessoa.
- Candidatura é entidade associativa.
- Vaga é opcional para Estágio.
- Candidatura é opcional para Estágio.
- Concedente é ligação direta de Estágio.
- OrigemEstagio continua enum na v0.3.
- Modalidade fica registrada no Estágio, mesmo quando originada de Vaga, para preservar o vínculo formalizado.

## Pontos ainda não fechados

- quantidade de posições de uma Vaga;
- supervisor previsto na Vaga versus supervisor efetivo;
- versionamento/aditivos do Termo;
- versionamento do Plano;
- regra exata de múltiplos estágios simultâneos;
- troca de supervisor/orientador;
- estrutura detalhada para projetos de extensão/pesquisa;
- regras de pendências para abertura/encerramento.

## Resultado

O núcleo está consistente o suficiente para seguir para revisão normativa final e validação com o professor antes da implementação Java.
