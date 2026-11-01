# DM-006 — Estágio como entidade central

## Status

Adotada na versão 0.2.

## Contexto

O domínio possui diferentes caminhos para chegar a um estágio:

- processo seletivo por Vaga/Candidatura;
- contato direto;
- extensão;
- pesquisa;
- Empresa Júnior.

Portanto, o Estágio não pode depender obrigatoriamente de Vaga ou Candidatura.

## Decisão

`Estagio` será a entidade central do vínculo efetivo.

```
Aluno
  |
  v
Estagio
  |-- Concedente
  |-- Supervisor
  |-- Orientador
  |-- TermoCompromisso
  |-- PlanoAtividades
  |-- ApoliceSeguro
```

Vaga e Candidatura serão relacionamentos opcionais de origem.

## Origem do estágio

Na versão 0.2, adotamos como hipótese um atributo `origem`.

Valores candidatos:

- VAGA_PUBLICADA
- CONTATO_DIRETO
- PROJETO_EXTENSAO
- PROJETO_PESQUISA
- EMPRESA_JUNIOR
- OUTRO

## Regra de ativação

Criar o Estágio não significa que ele já está ativo.

O vínculo pode existir em estado `EM_FORMALIZACAO` até que as condições obrigatórias sejam atendidas.
