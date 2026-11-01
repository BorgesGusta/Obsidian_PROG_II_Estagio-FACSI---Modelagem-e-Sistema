# Checklist de Prontidão — Sprint 01

## Modelagem do domínio
- [x] Pessoa
- [x] Aluno
- [x] Professor
- [x] Supervisor
- [x] Orientador
- [x] Concedente
- [x] Convênio
- [x] Vaga
- [x] Candidatura
- [x] Estágio
- [x] Termo de Compromisso
- [x] Plano de Atividades
- [x] Apólice de Seguro

## Decisões estruturais
- [x] Separar Concedente e Convênio
- [x] Separar Vaga e Estágio
- [x] Candidatura como entidade associativa
- [x] Vaga opcional na origem do Estágio
- [x] Candidatura opcional na origem do Estágio
- [x] Estágio relacionado à Concedente
- [x] Estágio relacionado ao Convênio aplicável
- [x] Supervisor como papel de Pessoa
- [x] Orientador como Professor
- [x] Origem do Estágio como enum provisório
- [x] Modalidade separada de remuneração
- [x] Condições financeiras formalizadas no Termo
- [x] Histórico de múltiplos Planos em prorrogações
- [x] Apólice coletiva compatível com múltiplos Estágios

## Regras/documentação
- [x] Regulamento FACSI 2022 analisado
- [x] Resolução CONSEPE 921/2025 analisada
- [x] Confirmado que a 921/2025 revogou a 016/2014
- [x] Convênio de 1 a 5 anos confirmado na norma vigente
- [x] Estágio sem candidatura confirmado
- [x] Extensão/pesquisa/Empresa Júnior consideradas
- [x] Soma de estágios simultâneos resolvida
- [x] Limite geral 6h/dia e 30h/semana
- [x] Dois não obrigatórios simultâneos regulamentados
- [x] Não obrigatório sem contrapartida financeira vedado
- [x] Termo real da FACSI analisado
- [x] Plano real da FACSI analisado
- [x] Ficha de Frequência analisada
- [x] Relatório Final analisado
- [x] Apólice institucional analisada
- [x] Prorrogação + novo Plano + Termo Aditivo confirmados
- [x] UML pré-validação atualizada

## Falta para encerrar a Sprint 01
- [ ] Validar com o professor apenas os pontos operacionais ainda abertos
- [ ] Aplicar correções finais
- [ ] Gerar UML final
- [ ] Marcar Sprint 01 como concluída

## Próxima etapa
- [ ] Revisão guiada de OO
- [ ] Exercícios
- [ ] Classes Java
- [ ] Regras básicas em Java
- [ ] Testes simples
- [ ] Spring/persistência somente depois
