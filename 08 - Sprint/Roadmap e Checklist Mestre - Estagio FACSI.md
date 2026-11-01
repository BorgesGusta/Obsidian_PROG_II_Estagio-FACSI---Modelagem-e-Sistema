# Roadmap e Checklist Mestre — Estágio FACSI

## Visão geral

> Estado do projeto: implementação Java avançada.
>
> As Sprints 01, 02 e 03 estão concluídas. A Sprint 04 está em andamento, com a Parte 1 de testes automatizados concluída localmente e aguardando versionamento.

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

- [x] Registro de frequência
- [x] Soma de horas
- [x] Relatório final
- [x] Avaliação do estágio
- [x] Cenários no Main
- [x] Build e execução
- [x] Commits e push

---

### Sprint 03 — Regras de negócio
**Status:** ✅ Concluída

- [x] 6h/dia e 30h/semana
- [x] simultaneidade e sobreposição de períodos
- [x] limite de dois não obrigatórios simultâneos
- [x] formalização por Termo, Plano, Seguro e Convênio
- [x] AmbitoEstagio
- [x] bolsa e auxílio-transporte no não obrigatório
- [x] iniciar() e encerrar(LocalDate)
- [x] carga mínima de 170h no obrigatório
- [x] dataFimReal
- [x] ValidadorCargaHoraria e ValidadorEstagio
- [x] Build e execução
- [x] Commits e push

### Decisões adiadas
- [ ] horas fracionadas
- [ ] comparação de Aluno por equals/id
- [ ] exceção de até 40h
- [ ] cancelamento de estágio
- [ ] restrições de alteração do âmbito após início
- [ ] enum para resultado da avaliação
- [ ] semana de transição entre estágios não sobrepostos
- [ ] reduzir dependência entre model e regras, se necessário

---

### Sprint 04 — Testes automatizados
**Status:** 🟡 Em andamento

#### Parte 1 — Carga horária e simultaneidade
**Status:** 🟡 Implementada localmente, aguardando commit

- [x] Adicionar JUnit 5
- [x] Testar cálculo de horas por data
- [x] Testar cálculo de horas por semana
- [x] Testar limite diário
- [x] Testar limite semanal
- [x] Testar sobreposição de períodos
- [x] Testar uso de dataFimReal
- [x] Testar estágios simultâneos
- [x] Testar estágios sem sobreposição
- [x] Testar dois não obrigatórios simultâneos
- [x] Testar três não obrigatórios simultâneos
- [x] Testar três não obrigatórios que nunca coincidem ao mesmo tempo
- [x] Executar 15 testes com sucesso
- [x] mvn test — BUILD SUCCESS
- [x] mvn compile — BUILD SUCCESS
- [ ] Commit
- [ ] Push

#### Parte 2 — Formalização e encerramento
**Status:** ⬜ Não iniciada

- [ ] Testar início sem documentos
- [ ] Testar início externo sem convênio
- [ ] Testar início interno sem convênio
- [ ] Testar início sem âmbito
- [ ] Testar não obrigatório sem bolsa
- [ ] Testar não obrigatório sem auxílio-transporte
- [ ] Testar não obrigatório válido
- [ ] Testar encerramento com menos de 170h
- [ ] Testar encerramento sem relatório
- [ ] Testar encerramento sem avaliação
- [ ] Testar avaliação não aprovada
- [ ] Testar encerramento válido
- [ ] Testar registro de dataFimReal
- [ ] Executar mvn test
- [ ] Commit e push

---

### Sprint 05 — Refinamento e UML final
**Status:** ⬜ Não iniciada

- [ ] Comparar código com UML
- [ ] Atualizar Pessoa / Profissional
- [ ] Adicionar AmbitoEstagio
- [ ] Adicionar Frequência, Relatório e Avaliação
- [ ] Representar validadores quando fizer sentido
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
- [ ] Simplificar Main para demonstração
- [ ] Preparar cenário demonstrável
- [ ] Preparar explicação de OO
- [ ] Preparar explicação das regras
- [ ] Preparar roteiro de apresentação
- [ ] Revisar código antes da entrega

---

## Próxima ação imediata

1. versionar a Sprint 04 — Parte 1;
2. iniciar testes de formalização e encerramento;
3. executar mvn test;
4. revisar antes do commit final da Sprint 04.

## Fora por enquanto

- Spring Boot
- JPA / Hibernate
- banco de dados
- API REST
- frontend
- autenticação
- Docker
