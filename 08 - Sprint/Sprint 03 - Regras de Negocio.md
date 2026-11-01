# Sprint 03 — Regras de Negócio

## Status

✅ Concluída

## Objetivo

Fazer o sistema deixar de apenas armazenar dados e passar a validar regras reais de estágio.

## Parte 1 — Carga horária e simultaneidade

**Status:** ✅ Concluída

- [x] Limite diário de 6 horas
- [x] Limite semanal de 30 horas
- [x] Cálculo de horas por data
- [x] Cálculo de horas por semana
- [x] Validação de estágios simultâneos
- [x] Sobreposição de períodos
- [x] Limite de dois não obrigatórios simultâneos
- [x] ValidadorCargaHoraria
- [x] Cenários válidos e inválidos no Main
- [x] BUILD SUCCESS
- [x] Execução sem exceções
- [x] Commit realizado
- [x] Push realizado

## Parte 2 — Formalização e encerramento

**Status:** ✅ Concluída

- [x] verificar Termo
- [x] verificar Plano de Atividades
- [x] verificar Seguro
- [x] criar AmbitoEstagio
- [x] exigir Convênio para estágio EXTERNO
- [x] permitir INTERNO sem convênio externo
- [x] bloquear início sem âmbito definido
- [x] exigir bolsa e auxílio-transporte no não obrigatório
- [x] criar regra podeIniciar()
- [x] criar regra podeEncerrar()
- [x] exigir 170 horas no obrigatório
- [x] controlar início por iniciar()
- [x] controlar encerramento por encerrar(LocalDate)
- [x] registrar dataFimReal
- [x] criar cenários válidos e inválidos
- [x] BUILD SUCCESS
- [x] execução sem exceções
- [x] commit realizado
- [x] push realizado

## Decisões adiadas

- horas fracionadas;
- comparação por equals/id em vez de referência;
- exceção de até 40h;
- cancelar estágio;
- impedir alterações estruturais depois do início;
- enum para resultado da avaliação;
- semana de transição entre estágios não sobrepostos;
- eventual refinamento da dependência entre model e regras.

## Próxima etapa

Sprint 04 — testes automatizados com JUnit.
