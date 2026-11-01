# Termo de Compromisso — versão 0.2

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

O sistema deve representar o estado da formalização e, futuramente, os dados estruturados relevantes do termo.

## Regras

- um Termo pertence a um único Estágio;
- o termo deve identificar as partes do vínculo;
- a formalização deve ocorrer antes do início efetivo do estágio;
- alterações relevantes podem exigir aditivo ou nova formalização, conforme regra institucional.

## Questões abertas

- O termo pode ter versões/aditivos?
- Quais campos precisam ser estruturados no sistema além dos aceites?
- Como representar assinatura/aceite institucional?
