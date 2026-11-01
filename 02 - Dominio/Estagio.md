# Estágio — versão 0.2

## Objetivo

Modelar o vínculo efetivo de estágio entre aluno, concedente e instituição, sem misturar nele informações que pertencem a outros conceitos do domínio.

---

## 1. Definição

`Estagio` representa o vínculo efetivamente estabelecido para um aluno.

Ele pode nascer de diferentes origens:

- vaga publicada no sistema;
- contato direto com concedente;
- projeto/programa de extensão;
- projeto/programa de pesquisa;
- Empresa Júnior;
- outros fluxos institucionais admitidos.

Por isso, Vaga e Candidatura são opcionais na origem do Estágio.

---

## 2. Papel central no domínio

```
Aluno
  |
  v
Estagio
  |-- Concedente
  |-- Supervisor
  |-- Orientador
  |-- Termo de Compromisso
  |-- Plano de Atividades
  |-- Apólice de Seguro
  |-- Vaga (opcional)
  |-- Candidatura (opcional)
```

---

## 3. Atributos iniciais

- id
- modalidade
- origem
- dataInicio
- dataFimPrevista
- dataFimReal
- cargaHorariaDiaria
- cargaHorariaSemanal
- status

### Observação

Evitar duplicar dados que já pertençam a outras entidades.

Exemplos:
- bolsa pode vir da Vaga/Termo, dependendo da decisão final;
- dados da concedente não devem ser copiados para Estagio;
- número da apólice pertence à ApoliceSeguro;
- conteúdo pedagógico pertence ao PlanoAtividades.

---

## 4. Modalidade

Valores iniciais:

- OBRIGATORIO
- NAO_OBRIGATORIO

Quando houver Vaga, a modalidade deve ser compatível com a oportunidade ofertada.

Quando não houver Vaga, a modalidade deve ser definida durante a formalização do estágio.

---

## 5. Origem

### Hipótese v0.2

Criar enumeração `OrigemEstagio`:

- VAGA_PUBLICADA
- CONTATO_DIRETO
- PROJETO_EXTENSAO
- PROJETO_PESQUISA
- EMPRESA_JUNIOR
- OUTRO

### Motivo

Permite registrar como o vínculo surgiu sem obrigar todo Estágio a possuir Vaga ou Candidatura.

### Ponto de atenção

Se projetos de extensão/pesquisa exigirem muitos dados específicos, a origem pode futuramente ser representada por entidades próprias, em vez de apenas enum.

---

## 6. Estados candidatos

- EM_FORMALIZACAO
- ATIVO
- ENCERRADO
- CANCELADO

### Fluxo inicial

```
EM_FORMALIZACAO
      |
      v
    ATIVO
    /   \
   v     v
ENCERRADO CANCELADO
```

### Significado

#### EM_FORMALIZACAO
O vínculo está sendo preparado, mas ainda não pode iniciar.

#### ATIVO
O estágio está formalizado e dentro do período de vigência.

#### ENCERRADO
O estágio foi concluído normalmente.

#### CANCELADO
O estágio foi interrompido antes da conclusão prevista.

---

## 7. Condições para ativação

Um Estágio não deve passar para ATIVO apenas porque o aluno foi selecionado.

Antes da ativação, devem ser verificadas as condições aplicáveis, como:

- aluno válido;
- concedente apta;
- convênio vigente, quando exigido;
- modalidade definida;
- jornada válida;
- supervisor definido;
- orientador definido;
- Termo de Compromisso formalizado;
- Plano de Atividades definido/aprovado;
- seguro válido;
- ausência de impedimentos institucionais.

---

## 8. Relacionamentos principais

### Aluno

```
Aluno 1 -------- 0..* Estagio
```

Cada Estágio pertence a exatamente um aluno.

---

### Concedente

```
Concedente 1 -------- 0..* Estagio
```

Cada Estágio deve estar associado à parte concedente responsável pelo vínculo.

### Observação

Mesmo em estágio interno, projeto de extensão, pesquisa ou Empresa Júnior, precisamos representar corretamente quem exerce o papel de concedente no vínculo.

---

### Vaga

```
Vaga 0..1 -------- 0..* Estagio
```

Do ponto de vista do Estágio:
- pode haver zero ou uma Vaga de origem.

---

### Candidatura

```
Candidatura 0..1 -------- 0..1 Estagio
```

Do ponto de vista do Estágio:
- pode haver zero ou uma Candidatura de origem.

---

### Supervisor

```
Estagio 1 -------- 1 Pessoa : supervisor
```

### Orientador

```
Estagio 1 -------- 1 Pessoa : orientador
```

Uma mesma Pessoa pode, em casos permitidos, desempenhar ambos os papéis.

---

### Termo de Compromisso

```
Estagio 1 -------- 0..1 TermoCompromisso
```

Durante a formalização, o termo pode ainda não estar completo.

Para ativação do vínculo, ele deve atender às exigências aplicáveis.

---

### Plano de Atividades

```
Estagio 1 -------- 0..1 PlanoAtividades
```

Durante a formalização, pode ainda não existir.

Para ativação, deve estar definido de acordo com as regras acadêmicas.

---

### Apólice de Seguro

```
ApoliceSeguro 1 -------- 0..* Estagio
```

Todo estágio ativo deve possuir cobertura válida.

---

## 9. Regras de negócio

### RN-EST-001

Todo Estágio pertence a exatamente um Aluno.

### RN-EST-002

Todo Estágio possui modalidade obrigatória ou não obrigatória.

### RN-EST-003

Todo Estágio deve possuir uma Concedente responsável.

### RN-EST-004

Vaga e Candidatura são opcionais na origem do Estágio.

### RN-EST-005

Um Estágio não pode ser ativado sem as formalizações obrigatórias aplicáveis.

### RN-EST-006

Todo Estágio ativo deve possuir Supervisor e Orientador definidos.

### RN-EST-007

Todo Estágio ativo deve possuir cobertura de seguro válida.

### RN-EST-008

A jornada deve respeitar limites legais, institucionais e acadêmicos.

### RN-EST-009

A duração na mesma concedente deve respeitar o limite legal aplicável.

### RN-EST-010

O encerramento deve preservar histórico e não excluir o vínculo.

---

## 10. Questões abertas

### Q-EST-001

A modalidade deve ser armazenada no Estágio mesmo quando já existe na Vaga, para preservar histórico?

### Q-EST-002

Devemos registrar a origem apenas como enum ou criar entidades específicas para projeto de extensão, pesquisa e Empresa Júnior?

### Q-EST-003

O Estágio pode ser criado antes do Termo e Plano, em estado EM_FORMALIZACAO, ou só deve existir depois desses registros?

### Q-EST-004

Quais regras exatas impedem a ativação quando o aluno possui pendências anteriores?

### Q-EST-005

Como representar formalmente troca de supervisor ou orientador durante o vínculo?
