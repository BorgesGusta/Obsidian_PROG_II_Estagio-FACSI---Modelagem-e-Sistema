# Auditoria dos documentos reais do estágio

## Documentos analisados

- Termo de Compromisso FACSI 2022
- Plano de Atividades FACSI 2022
- Registro de Frequência FACSI 2022
- Relatório Final FACSI 2022
- Apólice institucional de acidentes pessoais
- Regulamento FACSI 01/2022
- Resolução CONSEPE 921/2025

## Descobertas com impacto direto na modelagem

### 1. Norma geral vigente

A Resolução CONSEPE 921/2025 revogou a Resolução 016/2014.

Portanto, referências à 016/2014 devem ser consideradas históricas e substituídas pela 921/2025 como base geral atual.

### 2. Múltiplos estágios

A norma atual resolve a dúvida:
- a soma dos estágios simultâneos conta para o limite;
- regra geral: 6h/dia e 30h/semana;
- dois não obrigatórios podem coexistir se cumprirem as condições da norma.

### 3. Modalidade e remuneração são dimensões diferentes

O Termo FACSI possui cláusulas para estágio remunerado e não remunerado.

A Resolução 921/2025 proíbe estágio não obrigatório sem contrapartida financeira.

Consequência:
- obrigatório pode ser remunerado ou não;
- não obrigatório deve possuir contrapartida financeira;
- Vaga registra valores ofertados;
- Termo registra valores efetivamente pactuados.

### 4. Plano de Atividades possui ciclo próprio

O Plano real contém:
- dados acadêmicos;
- Professor Orientador;
- Concedente;
- Supervisor;
- período;
- carga semanal e total;
- área de atuação;
- justificativa;
- objetivos;
- atividades;
- adequação pedagógica;
- cronograma.

A Resolução 921/2025 confirma que prorrogação exige novo Plano anexado ao Termo Aditivo.

Consequência:
`Estagio 1 ---- 0..* PlanoAtividades`

### 5. Seguro institucional coletivo

A apólice analisada tem a Unifesspa como estipulante e contempla estagiários dentro de seguro coletivo.

Consequência:
não modelar uma apólice individual obrigatória para cada estágio.

### 6. Frequência

O Registro de Frequência contém:
- aluno;
- local/empresa;
- Supervisor;
- data;
- horário;
- descrição da atividade;
- assinatura do Supervisor;
- total.

Isso confirma uma futura entidade/estrutura de acompanhamento, deixada para a Sprint 02.

### 7. Relatório Final

O modelo FACSI contém:
- tema/objeto;
- justificativa;
- objetivos;
- metodologia;
- atividades realizadas;
- dificuldades;
- conclusão;
- referências.

Também fica para a Sprint 02, pois não é necessário para fechar o núcleo do vínculo.

## Resultado

A Sprint 01 mantém foco no núcleo de formalização.

Frequência, Relatório Final, avaliação e encerramento detalhado ficam documentados como próximos módulos, sem inflar a UML central.
