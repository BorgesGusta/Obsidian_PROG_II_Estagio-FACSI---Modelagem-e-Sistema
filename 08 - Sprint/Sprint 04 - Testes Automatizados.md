# Sprint 04 — Testes Automatizados

## Status

✅ Concluída

## Objetivo

Transformar as regras implementadas em verificações automáticas com JUnit 5.

## Parte 1 — Carga horária e simultaneidade

**Status:** ✅ Concluída

- [x] JUnit 5 no pom.xml
- [x] ValidadorCargaHorariaTest
- [x] EstagioTest
- [x] 15 testes
- [x] limite diário
- [x] limite semanal
- [x] cálculo por data e semana
- [x] sobreposição de períodos
- [x] dataFimReal
- [x] simultaneidade
- [x] dois e três não obrigatórios

## Parte 2 — Formalização e encerramento

**Status:** ✅ Concluída

- [x] ValidadorEstagioTest
- [x] 17 testes
- [x] início sem documentos
- [x] externo sem convênio
- [x] interno sem convênio
- [x] sem âmbito
- [x] não obrigatório sem bolsa
- [x] não obrigatório sem auxílio-transporte
- [x] não obrigatório válido
- [x] iniciar() válido
- [x] iniciar() inválido
- [x] menos de 170h
- [x] sem relatório
- [x] sem avaliação
- [x] avaliação não aprovada
- [x] encerramento válido
- [x] encerrar(null)
- [x] encerramento inválido sem alterar estado
- [x] dataFimReal registrada

## Resultado geral

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

## Pontos de atenção para refinamento

- Semana de transição entre estágios sem sobreposição continua pendente de validação acadêmica.
- remunerado=false com valor de bolsa preenchido representa um estado inconsistente ainda não tratado.
- Bolsa marcada como remunerada com valor zero já é rejeitada, mas não possui teste específico.
- dataFimReal ainda aceita qualquer data não nula; falta decidir se deve ser posterior ao início e coerente com a última frequência.
- Resultado da avaliação ainda é String e usa comparação exata com APROVADO.
- Os testes de carga criam estágio ativo por iniciar(), respeitando o fluxo do domínio atual.
