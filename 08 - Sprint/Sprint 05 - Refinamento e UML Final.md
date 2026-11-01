# Sprint 05 — Refinamento e UML Final

## Status

🟡 Em andamento

## Objetivo

Comparar a modelagem candidata da Sprint 01 com o código Java consolidado nas Sprints 02–04, corrigir apenas inconsistências relevantes e produzir a UML final.

## Etapa 1 — Auditoria estrutural

- [x] Comparar Pessoa, Aluno e Professor
- [x] Identificar Profissional ausente na UML candidata
- [x] Comparar Estagio e enums principais
- [x] Identificar AmbitoEstagio ausente na UML candidata
- [x] Identificar RegistroFrequencia ausente
- [x] Identificar RelatorioFinal ausente
- [x] Identificar AvaliacaoEstagio ausente
- [x] Comparar Concedente, Convenio, Vaga e Candidatura
- [x] Comparar TermoCompromisso, PlanoAtividades e ApoliceSeguro
- [x] Identificar ValidadorCargaHoraria e ValidadorEstagio como classes de regras

## Etapa 2 — Auditoria de comportamento

- [ ] Revisar iniciar()
- [ ] Revisar encerrar(LocalDate)
- [ ] Revisar regras de 6h/dia e 30h/semana
- [ ] Revisar simultaneidade e sobreposição
- [ ] Revisar regra de dois não obrigatórios
- [ ] Revisar formalização por Termo, Plano, Seguro e Convênio
- [ ] Revisar carga mínima de 170h
- [ ] Revisar remuneração do não obrigatório
- [ ] Revisar coerência de dataFimReal

## Etapa 3 — Classificação das diferenças

Cada diferença será marcada como:

- MANTER — código e modelo estão adequados;
- AJUSTAR UML — o código evoluiu e a UML ficou para trás;
- AJUSTAR JAVA — há inconsistência relevante no domínio;
- VALIDAR COM PROFESSOR — depende de regra operacional não documentada;
- MELHORIA FUTURA — não precisa entrar na entrega atual.

## Etapa 4 — Pontos já identificados

### Ajustar UML
- [ ] adicionar Profissional como subclasse de Pessoa
- [ ] adicionar AmbitoEstagio
- [ ] adicionar RegistroFrequencia
- [ ] adicionar RelatorioFinal
- [ ] adicionar AvaliacaoEstagio
- [ ] atualizar Estagio com ambito
- [ ] representar iniciar() e encerrar() se o diagrama final mostrar comportamento
- [ ] decidir como representar ValidadorCargaHoraria e ValidadorEstagio

### Avaliar antes de alterar Java
- [ ] dataFimReal aceita qualquer data não nula
- [ ] resultado da avaliação ainda é String
- [ ] estados textuais de Convenio, Vaga, Candidatura, Termo e Plano
- [ ] setters permitem alterar dados estruturais após o estágio iniciar
- [ ] validade de Convênio/Seguro é modelada por datas, mas o início atualmente verifica apenas existência
- [ ] consistência entre remunerado e valorRemuneracao

### Validar com professor
- [ ] semana de transição entre estágios não sobrepostos
- [ ] momento de definição do Supervisor
- [ ] escolha do Orientador
- [ ] troca de Supervisor/Orientador
- [ ] outras alterações que exigem Termo Aditivo

## Etapa 5 — UML final

- [ ] definir escopo do diagrama final
- [ ] atualizar entidades, atributos e enums
- [ ] revisar cardinalidades
- [ ] revisar herança e papéis
- [ ] revisar dependências das classes de regras
- [ ] gerar PlantUML final
- [ ] validar consistência com o código
- [ ] gerar imagem final

## Definição de pronto

A Sprint 05 termina quando:

- o código e a UML não tiverem divergências estruturais relevantes;
- as decisões de refinamento estiverem registradas;
- as dúvidas que dependem do professor estiverem separadas;
- a UML final estiver gerada e revisada;
- os 32 testes continuarem passando após qualquer refinamento de código.
