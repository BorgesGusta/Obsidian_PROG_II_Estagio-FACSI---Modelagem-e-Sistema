# Regras de Negócio

> Base principal vigente: Resolução CONSEPE nº 921/2025 da Unifesspa, complementada pelo Regulamento FACSI 01/2022 quando não houver conflito.

## Confirmadas

### RN-001 — Modalidade
Todo estágio é **obrigatório** ou **não obrigatório**.

### RN-002 — Convênio externo
Concedente externa deve possuir convênio válido quando aplicável.

### RN-003 — Vigência do convênio
O convênio deve possuir vigência entre **1 e 5 anos**.

### RN-004 — Histórico de convênios
Renovações não devem sobrescrever convênios anteriores.

### RN-005 — Vaga
Toda Vaga cadastrada pertence a uma Concedente.

### RN-006 — Vaga não é obrigatória
Nem todo Estágio precisa nascer de Vaga cadastrada.

### RN-007 — Candidatura não é estágio
Candidatura representa participação em processo seletivo, não vínculo de estágio.

### RN-008 — Estágio sem candidatura
Um Estágio pode ser formalizado sem Candidatura registrada.

### RN-009 — Contato direto
O discente pode obter oportunidade por contato direto com a concedente.

### RN-010 — Extensão e pesquisa
Atividades de programas/projetos de extensão e pesquisa podem compor estágio quando compatíveis com a formação e regras do curso.

### RN-011 — Empresa Júnior
A FACSI admite estágio por atividades na Empresa Júnior vinculada à Faculdade.

### RN-012 — Jornada simultânea
A soma dos estágios obrigatórios e não obrigatórios realizados simultaneamente não pode ultrapassar, como regra geral, **6 horas diárias e 30 horas semanais**.

### RN-013 — Dois estágios não obrigatórios
É permitida a acumulação de dois estágios não obrigatórios desde que:
- a soma respeite 6 horas diárias;
- os horários não coincidam;
- não coincidam com o turno letivo;
- ambos sejam compatíveis com o curso.

### RN-014 — Exceção de até 40 horas
Curso que alterne teoria e prática pode permitir jornada superior a 30 e até 40 horas semanais quando atendidas as condições previstas no PPC e na norma vigente.

### RN-015 — Não obrigatório exige contrapartida financeira
Estágio não obrigatório sem contrapartida financeira configura transgressão legal.

### RN-016 — Obrigatório pode ser remunerado
O estágio obrigatório não é definido pela presença ou ausência de remuneração. O vínculo pode prever remuneração conforme as condições formalizadas.

### RN-017 — Termo de Compromisso
O Termo de Compromisso é obrigatório para formalização e não pode ser assinado retroativamente.

### RN-018 — Plano de Atividades
Todo estágio deve possuir Plano de Atividades compatível com a formação.

### RN-019 — Conteúdo mínimo do Plano
O Plano deve contemplar, direta ou indiretamente:
- dados do discente;
- dados da concedente;
- período;
- carga horária semanal;
- carga horária total;
- cronograma detalhado das atividades.

### RN-020 — Prorrogação
Na prorrogação do estágio, deve existir novo Plano de Atividades validado e anexado ao Termo Aditivo.

### RN-021 — Supervisor
A concedente deve dispor de profissional da área ou com experiência compatível para supervisão.

### RN-022 — Limite do Supervisor
Supervisor acompanha no máximo **10 estudantes simultaneamente**, salvo regra específica mais restritiva aplicável a determinado cenário.

### RN-023 — Orientador
O estágio possui orientação acadêmica conforme a organização do curso; na modelagem atual, Orientador é Professor.

### RN-024 — Seguro
O estagiário deve estar coberto por seguro contra acidentes pessoais antes do início, e o número da apólice deve constar no Termo.

### RN-025 — Responsabilidade pelo seguro
- estágio não obrigatório: responsabilidade da Concedente;
- estágio obrigatório: responsabilidade da Unifesspa, conforme Resolução 921/2025.

### RN-026 — Frequência
O aluno deve registrar frequência e o Supervisor deve acompanhar/atestar esse registro.

### RN-027 — Relatórios
O estagiário deve elaborar relatórios e submetê-los aos responsáveis acadêmicos e de supervisão conforme o fluxo institucional.

### RN-028 — Encerramento preserva histórico
Estágio encerrado ou cancelado não deve ser excluído do histórico.

## Em validação

### RV-001 — Quantidade de oportunidades
Definir se uma única Vaga cadastrada pode representar várias oportunidades simultâneas ou se cada oportunidade será um registro.

### RV-002 — Supervisor previsto na Vaga
Definir se o sistema precisa registrar supervisor já na Vaga ou somente no Estágio formalizado.

### RV-003 — Origem do Estágio
Validar se `OrigemEstagio` como enum é suficiente ou se extensão/pesquisa devem virar relacionamentos específicos.

### RV-004 — Pendências
Confirmar quais pendências impedem novo estágio ou encerramento.

### RV-005 — Troca de responsáveis
Confirmar o fluxo de troca de Supervisor ou Orientador e a necessidade de histórico específico.
