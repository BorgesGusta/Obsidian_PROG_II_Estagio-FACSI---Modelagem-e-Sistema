# Resumo da Modelagem — Sprint 01

## Objetivo

Modelar o domínio central de estágios da FACSI/Unifesspa antes da implementação em Java, representando de forma estruturada os principais atores, vínculos, regras e documentos do processo.

## Estrutura principal

### Pessoas

`Pessoa` é a abstração base.

Especializações:
- `Aluno`
- `Professor`

Supervisor e Orientador não são tratados da mesma forma:
- Supervisor é um papel exercido por uma `Pessoa`;
- Orientador é um papel acadêmico exercido por um `Professor`.

## Concedente e Convênio

`Concedente` representa a organização, instituição, unidade ou profissional responsável pelo ambiente do estágio.

Para concedentes externas, existe `Convenio`, que registra o vínculo formal com a Unifesspa.

Regras confirmadas:
- convênio possui vigência;
- prazo entre 1 e 5 anos;
- deve preservar histórico de renovações;
- deve contemplar cursos, condições de supervisão, jornada e seguro, conforme normas aplicáveis.

## Vaga e Candidatura

`Vaga` representa uma oportunidade ofertada por uma concedente.

`Candidatura` é uma entidade associativa entre `Aluno` e `Vaga`.

Uma candidatura possui estado próprio e não representa vínculo de estágio.

Nem todo estágio precisa nascer de uma vaga ou candidatura.

## Estágio

`Estagio` é a entidade central do domínio.

Pode ter origem em:
- vaga publicada;
- contato direto com concedente;
- projeto de extensão;
- projeto de pesquisa;
- Empresa Júnior;
- outro fluxo institucional admitido.

Relacionamentos centrais:

```
Aluno
  |
  v
Estagio
  |-- Concedente
  |-- Convenio [quando aplicável]
  |-- Supervisor : Pessoa
  |-- Orientador : Professor
  |-- TermoCompromisso
  |-- PlanoAtividades
  |-- ApoliceSeguro
  |-- Vaga [opcional]
  |-- Candidatura [opcional]
```

Estados candidatos:
- EM_FORMALIZACAO
- ATIVO
- ENCERRADO
- CANCELADO

## Formalização

### Termo de Compromisso

Representa a formalização institucional do vínculo.

Não deve ser tratado apenas como arquivo PDF; deve possuir estado e dados estruturados.

### Plano de Atividades

Representa o conteúdo acadêmico-profissional do estágio.

A legislação permite sua evolução ao longo do vínculo por meio de aditivos ao Termo de Compromisso.

### Seguro

Todo estágio deve possuir cobertura válida contra acidentes pessoais.

O modelo preserva histórico e permite substituição/renovação da cobertura.

## Decisões principais da Sprint

1. Separar Concedente de Convênio.
2. Separar Vaga de Estágio.
3. Criar Candidatura como entidade associativa.
4. Permitir Estágio sem Vaga ou Candidatura.
5. Tratar Estágio como entidade central.
6. Tratar Supervisor como papel de Pessoa.
7. Tratar Orientador como Professor.
8. Relacionar Estágio ao Convênio utilizado quando aplicável.
9. Preservar histórico de convênios, planos, termos e seguros.

## Pontos ainda para validação

A modelagem central está fechada, mas alguns detalhes operacionais dependem de confirmação com a FACSI/professor:

- quantidade de posições por Vaga;
- supervisor previsto na Vaga versus supervisor efetivo;
- troca de supervisor/orientador;
- regra de múltiplos estágios simultâneos;
- escolha do orientador;
- fluxo de aditivos;
- restrições adicionais de convênio;
- pendências que impedem novo estágio ou encerramento.

## Estado atual

A modelagem está pronta para uma primeira validação com o professor antes da implementação Java.
