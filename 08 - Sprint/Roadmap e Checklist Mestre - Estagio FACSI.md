# Roadmap e Checklist Mestre — Estágio FACSI

## Visão geral

> Estado do projeto: implementação Java em andamento.
>
> As Sprints 01 e 02 estão concluídas. A Sprint 03 está em andamento, com a Parte 1 já concluída e versionada.

---

## Linha do tempo

### Sprint 01 — Domínio central
**Status:** ✅ Concluída

- [x] Regulamentos e documentos analisados
- [x] Domínio central modelado
- [x] UML candidata a final
- [x] Estrutura Java inicial
- [x] Pessoa / Aluno / Professor / Profissional
- [x] Concedente / Convênio
- [x] Vaga / Candidatura
- [x] Estágio
- [x] Termo / Plano / Seguro
- [x] Build e execução
- [x] Commit e push

**Pendência acadêmica:**
- [ ] Validar pontos operacionais com o professor Hugo
- [ ] Aplicar ajustes finais no UML, caso necessário

---

### Sprint 02 — Acompanhamento e encerramento
**Status:** ✅ Concluída

#### Parte 1 — Frequência
- [x] RegistroFrequencia
- [x] Soma de horas realizadas
- [x] Cenário no Main
- [x] Build e execução
- [x] Commit e push

#### Parte 2 — Relatório e avaliação
- [x] RelatorioFinal
- [x] AvaliacaoEstagio
- [x] Relações com Estagio
- [x] Cenário no Main
- [x] Build e execução
- [x] Commit e push

---

### Sprint 03 — Regras de negócio
**Status:** 🟡 Em andamento

#### Parte 1 — Carga horária e simultaneidade
**Status:** ✅ Concluída

- [x] Validar limite geral de 6h/dia
- [x] Validar limite geral de 30h/semana
- [x] Somar registros do mesmo dia
- [x] Validar estágios simultâneos
- [x] Considerar sobreposição real de períodos
- [x] Tratar até dois estágios não obrigatórios simultâneos
- [x] Criar ValidadorCargaHoraria
- [x] Criar cenários válidos e inválidos no Main
- [x] Build e execução
- [x] Commit e push
- [ ] Definir horas fracionadas em etapa futura
- [ ] Confirmar com professor caso de semana de transição entre estágios sem sobreposição

#### Parte 2 — Formalização e encerramento
**Status:** ⬜ Não iniciada

- [ ] Validar Termo antes de estágio ativo
- [ ] Validar Plano de Atividades
- [ ] Validar Seguro
- [ ] Validar Convênio quando aplicável
- [ ] Validar contrapartida financeira do não obrigatório
- [ ] Definir podeIniciar()
- [ ] Definir podeEncerrar()
- [ ] Avaliar carga horária mínima obrigatória da FACSI
- [ ] Definir transições de status
- [ ] Revisar status em String que merecem enum
- [ ] Criar cenários válidos e inválidos no Main
- [ ] Build e execução
- [ ] Commit e push

---

### Sprint 04 — Testes automatizados
**Status:** ⬜ Não iniciada

- [ ] Adicionar JUnit
- [ ] Testar cálculo de horas
- [ ] Testar limite diário
- [ ] Testar limite semanal
- [ ] Testar estágios simultâneos
- [ ] Testar formalização
- [ ] Testar não obrigatório sem contrapartida
- [ ] Testar encerramento válido
- [ ] Testar cenários inválidos
- [ ] Executar com mvn test

---

### Sprint 05 — Refinamento e UML final
**Status:** ⬜ Não iniciada

- [ ] Comparar código com UML
- [ ] Atualizar Pessoa / Profissional
- [ ] Adicionar Frequência, Relatório e Avaliação ao UML
- [ ] Adicionar regras/serviços auxiliares relevantes
- [ ] Revisar cardinalidades
- [ ] Revisar enums
- [ ] Incorporar feedback do professor
- [ ] Gerar UML final
- [ ] Gerar imagem final do diagrama

---

### Sprint 06 — Entrega e apresentação
**Status:** ⬜ Não iniciada

- [ ] Revisar README
- [ ] Organizar documentação final
- [ ] Garantir build limpo
- [ ] Garantir testes passando
- [ ] Preparar cenário demonstrável
- [ ] Preparar explicação de OO
- [ ] Preparar explicação das regras
- [ ] Preparar roteiro de apresentação
- [ ] Revisar código antes da entrega

---

## Próxima ação imediata

1. iniciar Sprint 03 — Parte 2;
2. implementar formalização e encerramento;
3. validar cenários no Main;
4. revisar antes do commit.

## Fora por enquanto

- Spring Boot
- JPA / Hibernate
- banco de dados
- API REST
- frontend
- autenticação
- Docker
