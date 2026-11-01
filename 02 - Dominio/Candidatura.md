# Candidatura — versão 0.2

## Objetivo

Modelar a participação de um aluno em uma vaga sem confundir esse processo com a existência de um estágio.

---

## 1. Definição

Candidatura representa a relação entre um Aluno e uma Vaga durante o processo de seleção.

Ela existe antes do vínculo de estágio.

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

Não basta criar uma ligação direta entre Aluno e Vaga.

A relação possui dados e estado próprios, por exemplo:

- quando o aluno se candidatou;
- situação atual da candidatura;
- eventual data de decisão;
- observação de seleção, quando necessário.

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

CANCELADA pode ocorrer antes da decisão final.

---

## 5. Relacionamentos

### Aluno e Candidatura

```
Aluno 1 -------- 0..* Candidatura
```

Um aluno pode se candidatar a várias vagas ao longo do tempo.

Cada candidatura pertence a exatamente um aluno.

### Vaga e Candidatura

```
Vaga 1 -------- 0..* Candidatura
```

Uma vaga pode receber várias candidaturas.

Cada candidatura pertence a exatamente uma vaga.

---

## 6. Relação com Estágio

### Regra proposta

Uma candidatura selecionada pode originar, no máximo, um estágio.

```
Candidatura 1 -------- 0..1 Estagio
```

Nem toda candidatura gera estágio.

Uma candidatura:
- pode ser rejeitada;
- pode ser cancelada;
- pode ser selecionada e ainda assim não chegar à formalização.

---

## 7. Regra importante: seleção não é formalização

Mesmo após a candidatura ser marcada como SELECIONADA, o estágio ainda não deve ser considerado ativo.

Ainda podem faltar:

- validação do convênio;
- Termo de Compromisso;
- Plano de Atividades;
- apólice de seguro;
- definição/validação de supervisor e orientador;
- outras verificações institucionais.

Portanto:

```
Candidatura SELECIONADA
        |
        v
Estágio EM_FORMALIZACAO
        |
        v
Estágio ATIVO
```

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

Somente candidatura selecionada pode, no fluxo padrão, originar um estágio.

### RN-CAND-006

Uma candidatura selecionada pode originar no máximo um estágio.

### RN-CAND-007

Selecionar o aluno não torna o estágio automaticamente ativo.

---

## 9. Questões abertas

### Q-CAND-001

Pode existir estágio sem candidatura registrada no sistema, por exemplo quando o aluno encontra diretamente uma oportunidade?

### Q-CAND-002

O sistema deve impedir o mesmo aluno de se candidatar duas vezes à mesma vaga?

### Q-CAND-003

Uma candidatura selecionada pode voltar para EM_ANALISE ou ser substituída por outro candidato?

### Q-CAND-004

Devemos guardar o responsável pela decisão de seleção?
