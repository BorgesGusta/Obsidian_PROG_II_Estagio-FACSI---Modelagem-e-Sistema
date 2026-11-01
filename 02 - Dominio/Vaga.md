# Vaga — versão 0.2

## Objetivo

Modelar a oportunidade de estágio ofertada por uma concedente antes da existência de um vínculo individual com um aluno.

---

## 1. Definição

Vaga representa uma oportunidade de estágio ofertada por uma concedente apta.

Ela descreve as condições da oportunidade e pode receber candidaturas de alunos.

A vaga ainda não é um estágio. O estágio só surge depois que um aluno é selecionado e o vínculo é formalizado.

---

## 2. Relação com Concedente

```
Concedente 1 -------- 0..* Vaga
```

Uma concedente pode ofertar várias vagas.

Cada vaga pertence a uma única concedente.

### Regra

Para vagas de estágio externo, a concedente deve estar apta segundo as regras de convênio aplicáveis.

---

## 3. Atributos iniciais

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
- quantidadePosicoes
- status

### Observação sobre quantidadePosicoes

Esse atributo é uma hipótese de modelagem.

Ainda precisamos confirmar com o professor se:
- uma Vaga pode possuir várias posições; ou
- cada registro de Vaga representa exatamente uma posição.

---

## 4. Modalidade

A oportunidade deve ser classificada como:

- OBRIGATORIO
- NAO_OBRIGATORIO

Na reunião de levantamento, o professor indicou que a modalidade é característica da vaga ofertada pela concedente, e não uma escolha posterior do aluno.

### Regra legal associada

A Lei nº 11.788/2008 estabelece que, no estágio não obrigatório, bolsa ou outra forma de contraprestação e auxílio-transporte são compulsórios.

No estágio obrigatório, a concessão de bolsa pode ser acordada, mas não é obrigatória pela mesma regra.

---

## 5. Jornada

Para estudante de ensino superior, a Lei nº 11.788/2008 estabelece, como regra geral:

- máximo de 6 horas diárias;
- máximo de 30 horas semanais.

Há exceção legal para cursos que alternam teoria e prática em períodos sem aulas presenciais, quando a jornada pode chegar a 40 horas semanais se isso estiver previsto no projeto pedagógico.

### Consequência para o modelo

A Vaga deve registrar a jornada proposta, mas a validação final também deve considerar:

- regras do curso;
- convênio aplicável;
- outros vínculos simultâneos do aluno;
- compatibilidade com atividades acadêmicas.

---

## 6. Bolsa e auxílio-transporte

### Estágio não obrigatório

- bolsa/contraprestação: obrigatória;
- auxílio-transporte: obrigatório.

### Estágio obrigatório

- bolsa: opcional;
- auxílio/benefícios: podem existir conforme acordo e condições aplicáveis.

### Consequência de modelagem

Não assumir:

```
valorBolsa > 0
```

para toda vaga.

A validação depende da modalidade.

---

## 7. Supervisor

A concedente deve indicar profissional da área para supervisão técnica quando aplicável.

Na reunião, o professor sugeriu informar o supervisor já no cadastro da vaga.

### Hipótese v0.2

```
Vaga ---- Pessoa : supervisorPrevisto
```

Porém o estágio também precisa registrar quem efetivamente supervisiona aquele vínculo.

### Questão aberta

Confirmar se:
- o supervisor definido na vaga é sempre o supervisor do estágio; ou
- ele funciona apenas como supervisor previsto e pode ser alterado na formalização.

---

## 8. Requisitos e cursos elegíveis

A vaga pode possuir requisitos específicos, por exemplo:

- curso ou área relacionada;
- conhecimentos prévios;
- período acadêmico;
- habilidades específicas.

Além disso, a oportunidade não pode contrariar os cursos contemplados pelo convênio aplicável.

### Regra proposta

Um aluno só deve poder avançar para formalização se seu curso for compatível com:
1. os requisitos da vaga; e
2. o convênio vigente da concedente, quando aplicável.

---

## 9. Estados candidatos

- RASCUNHO
- PUBLICADA
- ENCERRADA
- CANCELADA

### Possível estado adicional

- PREENCHIDA

Esse estado depende da decisão sobre quantidade de posições.

Se a vaga puder ter várias posições, talvez seja melhor calcular disponibilidade com base em:
- quantidadePosicoes;
- quantidade de candidatos selecionados/vínculos gerados.

---

## 10. Regras de negócio

### RN-VAGA-001

Toda vaga pertence a uma concedente.

### RN-VAGA-002

A modalidade da vaga é OBRIGATORIO ou NAO_OBRIGATORIO.

### RN-VAGA-003

A jornada proposta deve respeitar os limites legais e institucionais aplicáveis.

### RN-VAGA-004

Para estágio não obrigatório, bolsa/contraprestação e auxílio-transporte são obrigatórios.

### RN-VAGA-005

A vaga deve possuir requisitos compatíveis com a formação acadêmica esperada.

### RN-VAGA-006

A vaga externa só pode originar estágio se houver convênio válido e compatível com o curso.

### RN-VAGA-007

A publicação da vaga não cria vínculo de estágio.

### RN-VAGA-008

A existência de candidatura também não cria vínculo de estágio.

---

## 11. Questões abertas

### Q-VAGA-001

Uma vaga pode possuir mais de uma posição?

### Q-VAGA-002

O supervisor fica definitivamente vinculado à vaga ou apenas como indicação inicial?

### Q-VAGA-003

Pode ser publicada vaga cujo convênio começa em data futura?

### Q-VAGA-004

Existe exigência institucional adicional sobre período mínimo/máximo de duração da vaga?

### Q-VAGA-005

Quais requisitos acadêmicos mínimos devem ser validados automaticamente pelo sistema?
