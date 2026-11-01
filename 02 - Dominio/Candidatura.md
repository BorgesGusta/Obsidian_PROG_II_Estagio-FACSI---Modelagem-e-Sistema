# Candidatura — versão 0.2

## Objetivo

Modelar a participação de um aluno em uma vaga quando houver processo de seleção, sem tornar a candidatura obrigatória para todo estágio.

---

## 1. Definição

Candidatura representa a relação entre um Aluno e uma Vaga durante um processo de seleção.

Ela pode existir antes do vínculo de estágio, mas **nem todo estágio precisa nascer de uma candidatura**.

```
Aluno
  |
  v
Candidatura
  |
  v
Vaga
```

---

## 2. Por que Candidatura é uma entidade

A relação possui dados e estado próprios, como:

- data da candidatura;
- situação atual;
- data de decisão;
- observações da seleção.

Por isso, Candidatura é tratada como entidade associativa.

---

## 3. Atributos iniciais

- id
- dataCandidatura
- status
- dataDecisao (opcional)
- observacao (opcional)

---

## 4. Estados candidatos

- INSCRITA
- EM_ANALISE
- SELECIONADA
- NAO_SELECIONADA
- CANCELADA

### Fluxo inicial

```
INSCRITA
   |
   v
EM_ANALISE
   |        \
   v         v
SELECIONADA NAO_SELECIONADA
   |
   v
pode originar Estágio
```

---

## 5. Relacionamentos

### Aluno e Candidatura

```
Aluno 1 -------- 0..* Candidatura
```

### Vaga e Candidatura

```
Vaga 1 -------- 0..* Candidatura
```

Cada candidatura pertence a exatamente um aluno e uma vaga.

---

## 6. Relação com Estágio

Uma candidatura selecionada pode originar, no máximo, um estágio.

Mas um estágio pode existir sem candidatura.

```
Candidatura 0..1 -------- 0..1 Estagio
```

### Casos sem candidatura

O regulamento da FACSI permite que o aluno encontre oportunidade por contato direto com a concedente ou por meio da coordenação de estágio.

Também admite estágio realizado por meio de atividades em:

- programas de extensão;
- projetos de extensão;
- programas/projetos de pesquisa;
- Empresa Júnior vinculada à FACSI.

Nesses casos, o vínculo pode ser formalizado sem existir uma candidatura prévia cadastrada no sistema.

---

## 7. Regra importante: seleção não é formalização

Mesmo quando existe candidatura e ela é SELECIONADA, o estágio ainda não deve ser considerado ativo.

Ainda podem faltar:

- validação institucional;
- Termo de Compromisso;
- Plano de Atividades;
- apólice de seguro;
- supervisor/orientador;
- demais verificações aplicáveis.

---

## 8. Regras de negócio

### RN-CAND-001

Toda candidatura pertence a exatamente um aluno e uma vaga.

### RN-CAND-002

Uma vaga pode receber múltiplas candidaturas.

### RN-CAND-003

Um aluno pode possuir múltiplas candidaturas ao longo do tempo.

### RN-CAND-004

Candidatura não representa vínculo de estágio.

### RN-CAND-005

Quando o estágio nasce de processo seletivo registrado, somente candidatura selecionada pode originá-lo.

### RN-CAND-006

Uma candidatura selecionada pode originar no máximo um estágio.

### RN-CAND-007

Estágio pode existir sem candidatura.

---

## 9. Questões abertas

### Q-CAND-001

O sistema deve impedir o mesmo aluno de se candidatar duas vezes à mesma vaga?

### Q-CAND-002

Uma candidatura selecionada pode voltar para EM_ANALISE ou ser substituída por outro candidato?

### Q-CAND-003

Devemos guardar o responsável pela decisão de seleção?
