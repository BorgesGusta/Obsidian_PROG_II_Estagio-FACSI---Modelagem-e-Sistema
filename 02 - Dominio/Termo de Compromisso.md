# Termo de Compromisso — versão 0.4

## Definição

Representa a formalização do vínculo entre discente, concedente e instituição de ensino.

A Resolução 921/2025 determina que o Termo seja celebrado para cada nova oportunidade de estágio e proíbe assinatura retroativa.

## Atributos iniciais

- id
- dataCriacao
- dataAceiteAluno
- dataAceiteConcedente
- dataAceiteInstituicao
- remunerado
- valorRemuneracao
- valorAuxilioTransporte
- horasSemanais
- cargaHorariaTotalPrevista
- dataInicio
- dataFim
- status

## Estados candidatos

- EM_PREENCHIMENTO
- AGUARDANDO_ACEITES
- FORMALIZADO
- CANCELADO

## Condições financeiras

O modelo de Termo usado pela FACSI possui cláusulas distintas para:
- estágio remunerado, registrando remuneração, auxílio-transporte e apólice;
- estágio não remunerado, registrando a responsabilidade pelo seguro.

Na modelagem, modalidade e remuneração são conceitos diferentes.

### Validação

Se o Estágio for `NAO_OBRIGATORIO`, o Termo deve possuir contrapartida financeira válida.

## Relação com Estágio

```
Estagio 1 -------- 0..1 TermoCompromisso
```

## Seguro

O número da apólice deve constar no Termo, mas a Apólice continua sendo entidade própria do domínio.

## Aditivos

Prorrogação exige novo Plano de Atividades validado e anexado a Termo Aditivo.

## Regras

- deve existir antes do início;
- não admite assinatura retroativa;
- formaliza condições pactuadas;
- deve preservar histórico de aditivos e alterações relevantes.
