# Entidades — versão 0.1

## Pessoa

Representa os dados comuns às pessoas relevantes para o domínio.

### Atributos iniciais
- id
- nome
- cpf
- email
- telefone

### Responsabilidade
Concentrar os dados de identificação que não dependem do papel exercido pela pessoa.

---

## Aluno

Representa o discente que pode se candidatar a vagas e estabelecer vínculos de estágio.

### Atributos iniciais
- matricula
- curso
- situacaoAcademica

### Relação com Pessoa
Aluno é uma especialização de Pessoa.

---

## Professor

Representa um docente da instituição.

### Atributos iniciais
- siape
- unidadeAcademica

### Relação com Pessoa
Professor é uma especialização de Pessoa.

---

## Concedente

Representa a organização, instituição ou profissional que pode receber estagiários.

### Atributos iniciais
- id
- nome
- tipo
- documento
- email
- telefone

### Observação
O estado de aptidão da concedente não deve depender apenas de um campo booleano. A vigência deve ser representada por Convênio.

---

## Convênio

Representa um período formal de vínculo entre a concedente e a universidade.

### Atributos iniciais
- id
- dataInicio
- dataFim
- status

### Responsabilidade
Preservar o histórico de vigências da concedente.

---

## Vaga

Representa uma oportunidade de estágio ofertada por uma concedente.

### Atributos iniciais
- id
- titulo
- descricao
- modalidade
- cargaHorariaDiaria
- cargaHorariaSemanal
- valorBolsa
- valorAuxilioTransporte
- duracaoPrevista
- requisitos
- status

### Modalidade
- OBRIGATORIO
- NAO_OBRIGATORIO

---

## Candidatura

Representa a relação entre um aluno e uma vaga durante o processo de seleção.

### Atributos iniciais
- id
- dataCandidatura
- status

### Estados candidatos
- INSCRITA
- EM_ANALISE
- SELECIONADA
- NAO_SELECIONADA
- CANCELADA

### Observação
Candidatura não equivale a estágio.

---

## Estágio

Representa o vínculo efetivamente estabelecido após seleção e formalização.

### Atributos iniciais
- id
- dataInicio
- dataFimPrevista
- dataFimReal
- cargaHorariaDiaria
- cargaHorariaSemanal
- status

### Estados candidatos
- EM_FORMALIZACAO
- ATIVO
- ENCERRADO
- CANCELADO

### Observação
A modalidade pode ser derivada da vaga. Evitar duplicação sem necessidade.

---

## Termo de Compromisso

Representa a formalização eletrônica do vínculo de estágio.

### Atributos iniciais
- id
- dataCriacao
- dataAceiteAluno
- dataAceiteConcedente
- dataAceiteInstituicao
- status

### Observação
O objetivo não é apenas armazenar um PDF, mas representar o conteúdo e o estado da formalização.

---

## Plano de Atividades

Representa as atividades acadêmico-profissionais previstas para o estágio.

### Atributos iniciais
- id
- justificativa
- objetivo
- descricaoAtividades
- adequacaoPedagogica
- status

### Observação
Deve permitir validação conjunta entre aluno, supervisor e orientador.

---

## Apólice de Seguro

Representa a cobertura contra acidentes pessoais válida durante determinado período.

### Atributos iniciais
- id
- numero
- dataInicio
- dataFim
- documentoReferencia
