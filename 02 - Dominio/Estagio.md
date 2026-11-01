# Estágio — versão 0.4

## Definição

`Estagio` representa o vínculo efetivamente formalizado para um aluno.

Pode surgir de:
- Vaga publicada;
- contato direto;
- projeto/programa de extensão;
- projeto/programa de pesquisa;
- Empresa Júnior;
- outro fluxo institucional permitido.

Vaga e Candidatura são opcionais na origem.

## Atributos centrais

- id
- modalidade
- origem
- dataInicio
- dataFimPrevista
- dataFimReal
- cargaHorariaDiaria
- cargaHorariaSemanal
- cargaHorariaTotalPrevista
- status

## Modalidade

- OBRIGATORIO
- NAO_OBRIGATORIO

Modalidade não deve ser confundida com remuneração.

Um estágio obrigatório pode possuir ou não remuneração conforme as condições formalizadas.

Estágio não obrigatório precisa possuir contrapartida financeira.

## Jornada

A Resolução CONSEPE nº 921/2025 determina que o somatório de estágios simultâneos, obrigatórios e não obrigatórios, respeite como regra geral:
- 6 horas diárias;
- 30 horas semanais.

Dois estágios não obrigatórios podem coexistir se:
- respeitarem a soma máxima;
- os horários não coincidirem;
- não coincidirem com o turno letivo;
- forem compatíveis com o curso.

## Estado

- EM_FORMALIZACAO
- ATIVO
- ENCERRADO
- CANCELADO

## Relações

```
Aluno 1 -------- 0..* Estagio
Concedente 1 ---- 0..* Estagio
Convenio 0..1 --- 0..* Estagio
Vaga 0..1 ------- 0..* Estagio
Candidatura 0..1 - 0..1 Estagio
Estagio --------- 1 Pessoa : supervisor
Estagio --------- 1 Professor : orientador
Estagio 1 ------- 0..1 TermoCompromisso
Estagio 1 ------- 0..1 PlanoAtividades
Estagio 0..* ---- 0..* ApoliceSeguro
```

## Condições para ativação

Antes de passar para ATIVO, verificar:
- aluno válido;
- concedente apta;
- convênio vigente quando exigido;
- modalidade;
- jornada e soma com outros estágios;
- Supervisor;
- Orientador;
- Termo formalizado;
- Plano válido;
- seguro vigente;
- demais impedimentos institucionais.

## Observação sobre remuneração

As condições financeiras efetivas ficam formalizadas no `TermoCompromisso`.

A Vaga pode trazer valores ofertados, mas o Termo representa as condições efetivamente pactuadas.

## Questões abertas

- Origem como enum ou entidades específicas?
- Como registrar mudança de Supervisor/Orientador?
- Quais pendências anteriores bloqueiam novo vínculo?
