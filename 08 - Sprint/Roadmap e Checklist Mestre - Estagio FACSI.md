# Roadmap e Checklist Mestre — Estágio FACSI

## Visão geral

> Estado do projeto: implementação Java avançada.
>
> As Sprints 01, 02 e 03 estão concluídas. A próxima etapa é a Sprint 04, dedicada a testes automatizados.

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

#### Parte 1 — Carga horária e simultaneidade
- [x] Limite de 6h/dia
- [x] Limite de 30h/semana
- [x] Soma de registros no mesmo dia
- [x] Cálculo semanal
- [x] Estágios simultâneos
- [x] Sobreposição real de períodos
- [x] Limite de dois não obrigatórios simultâneos
- [x] ValidadorCargaHoraria
- [x] Cenários válidos e inválidos
- [x] Build e execução
- [x] Commit e push

#### Parte 2 — Formalização e encerramento
- [x] Termo obrigatório
- [x] Plano de Atividades
- [x] Seguro
- [x] Âmbito INTERNO / EXTERNO
- [x] Convênio para estágio externo
- [x] Contrapartida do não obrigatório
- [x] Bolsa e auxílio-transporte no não obrigatório
- [x] podeIniciar()
- [x] podeEncerrar()
- [x] 170h para estágio obrigatório
- [x] Transição EM_FORMALIZACAO → ATIVO
- [x] Transição ATIVO → ENCERRADO
- [x] Data real de encerramento
- [x] Bloqueio de início sem âmbito definido
- [x] ValidadorEstagio
- [x] Cenários válidos e inválidos
- [x] Build e execução
- [x] Commit e push

### Decisões adiadas
- [ ] horas fracionadas;
- [ ] comparação de Aluno por equals/id;
- [ ] exceção de até 40h;
- [ ] cancelamento de estágio;
- [ ] restrições de alteração do âmbito após início;
- [ ] enum para resultado da avaliação;
- [ ] semana de transição entre estágios não sobrepostos;
- [ ] reduzir dependência entre model e regras, se necessário.

---

### Sprint 04 — Testes automatizados
**Status:** ⬜ Não iniciada

- [ ] Adicionar JUnit
- [ ] Testar cálculo de horas
- [ ] Testar limite diário
- [ ] Testar limite semanal
- [ ] Testar sobreposição de períodos
- [ ] Testar estágios simultâneos
- [ ] Testar limite de dois não obrigatórios
- [ ] Testar início sem documentos
- [ ] Testar início externo sem convênio
- [ ] Testar início interno sem convênio
- [ ] Testar não obrigatório sem bolsa
- [ ] Testar não obrigatório sem auxílio-transporte
- [ ] Testar início sem âmbito
- [ ] Testar encerramento com menos de 170h
- [ ] Testar encerramento válido
- [ ] Testar registro de dataFimReal
- [ ] Executar com mvn test
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

1. iniciar Sprint 04;
2. configurar JUnit;
3. transformar as regras já validadas no Main em testes automatizados;
4. executar mvn test;
5. revisar antes do commit.

## Fora por enquanto

- Spring Boot
- JPA / Hibernate
- banco de dados
- API REST
- frontend
- autenticação
- Docker
