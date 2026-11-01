# Registro de Decisões

As decisões abaixo são hipóteses de modelagem que devem ser revisadas conforme o domínio evolui.

## DM-001 — Separar Concedente de Convênio

**Status:** proposta

**Decisão:** modelar `Concedente` e `Convenio` como conceitos distintos.

**Motivo:** uma concedente pode possuir diferentes períodos de vigência e pode ficar inativa entre um convênio e outro.

**Evitar:** representar toda a situação apenas por `Concedente.ativa = true/false`.

---

## DM-002 — Candidatura como entidade própria

**Status:** proposta

**Decisão:** criar `Candidatura` entre `Aluno` e `Vaga`.

**Motivo:** a relação possui estado e histórico próprios. Candidatar-se não significa ter um estágio.

---

## DM-003 — Supervisor e Orientador como papéis

**Status:** em análise

**Decisão proposta:** evitar assumir inicialmente que `Supervisor` e `Orientador` sejam subclasses permanentes de `Pessoa`.

**Motivo:** uma mesma pessoa, especialmente um professor em estágio interno, pode exercer mais de um papel simultaneamente.

---

## DM-004 — Documentos como dados estruturados

**Status:** proposta

**Decisão:** Termo de Compromisso e Plano de Atividades devem ser representados como conceitos do domínio, não apenas como arquivos enviados.

**Motivo:** o objetivo do futuro sistema é permitir consultas, validações e gestão eletrônica do processo.
