# Concedente e Convênio — versão 0.2

## Objetivo

Modelar corretamente a organização ou profissional que recebe estagiários e separar essa identidade do período de vigência do vínculo com a universidade.

---

## 1. Concedente

### Definição

Concedente é a organização, instituição ou profissional que pode receber estagiários.

A Resolução CONSEPE nº 016/2014 admite como concedentes unidades da própria Unifesspa, instituições e entidades públicas ou privadas, organizações sociais, movimentos sociais e profissionais liberais autônomos registrados em seus conselhos de classe.

Ela possui identidade própria e pode continuar existindo no sistema mesmo quando não estiver apta a receber novos estagiários.

### Atributos iniciais

- id
- nome
- tipo
- documento
- email
- telefone

### Tipo da concedente

A classificação exata ainda pode ser refinada. Valores candidatos:

- UNIDADE_UNIFESSPA
- PESSOA_JURIDICA
- PROFISSIONAL_AUTONOMO
- INSTITUICAO_PUBLICA
- ORGANIZACAO_SOCIAL
- MOVIMENTO_SOCIAL
- OUTRA

### Responsabilidades

- manter os dados cadastrais da parte concedente;
- possuir histórico de convênios, quando se tratar de concedente externa;
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

Convênio representa o instrumento formal firmado entre a Unifesspa e uma concedente externa, estabelecendo as condições para realização de estágios.

### Base normativa confirmada

A Resolução CONSEPE nº 016/2014, art. 14, determina que a Unifesspa firme convênio com entidades externas concedentes de estágio.

O instrumento deve conter, no mínimo:

- cursos de graduação contemplados;
- carga horária a ser cumprida pelo estagiário;
- obrigação de a concedente designar supervisor da área;
- condições de supervisão pela Unifesspa;
- prazo de vigência;
- obrigatoriedade de seguro em favor do estagiário.

O prazo de vigência **não pode ser inferior a 1 ano nem superior a 5 anos**.

A mesma resolução também atribui à Central de Estágios da PROEG a orientação sobre efetivação e renovação de convênios e a manutenção do cadastro de convênios atualizado.

### Atributos iniciais

- id
- numeroReferencia
- dataInicio
- dataFim
- status

### Informações associadas ao convênio

A norma confirma que o convênio precisa registrar também condições como:

- cursosContemplados
- cargaHorariaPermitida
- condicoesSupervisao
- exigenciaSeguro

Na modelagem detalhada, essas informações podem virar atributos, objetos de valor ou associações, dependendo da complexidade necessária.

### Estados candidatos

- FUTURO
- VIGENTE
- ENCERRADO
- CANCELADO

### Observação importante sobre status

Na implementação futura, parte do status pode ser calculada a partir das datas:

- antes de dataInicio → FUTURO;
- entre dataInicio e dataFim → VIGENTE;
- após dataFim → ENCERRADO.

`CANCELADO` representa interrupção explícita antes do fim natural.

---

## 3. Relacionamento

```
Concedente 1 -------- 0..* Convênio
```

Uma concedente externa pode:

- ainda não possuir convênio;
- possuir um convênio vigente;
- possuir vários convênios ao longo do tempo.

Cada convênio pertence a uma única concedente.

Para unidades internas da própria Unifesspa, a necessidade desse mesmo vínculo de convênio deve ser tratada separadamente, pois a Resolução exige expressamente convênio para entidades externas.

---

## 4. Aptidão da concedente

### Regra proposta

Uma concedente externa está apta a receber novos vínculos de estágio quando possui convênio vigente e atende às demais condições normativas.

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
→ mas não está apta para novo estágio externo
```

Depois:

```
Convênio C
01/06/2026 a 31/05/2027
VIGENTE

→ concedente volta a estar apta
```

Isso preserva o histórico e permite identificar lacunas entre períodos.

---

## 5. Regras de negócio associadas

### RN-CONV-001

Concedente externa deve possuir convênio com a Unifesspa para realização de estágio.

### RN-CONV-002

Cada convênio pertence a exatamente uma concedente.

### RN-CONV-003

O prazo de vigência do convênio deve ser de **1 a 5 anos**.

### RN-CONV-004

O instrumento de convênio deve indicar os cursos de graduação contemplados.

### RN-CONV-005

O instrumento de convênio deve estabelecer a carga horária a ser cumprida pelo estagiário.

### RN-CONV-006

A entidade conveniada deve designar supervisor para a área de formação do estagiário.

### RN-CONV-007

O convênio deve estabelecer as condições de supervisão pela Unifesspa.

### RN-CONV-008

O convênio deve prever seguro em favor do estagiário.

### RN-CONV-009

O encerramento de um convênio não exclui a concedente nem seu histórico.

### RN-CONV-010

Renovações devem ser representadas sem sobrescrever convênios anteriores.

### RN-CONV-011

Antes de formalizar um estágio externo, deve ser possível verificar se a concedente possui convênio válido para o curso e período correspondentes.

---

## 6. Questões ainda abertas

### Q-CONV-001

Pode existir mais de um convênio vigente simultaneamente para a mesma concedente?

### Q-CONV-002

Além dos cursos contemplados, o convênio pode restringir campus, unidade acadêmica ou modalidade de estágio?

### Q-CONV-003

A concedente pode anunciar vaga antes do início da vigência de um novo convênio, desde que o estágio só comece após o início da vigência?

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

Isso separa a identidade da concedente do histórico de relacionamento institucional e está alinhado à Resolução CONSEPE nº 016/2014.
