# Matriz de Auditoria — Sprint 05

## Objetivo

Classificar as diferenças entre a UML candidata, o código Java atual, as regras oficiais e os testes automatizados.

## 1. MANTER

| Item | Decisão | Motivo |
|---|---|---|
| Pessoa abstrata | MANTER | Base adequada para Aluno, Professor e Profissional |
| Supervisor como Pessoa | MANTER | Permite supervisor interno ou externo |
| Orientador como Professor | MANTER | Compatível com o papel acadêmico modelado |
| Concedente separada de Convênio | MANTER | Entidades têm ciclos de vida diferentes |
| Vaga separada de Estágio | MANTER | Vaga é oportunidade; Estágio é vínculo formalizado |
| Candidatura como entidade | MANTER | Guarda decisão e histórico da candidatura |
| Termo, Plano e Seguro separados | MANTER | Correspondem a documentos/relações distintas |
| Histórico de Planos | MANTER | Compatível com prorrogação e novo Plano |
| Apólice muitos-para-muitos | MANTER | Compatível com apólice coletiva |
| AmbitoEstagio | MANTER | Resolve explicitamente INTERNO x EXTERNO |
| RegistroFrequencia | MANTER | Representa acompanhamento real |
| 6h/dia e 30h/semana | MANTER | Regra geral vigente |
| Limite de dois não obrigatórios | MANTER | Regra vigente |
| 170h no obrigatório FACSI | MANTER | Regra específica do curso |
| iniciar() e encerrar() | MANTER | Protegem as transições principais de status |
| ValidadorCargaHoraria separado | MANTER | Regras simultâneas precisam receber vários estágios |

## 2. AJUSTAR UML

- adicionar Profissional como subclasse de Pessoa;
- adicionar AmbitoEstagio;
- adicionar RegistroFrequencia;
- adicionar RelatorioFinal;
- adicionar AvaliacaoEstagio;
- atualizar Estagio com ambito;
- mostrar iniciar() e encerrar(LocalDate) no Estagio;
- representar relacionamentos de frequência, relatório e avaliação;
- decidir se ValidadorEstagio e ValidadorCargaHoraria aparecem no diagrama técnico complementar.

## 3. AJUSTAR JAVA ANTES DA UML FINAL

### AJ-01 — Período obrigatório para iniciar

Hoje um estágio pode iniciar com dataInicio ou dataFimPrevista nulas.

Decisão:
- exigir dataInicio;
- exigir dataFimPrevista;
- impedir dataFimPrevista anterior à dataInicio.

Motivo:
o período de vigência é informação obrigatória do Plano e é necessário para validar Convênio, Seguro e simultaneidade.

### AJ-02 — Vigência do Convênio

Hoje estágio EXTERNO exige um objeto Convenio, mas não verifica se o convênio está vigente no início.

Decisão:
- adicionar verificação simples de vigência;
- para estágio EXTERNO, o convênio deve cobrir a dataInicio;
- não inventar regra adicional sobre renovação no meio do estágio sem base operacional.

### AJ-03 — Cobertura do Seguro

Hoje basta existir uma ApoliceSeguro.

Decisão:
- exigir pelo menos uma apólice que cubra a dataInicio do estágio;
- uma apólice sem datas não comprova cobertura para a regra de início.

### AJ-04 — Coerência de dataFimReal

Hoje encerrar(dataFimReal) aceita qualquer data não nula.

Decisão:
- dataFimReal não pode ser anterior a dataInicio;
- dataFimReal não pode ser anterior ao último RegistroFrequencia;
- não exigir que seja menor ou igual a dataFimPrevista, porque prorrogações podem existir.

## 4. VALIDAR COM PROFESSOR

### VP-01 — Resultado da avaliação

O regulamento FACSI fala em avaliação pelo coordenador e lançamento de conceito no histórico, mas o código usa String "APROVADO".

Não criar enum nem novos valores sem confirmar quais conceitos/status devem existir.

### VP-02 — Supervisor e Orientador antes do início

Os documentos exigem participação/assinaturas desses papéis, mas o momento operacional de definição ainda precisa ser confirmado.

Não bloquear iniciar() por esses campos até essa decisão.

### VP-03 — Semana de transição

Dois estágios sem sobreposição podem cair na mesma semana civil.

Confirmar se a FACSI soma essas horas para o limite semanal.

### VP-04 — Termo Aditivo

A norma confirma novo Plano na prorrogação, mas outras alterações que geram Termo Aditivo ainda precisam ser confirmadas.

## 5. MELHORIA FUTURA

- transformar status textuais de Convenio, Vaga, Candidatura, Termo e Plano em enums quando os estados forem conhecidos;
- criar cancelar() e regras de cancelamento;
- limitar setters estruturais depois que o estágio iniciar;
- substituir comparação de Aluno por referência por identidade/equals quando houver persistência;
- modelar exceção de até 40h somente se aplicável ao PPC;
- tratar horas fracionadas se o processo real exigir;
- resolver dependência circular entre model e regras caso a arquitetura evolua;
- histórico/versionamento de RelatorioFinal;
- registrar autor efetivo dos pareceres caso haja troca de responsáveis;
- validar assinatura/data de assinatura do Termo quando esse dado for modelado.

## Prioridade

Antes da UML final:
1. AJ-01 período;
2. AJ-02 convênio vigente;
3. AJ-03 seguro vigente;
4. AJ-04 dataFimReal coerente;
5. executar todos os testes;
6. atualizar UML.
