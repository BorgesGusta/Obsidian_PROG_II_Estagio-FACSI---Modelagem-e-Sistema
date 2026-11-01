# Plano de Atividades — versão 0.4

## Definição

Representa o planejamento acadêmico-profissional das atividades do Estágio.

## Atributos próprios

- id
- areaAtuacao
- justificativa
- objetivoGeral
- objetivosEspecificos
- descricaoAtividades
- adequacaoPedagogica
- cronograma
- status

## Dados obrigatórios do Plano

A Resolução 921/2025 exige:
- dados do discente;
- dados da concedente;
- período de vigência;
- carga horária semanal;
- carga horária total;
- cronograma detalhado.

Na modelagem OO, dados de Aluno, Concedente, período e carga podem ser obtidos pelas relações com o Estágio, evitando duplicação desnecessária.

## Fluxo

- RASCUNHO
- EM_ANALISE
- APROVADO
- REJEITADO
- SUBSTITUIDO

## Participantes

O Plano é acompanhado/validado pelos responsáveis acadêmicos e pelo Supervisor da concedente conforme o tipo de estágio.

## Prorrogação e versão

Quando o período do estágio for prorrogado:
1. deve ser criado novo Plano;
2. o docente orientador deve validá-lo;
3. o novo Plano deve ser anexado ao Termo Aditivo.

Isso confirma a necessidade de preservar histórico de Planos.

## Relação

```
Estagio 1 -------- 0..* PlanoAtividades
```

### Revisão de cardinalidade

A versão anterior usava `0..1`. A norma vigente confirma que uma prorrogação pode gerar um novo Plano, portanto um Estágio pode possuir vários Planos ao longo do tempo, ainda que apenas um esteja vigente em determinado período.
