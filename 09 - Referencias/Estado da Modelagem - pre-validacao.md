# Estado da Modelagem — pré-validação com o professor

## Base normativa vigente

A base geral principal passa a ser a **Resolução CONSEPE nº 921/2025**, que revogou a Resolução nº 016/2014.

O Regulamento FACSI 01/2022 continua sendo utilizado para as regras específicas do curso quando compatível com a norma geral vigente.

## Confirmado

- Convênio externo com vigência de 1 a 5 anos.
- Termo obrigatório e sem assinatura retroativa.
- Plano de Atividades acompanha o Termo.
- Prorrogação gera novo Plano anexado a Termo Aditivo.
- Seguro antes do início.
- Não obrigatório: seguro pela Concedente.
- Obrigatório: seguro pela Unifesspa.
- Não obrigatório sem contrapartida financeira é irregular.
- Modalidade e remuneração são conceitos diferentes.
- Limite geral de 6h/dia e 30h/semana considera o somatório dos estágios simultâneos.
- Dois estágios não obrigatórios podem coexistir nas condições da Resolução 921/2025.
- Supervisor acompanha até 10 estudantes simultaneamente na regra geral.
- Estágio pode ter origem em contato direto, extensão e pesquisa.
- Registro de frequência e relatórios fazem parte do acompanhamento.

## Evidência dos documentos FACSI

Os anexos usados no fluxo real confirmam:
- Termo com dados de Concedente, aluno, Supervisor, Orientador, jornada, período, remuneração/auxílio e apólice;
- Plano com aluno, Professor Orientador, empresa/instituição, Supervisor, período, carga semanal/total, área, justificativa, objetivos, atividades, adequação pedagógica e cronograma;
- Registro de Frequência com data, horário, atividade e assinatura do Supervisor;
- Relatório Final com tema, justificativa, objetivos, metodologia, atividades realizadas, dificuldades, conclusão e referências.

## Decisões de modelagem

- Estágio é a entidade central.
- Vaga e Candidatura são origens opcionais.
- Supervisor é papel exercido por Pessoa.
- Orientador é Professor.
- Estágio referencia Concedente e Convênio quando aplicável.
- Condições financeiras efetivas ficam no Termo.
- Plano passa a ser `0..*` por Estágio para preservar prorrogações/novos planos.
- Apólice permanece muitos-para-muitos com Estágio.

## Pendente

- Forma de cadastro de múltiplas oportunidades na mesma Vaga.
- Momento de definição do Supervisor.
- Forma de escolha do Orientador.
- Pendências que bloqueiam abertura/encerramento.
- Fluxo de troca de responsáveis.
- Outras situações de Termo Aditivo.
- Detalhamento de origem para extensão/pesquisa.
