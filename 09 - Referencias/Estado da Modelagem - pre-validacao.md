# Estado da Modelagem — pré-validação com o professor

## Confirmado por norma/documentação

- Concedentes externas utilizam Convênio com a Unifesspa.
- Vigência do Convênio entre 1 e 5 anos.
- Estágio pode ocorrer por contato direto com concedente.
- Atividades de extensão, pesquisa e Empresa Júnior podem compor fluxos de estágio conforme o regulamento.
- Estágio não obrigatório exige contraprestação/bolsa e auxílio-transporte.
- Jornada de ensino superior segue, como regra geral, 6h/dia e 30h/semana.
- Estágio exige supervisão, orientação acadêmica, Termo de Compromisso, Plano de Atividades e seguro.
- Plano de Atividades pode evoluir por aditivos ao Termo.
- Supervisor é indicado pela concedente e deve possuir formação ou experiência compatível.
- Supervisor pode acompanhar até 10 estagiários simultaneamente.

## Sustentado pela reunião com o professor Hugo

- O sistema deve modelar dados estruturados, não apenas armazenar PDFs.
- Convênios precisam preservar vigência e histórico.
- Vaga, Candidatura e Estágio devem ser conceitos distintos.
- Supervisor pode ser informado já no contexto da vaga.
- Estágio pode ocorrer dentro da própria universidade.
- Em casos internos, uma mesma pessoa pode exercer supervisão e orientação.
- O modelo deve contemplar múltiplos vínculos e controle de carga horária.

## Decisão de modelagem

- Pessoa é superclasse de Aluno e Professor.
- Supervisor é papel de Pessoa.
- Orientador é Professor.
- Candidatura é entidade associativa entre Aluno e Vaga.
- Estágio é a entidade central.
- Vaga e Candidatura são opcionais na origem do Estágio.
- Estágio referencia diretamente a Concedente e, quando aplicável, o Convênio usado.
- OrigemEstagio permanece como enum na versão pré-validação.
- Modalidade permanece registrada no Estágio para representar o vínculo formalizado.

## Pendente de validação institucional

- Uma Vaga pode ter várias posições?
- Supervisor previsto na Vaga precisa ser o mesmo do Estágio?
- Como registrar troca de Supervisor/Orientador?
- Como a FACSI trata soma de carga horária de múltiplos estágios simultâneos?
- Como o Orientador é escolhido?
- Quais alterações além do Plano de Atividades geram aditivo?
- Existem restrições adicionais do Convênio por campus/unidade/modalidade?
- Quais pendências impedem encerramento ou abertura de novo estágio?

## Status

Modelo pronto para apresentação e validação com o professor Hugo.

Ainda não é a UML final da disciplina: ela é a versão **pré-validação**.
