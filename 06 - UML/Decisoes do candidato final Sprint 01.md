# Decisões do Diagrama Candidato Final — Sprint 01

## Status

Versão candidata a final, pronta para validação com o professor Hugo.

## Simplificações conscientes

### Vaga representa uma oportunidade

Nesta versão, uma `Vaga` representa uma oportunidade individual.

```
Vaga 0..1 ---- 0..1 Estagio
```

Se a FACSI precisar representar uma publicação com várias oportunidades idênticas, podemos acrescentar `quantidadeDisponivel` posteriormente sem alterar o restante do domínio.

### Supervisor não fica na Vaga

O Supervisor é ligado ao `Estagio`, porque é no vínculo efetivamente formalizado que precisamos garantir quem acompanha o discente.

Se a FACSI quiser registrar Supervisor já na oferta, isso pode ser adicionado posteriormente como informação opcional.

### Datas e carga ficam no Estágio

O Termo formaliza essas condições, mas evitamos repetir na classe `TermoCompromisso` os mesmos atributos de período e carga já presentes em `Estagio`.

### Remuneração fica no Termo

`modalidade` e `remuneracao` são dimensões diferentes.

A Vaga possui valores ofertados.
O Termo registra as condições financeiras efetivamente pactuadas.

### Mais de um Plano

```
Estagio 1 ---- 0..* PlanoAtividades
```

A prorrogação pode exigir novo Plano, portanto o histórico deve ser preservado.

### Frequência e Relatório Final

Não aparecem na UML da Sprint 01 porque pertencem à etapa de acompanhamento/encerramento, prevista para a próxima evolução do modelo.

## Pontos que o professor ainda pode alterar

- forma de escolha do Orientador;
- momento exato de definição do Supervisor;
- regras de pendências para novo vínculo/encerramento;
- fluxo de troca de Supervisor/Orientador;
- outras situações de Termo Aditivo;
- eventual necessidade de representar várias oportunidades dentro de uma mesma publicação de Vaga.
