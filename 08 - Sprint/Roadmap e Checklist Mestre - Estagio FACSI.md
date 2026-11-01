# Roadmap e Checklist Mestre — Estágio FACSI

## Visão geral

> Estado do projeto: implementação Java avançada.
>
> As Sprints 01, 02 e 03 estão concluídas. As Sprints 01 a 04 estão concluídas. A Sprint 05 está em andamento, com refinamentos Java versionados e UML final em PlantUML criada; 48 testes passam.

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
**Status:** ✅ Concluída

#### Parte 1 — Carga horária e simultaneidade
- [x] JUnit 5 configurado
- [x] 15 testes criados
- [x] cálculo de horas por data
- [x] cálculo de horas por semana
- [x] limite diário
- [x] limite semanal
- [x] sobreposição de períodos
- [x] uso de dataFimReal
- [x] estágios simultâneos
- [x] estágios sem sobreposição
- [x] dois não obrigatórios simultâneos
- [x] três não obrigatórios simultâneos
- [x] três não obrigatórios que nunca coincidem ao mesmo tempo

#### Parte 2 — Formalização e encerramento
- [x] 17 testes criados
- [x] início sem documentos
- [x] externo sem convênio
- [x] interno sem convênio
- [x] início sem âmbito
- [x] não obrigatório sem bolsa
- [x] não obrigatório sem auxílio-transporte
- [x] não obrigatório válido
- [x] iniciar() válido e inválido
- [x] encerramento obrigatório com menos de 170h
- [x] encerramento sem relatório
- [x] encerramento sem avaliação
- [x] avaliação não aprovada
- [x] encerramento válido
- [x] encerrar(null)
- [x] dataFimReal registrada corretamente

#### Resultado
- [x] 32 testes executados
- [x] 32 aprovados
- [x] 0 falhas
- [x] 0 erros
- [x] 0 ignorados
- [x] mvn test — BUILD SUCCESS
- [x] mvn compile — BUILD SUCCESS
- [x] nenhum bug de produção encontrado
- [x] commit
- [x] push

### Pontos para refinamento
- [ ] avaliar inconsistência remunerado=false com valor de bolsa preenchido
- [ ] avaliar teste específico para bolsa marcada como remunerada com valor zero
- [ ] validar coerência de dataFimReal com início e último registro
- [ ] substituir resultado textual da avaliação por enum quando formalizado

---

### Sprint 05 — Refinamento e UML final
**Status:** 🟡 Em andamento

- [x] Comparar código com UML
- [x] Atualizar Pessoa / Profissional
- [x] Adicionar AmbitoEstagio
- [x] Adicionar Frequência, Relatório e Avaliação
- [x] Revisar validadores e responsabilidades
- [x] Revisar cardinalidades
- [x] Revisar enums
- [x] Revisar pendências técnicas registradas
- [ ] Incorporar feedback do professor
- [x] Gerar UML final
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

1. versionar os refinamentos da Sprint 05;
2. atualizar o PlantUML com o código consolidado;
3. revisar cardinalidades e gerar a UML final.

## Fora por enquanto

- Spring Boot
- JPA / Hibernate
- banco de dados
- API REST
- frontend
- autenticação
- Docker
