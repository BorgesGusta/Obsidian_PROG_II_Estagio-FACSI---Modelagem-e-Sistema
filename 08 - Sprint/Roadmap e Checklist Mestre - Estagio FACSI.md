# Roadmap e Checklist Mestre — Estágio FACSI

## Visão geral

> Estado do projeto: implementação Java em andamento.
>
> A modelagem central e a Sprint 01 estão concluídas internamente. A validação final com o professor Hugo continua como pendência acadêmica, mas não bloqueia o avanço técnico.

---

## Linha do tempo

### Sprint 01 — Domínio central
**Status:** ✅ Concluída internamente

Objetivo: transformar regulamentos, documentos reais e explicações do professor em um modelo orientado a objetos consistente.

- [x] Analisar Regulamento FACSI 2022
- [x] Analisar Resolução CONSEPE 921/2025
- [x] Confirmar revogação da Resolução 016/2014
- [x] Analisar Termo de Compromisso
- [x] Analisar Plano de Atividades
- [x] Analisar Ficha de Frequência
- [x] Analisar Relatório Final
- [x] Analisar apólice institucional
- [x] Modelar Pessoa, Aluno e Professor
- [x] Criar Profissional para representar supervisor externo
- [x] Modelar Concedente e Convênio
- [x] Modelar Vaga e Candidatura
- [x] Modelar Estágio como entidade central
- [x] Modelar Termo de Compromisso
- [x] Modelar Plano de Atividades
- [x] Modelar Apólice de Seguro
- [x] Separar modalidade de remuneração
- [x] Representar origem opcional por Vaga/Candidatura
- [x] Criar UML candidata a final
- [x] Implementar estrutura inicial em Java
- [x] Compilar e executar cenário de demonstração
- [x] Commit Java: estrutura inicial do sistema de estágios

**Pendência externa:**
- [ ] Validar pontos operacionais com o professor Hugo
- [ ] Aplicar ajustes finais no UML, caso o professor solicite

---

### Sprint 02 — Acompanhamento e encerramento
**Status:** 🟡 Em andamento

#### Parte 1 — Frequência e acompanhamento
**Status:** ✅ Concluída

- [x] Criar RegistroFrequencia
- [x] Relacionar registros ao Estagio
- [x] Criar lista de registros no Estagio
- [x] Criar adicionarRegistroFrequencia(...)
- [x] Criar calcularHorasRealizadas()
- [x] Atualizar Main
- [x] Compilar
- [x] Executar cenário
- [x] Commit Java: registro de frequência do estágio

#### Parte 2 — Relatório e avaliação
**Status:** 🟡 Implementada localmente, aguardando commit

- [x] Criar RelatorioFinal
- [x] Criar AvaliacaoEstagio
- [x] Relacionar RelatorioFinal ao Estagio
- [x] Relacionar AvaliacaoEstagio ao Estagio
- [x] Atualizar Main
- [x] Ajustar cenário para Estagio ATIVO
- [x] Compilar
- [x] Executar cenário sem exceções
- [ ] Revisar diff final
- [ ] Fazer commit da Parte 2
- [ ] Fazer push
- [ ] Marcar Sprint 02 como concluída

---

### Sprint 03 — Regras de negócio
**Status:** ⬜ Não iniciada

#### Parte 1 — Carga horária e simultaneidade
- [ ] Validar limite geral de 6h/dia
- [ ] Validar limite geral de 30h/semana
- [ ] Somar registros do mesmo dia
- [ ] Avaliar horas fracionadas
- [ ] Validar estágios simultâneos
- [ ] Tratar regra dos dois estágios não obrigatórios
- [ ] Criar métodos de validação claros
- [ ] Atualizar Main com cenários válidos e inválidos

#### Parte 2 — Formalização e encerramento
- [ ] Validar Termo antes de estágio ativo
- [ ] Validar Plano de Atividades
- [ ] Validar Seguro
- [ ] Validar Convênio quando aplicável
- [ ] Validar contrapartida financeira do não obrigatório
- [ ] Definir condição para encerramento
- [ ] Avaliar carga horária mínima obrigatória da FACSI
- [ ] Definir transições de status
- [ ] Revisar enums/status em String

---

### Sprint 04 — Testes automatizados
**Status:** ⬜ Não iniciada

- [ ] Adicionar JUnit
- [ ] Testar cálculo de horas
- [ ] Testar limite diário
- [ ] Testar limite semanal
- [ ] Testar estágios simultâneos
- [ ] Testar documentação obrigatória
- [ ] Testar estágio não obrigatório sem contrapartida
- [ ] Testar encerramento válido
- [ ] Testar cenários inválidos
- [ ] Executar com mvn test

---

### Sprint 05 — Refinamento e UML final
**Status:** ⬜ Não iniciada

- [ ] Comparar código com UML
- [ ] Atualizar Pessoa / Profissional
- [ ] Adicionar Frequência, Relatório e Avaliação ao UML
- [ ] Revisar cardinalidades
- [ ] Revisar associações bidirecionais
- [ ] Revisar enums
- [ ] Revisar responsabilidades das classes
- [ ] Incorporar feedback do professor
- [ ] Gerar UML final
- [ ] Gerar imagem final do diagrama

---

### Sprint 06 — Entrega e apresentação
**Status:** ⬜ Não iniciada

- [ ] Revisar README do repositório Java
- [ ] Organizar documentação final
- [ ] Garantir build limpo
- [ ] Garantir testes passando
- [ ] Preparar cenário demonstrável
- [ ] Preparar explicação do domínio
- [ ] Preparar explicação de OO
- [ ] Preparar explicação das regras
- [ ] Preparar roteiro de apresentação
- [ ] Revisar código antes da entrega

---

## Próxima ação imediata

1. revisar alterações locais da Sprint 02 — Parte 2;
2. fazer commit e push;
3. marcar Sprint 02 como concluída;
4. iniciar Sprint 03 — Parte 1: carga horária e simultaneidade.

---

## Assuntos que ficam fora por enquanto

- Spring Boot
- JPA / Hibernate
- banco de dados
- API REST
- frontend
- autenticação
- Docker

Só entram se forem necessários para a disciplina ou solicitados pelo professor.
