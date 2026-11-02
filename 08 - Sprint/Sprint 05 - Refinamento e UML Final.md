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

**Status:** ✅ Concluída


- [x] Revisar iniciar()
- [x] Revisar encerrar(LocalDate)
- [x] Revisar regras de 6h/dia e 30h/semana
- [x] Revisar simultaneidade e sobreposição
- [x] Revisar regra de dois não obrigatórios
- [x] Revisar formalização por Termo, Plano, Seguro e Convênio
- [x] Revisar carga mínima de 170h
- [x] Revisar remuneração do não obrigatório
- [x] Revisar coerência de dataFimReal

## Etapa 3 — Classificação das diferenças

**Status:** ✅ Concluída


Cada diferença será marcada como:

- MANTER — código e modelo estão adequados;
- AJUSTAR UML — o código evoluiu e a UML ficou para trás;
- AJUSTAR JAVA — há inconsistência relevante no domínio;
- VALIDAR COM PROFESSOR — depende de regra operacional não documentada;
- MELHORIA FUTURA — não precisa entrar na entrega atual.

## Etapa 4 — Pontos já identificados

### Refinamentos Java concluídos
- [x] período obrigatório e válido para iniciar
- [x] convênio externo vigente na data de início
- [x] apólice vigente na data de início
- [x] dataFimReal coerente com início e última frequência
- [x] 48 testes passando
- [x] Main ajustado para dados de demonstração válidos


### Ajustar UML
- [x] adicionar Profissional como subclasse de Pessoa
- [x] adicionar AmbitoEstagio
- [x] adicionar RegistroFrequencia
- [x] adicionar RelatorioFinal
- [x] adicionar AvaliacaoEstagio
- [x] atualizar Estagio com ambito
- [x] representar iniciar() e encerrar() se o diagrama final mostrar comportamento
- [x] decidir como representar ValidadorCargaHoraria e ValidadorEstagio

### Avaliar antes de alterar Java
- [x] dataFimReal aceita qualquer data não nula — AJUSTAR JAVA
- [x] resultado da avaliação ainda é String — VALIDAR COM PROFESSOR
- [x] estados textuais de Convenio, Vaga, Candidatura, Termo e Plano — MELHORIA FUTURA
- [x] setters permitem alterar dados estruturais após o estágio iniciar — MELHORIA FUTURA
- [x] validade de Convênio/Seguro é modelada por datas, mas o início atualmente verifica apenas existência — AJUSTAR JAVA
- [x] consistência entre remunerado e valorRemuneracao — MELHORIA FUTURA

### Validar com professor
- [ ] semana de transição entre estágios não sobrepostos
- [ ] momento de definição do Supervisor
- [ ] escolha do Orientador
- [ ] troca de Supervisor/Orientador
- [ ] outras alterações que exigem Termo Aditivo

## Etapa 5 — UML final

- [x] definir escopo do diagrama final
- [x] atualizar entidades, atributos e enums
- [x] revisar cardinalidades
- [x] revisar herança e papéis
- [x] revisar dependências das classes de regras
- [x] gerar PlantUML final
- [x] validar consistência com o código
- [ ] validar visual da versão compactada
- [ ] gerar imagem final

## Definição de pronto

A Sprint 05 termina quando:

- o código e a UML não tiverem divergências estruturais relevantes;
- as decisões de refinamento estiverem registradas;
- as dúvidas que dependem do professor estiverem separadas;
- a UML final estiver gerada e revisada;
- os 48 testes continuarem passando após qualquer refinamento de código.
