# Concedente e Convênio — versão 0.2

## Objetivo

Modelar corretamente a organização ou profissional que recebe estagiários e separar essa identidade do período de vigência do vínculo com a universidade.

---

## 1. Concedente

### Definição

Concedente é a organização, instituição ou profissional que pode receber estagiários.

Ela possui identidade própria e pode continuar existindo no sistema mesmo quando não estiver apta a receber novos estagiários.

### Atributos iniciais

- id
- nome
- tipo
- documento
- email
- telefone

### Tipo da concedente

A classificação exata ainda precisa ser refinada, mas a modelagem deve admitir mais do que empresa privada.

Possíveis valores iniciais:

- PESSOA_JURIDICA
- PROFISSIONAL_AUTONOMO
- INSTITUICAO_PUBLICA
- OUTRA

### Responsabilidades

- manter os dados cadastrais da parte concedente;
- possuir histórico de convênios;
- possuir vagas ofertadas;
- permitir consulta de sua situação institucional a partir dos convênios vigentes.

### O que NÃO deve ser responsabilidade da Concedente

Evitar armazenar apenas:

```
ativa = true/false
```

Esse valor isolado perde o histórico e não explica por que a concedente está apta ou inapta.

---

## 2. Convênio

### Definição

Convênio representa um período formal em que a concedente está vinculada à universidade para fins de estágio.

### Atributos iniciais

- id
- dataInicio
- dataFim
- status
- numeroReferencia (opcional, caso exista identificação institucional)

### Estados candidatos

- FUTURO
- VIGENTE
- ENCERRADO
- CANCELADO

### Observação importante sobre status

Na implementação futura, parte do status pode ser calculada a partir das datas.

Exemplo:

- antes de dataInicio → FUTURO;
- entre dataInicio e dataFim → VIGENTE;
- após dataFim → ENCERRADO.

`CANCELADO` representa uma interrupção explícita e não apenas o fim natural da vigência.

---

## 3. Relacionamento

```
Concedente 1 -------- 0..* Convênio
```

Uma concedente pode:

- ainda não possuir convênio;
- possuir um convênio atual;
- possuir vários convênios ao longo do tempo.

Cada convênio pertence a uma única concedente.

---

## 4. Aptidão da concedente

### Regra proposta

Uma concedente externa está apta a receber novos vínculos de estágio quando possui pelo menos um convênio vigente e não cancelado, respeitadas as demais regras institucionais.

### Exemplo

```
Concedente: Empresa XPTO

Convênio A
01/01/2024 a 31/12/2024
ENCERRADO

Convênio B
01/03/2025 a 28/02/2026
ENCERRADO

Sem convênio vigente
→ concedente continua cadastrada
→ mas não está apta para novos vínculos
```

Depois:

```
Convênio C
01/06/2026 a 31/05/2027
VIGENTE

→ concedente volta a estar apta
```

Isso preserva o histórico e permite identificar lacunas entre os períodos.

---

## 5. Regras de negócio associadas

### RN-CONV-001

Uma concedente pode possuir vários convênios ao longo do tempo.

### RN-CONV-002

Cada convênio pertence a exatamente uma concedente.

### RN-CONV-003

A situação atual da concedente deve ser derivada dos seus vínculos vigentes, e não apenas de um campo booleano manual.

### RN-CONV-004

O encerramento de um convênio não exclui a concedente nem seu histórico.

### RN-CONV-005

A existência de um novo convênio não deve apagar períodos anteriores.

### RN-CONV-006

Antes de formalizar um novo estágio externo, deve ser possível verificar se a concedente possui vínculo institucional válido.

---

## 6. Questões ainda abertas

### Q-CONV-001

Pode existir mais de um convênio vigente simultaneamente para a mesma concedente?

### Q-CONV-002

O convênio é geral para toda a universidade ou pode restringir curso, campus, unidade acadêmica ou modalidade de estágio?

### Q-CONV-003

A concedente pode anunciar vagas antes do início da vigência de um novo convênio, desde que o estágio comece somente depois?

### Q-CONV-004

Convênios cancelados precisam registrar motivo e data de cancelamento?

---

## 7. Decisão de modelagem

Não modelar:

```
Concedente
- ativa
- dataInicioConvenio
- dataFimConvenio
```

Modelar:

```
Concedente
    |
    | 1
    |
    | 0..*
    v
Convenio
```

Isso separa a identidade da concedente do histórico de relacionamento institucional.
