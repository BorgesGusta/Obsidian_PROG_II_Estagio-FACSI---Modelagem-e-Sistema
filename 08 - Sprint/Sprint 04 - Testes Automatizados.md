# Sprint 04 — Testes Automatizados

## Status

🟡 Em andamento

## Objetivo

Transformar as regras já implementadas em verificações automáticas com JUnit 5.

## Parte 1 — Carga horária e simultaneidade

**Status:** 🟡 Implementada localmente, aguardando versionamento

### Estrutura
- [x] adicionar JUnit 5 ao pom.xml
- [x] criar ValidadorCargaHorariaTest
- [x] criar EstagioTest

### ValidadorCargaHorariaTest
- [x] 6h no mesmo dia
- [x] 7h no mesmo dia
- [x] 30h na semana
- [x] 36h na semana
- [x] soma de estágios com sobreposição
- [x] estágios sem sobreposição
- [x] dois não obrigatórios simultâneos
- [x] três não obrigatórios simultâneos
- [x] três não obrigatórios sem três simultâneos

### EstagioTest
- [x] soma de registros da mesma data
- [x] soma de registros da mesma semana
- [x] períodos sobrepostos
- [x] períodos separados
- [x] fronteira inclusiva
- [x] dataFimReal substitui dataFimPrevista

### Resultado
- [x] 15 testes executados
- [x] 15 aprovados
- [x] 0 falhas
- [x] 0 erros
- [x] mvn test — BUILD SUCCESS
- [x] mvn compile — BUILD SUCCESS
- [ ] commit
- [ ] push

## Parte 2 — Formalização e encerramento

**Status:** ⬜ Não iniciada

- [ ] ValidadorEstagioTest
- [ ] início sem documentos
- [ ] externo sem convênio
- [ ] interno sem convênio
- [ ] início sem âmbito
- [ ] não obrigatório sem bolsa
- [ ] não obrigatório sem auxílio-transporte
- [ ] não obrigatório válido
- [ ] obrigatório com menos de 170h
- [ ] sem relatório
- [ ] sem avaliação
- [ ] avaliação não aprovada
- [ ] encerramento válido
- [ ] dataFimReal
- [ ] mvn test
- [ ] commit
- [ ] push

## Pontos de atenção

- A semana de transição entre estágios sem sobreposição permanece como regra pendente de validação acadêmica.
- Os testes de carga criam estágios ativos por meio de iniciar(), respeitando o fluxo atual do domínio. Esse acoplamento é aceitável nesta fase, mas pode ser refinado se a criação de fixtures ficar difícil no futuro.
