# Sprint 03 — Regras de Negócio

## Status

🟡 Em andamento

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

### Decisões adiadas
- horas fracionadas;
- comparação por equals/id em vez de referência;
- exceção de até 40h;
- semana de transição entre estágios não sobrepostos.

## Parte 2 — Formalização e encerramento

**Status:** ⬜ Não iniciada

- [ ] verificar Termo
- [ ] verificar Plano de Atividades
- [ ] verificar Seguro
- [ ] verificar Convênio quando aplicável
- [ ] verificar contrapartida financeira do estágio não obrigatório
- [ ] criar regra podeIniciar()
- [ ] criar regra podeEncerrar()
- [ ] avaliar carga horária mínima obrigatória
- [ ] definir transições de status
- [ ] revisar status textuais
- [ ] criar cenários válidos e inválidos
- [ ] BUILD SUCCESS
- [ ] execução sem exceções
- [ ] commit
- [ ] push
