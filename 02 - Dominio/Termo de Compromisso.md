# Termo de Compromisso — versão 0.3

## Definição

Representa a formalização específica do vínculo de estágio entre as partes envolvidas.

No estágio externo, o termo formaliza o vínculo entre:
- aluno;
- concedente;
- instituição de ensino.

## Atributos iniciais

- id
- dataCriacao
- dataAceiteAluno
- dataAceiteConcedente
- dataAceiteInstituicao
- status

## Estados candidatos

- EM_PREENCHIMENTO
- AGUARDANDO_ACEITES
- FORMALIZADO
- CANCELADO

## Relação com Estágio

```
Estagio 1 -------- 0..1 TermoCompromisso
```

Durante a formalização, o Estágio pode existir sem termo concluído.

Para ativação do vínculo, o termo deve estar formalizado quando exigido.

## Responsabilidade

O Termo não deve ser tratado apenas como arquivo PDF.

O sistema deve representar o estado da formalização e os dados estruturados relevantes.

## Aditivos

A Lei nº 11.788/2008 prevê expressamente que o Plano de Atividades seja incorporado ao Termo por **aditivos** ao longo do acompanhamento do estágio.

### Consequência

A existência de aditivos deixa de ser hipótese e passa a ser requisito confirmado.

Na v0.3 ainda não criamos a entidade `AditivoTermo`; ela fica como evolução natural para a próxima etapa de modelagem.

## Regras

- um Termo principal pertence a um único Estágio;
- o termo deve identificar as partes do vínculo;
- deve ser celebrado antes do início efetivo;
- mudanças no plano podem gerar aditivos;
- o histórico dessas alterações não deve ser perdido.

## Questões ainda abertas

- Quais outros tipos de alteração, além do Plano de Atividades, a FACSI formaliza por aditivo?
- Como representar assinatura/aceite institucional no sistema?
