# Etapa 7 — DevSecOps e Vídeo Final

## Pipeline DevSecOps proposto

O pipeline DevSecOps proposto busca integrar as atividades de segurança ao ciclo de desenvolvimento do Sistema de Agendamento de Consultas Médicas.

Como o sistema analisado não foi implementado, o pipeline apresentado nesta etapa representa uma proposta de como as atividades de segurança estudadas ao longo do trabalho poderiam ser incorporadas a um processo real de desenvolvimento.

A segurança seria considerada desde o planejamento até a operação do sistema, utilizando os resultados produzidos nas etapas anteriores.

| Momento                          | Atividade de segurança                                           | Evidência produzida                                                      | Condição para continuar                                                 |
| -------------------------------- | ---------------------------------------------------------------- | ------------------------------------------------------------------------ | ----------------------------------------------------------------------- |
| Planejamento                     | Modelagem de ameaças com STRIDE e definição de casos de abuso    | Ameaças T01–T06 e casos de abuso                                         | Principais ameaças identificadas e relacionadas ao sistema              |
| Análise de riscos                | Avaliação de probabilidade, impacto, priorização e tratamento    | Registro dos riscos R01–R06 e plano de tratamento                        | Riscos prioritários identificados e estratégias de tratamento definidas |
| Arquitetura                      | Definição de requisitos e decisões de segurança                  | RS01–RS03, vulnerabilidades catalogadas e diagrama de arquitetura segura | Requisitos de segurança definidos para os riscos prioritários           |
| Implementação                    | Aplicação de práticas de código seguro                           | Pseudocódigos de autorização e proteção da autenticação                  | Controles de segurança coerentes com os requisitos                      |
| Testes                           | Execução de testes de segurança                                  | Testes TS01–TS04                                                         | Comportamentos seguros esperados atendidos                              |
| Análise de código e dependências | Análise estática do código, dependências e possíveis segredos    | Relatórios de SAST, SCA e verificação de segredos                        | Nenhuma vulnerabilidade crítica ou segredo exposto sem tratamento       |
| Verificação dinâmica             | Teste da aplicação em execução com ferramenta de segurança       | Relatório do OWASP ZAP                                                   | Alertas relevantes analisados e riscos críticos tratados                |
| Implantação                      | Verificação das condições de segurança antes da disponibilização | Registro de aprovação da implantação                                     | Nenhum bloqueio de segurança pendente                                   |
| Operação                         | Monitoramento de eventos e aplicação das regras de detecção      | Logs, alertas e regras RD01–RD03                                         | Incidentes identificados e tratados conforme sua gravidade              |

## Fluxo do pipeline

O fluxo proposto pode ser representado de forma simplificada como:

`Planejamento → Riscos → Arquitetura → Implementação → Testes → Análise de código e dependências → Verificação dinâmica → Implantação → Monitoramento`

A aprovação de uma etapa não deverá ocorrer apenas porque a atividade anterior foi concluída.

Cada etapa possui condições de segurança que precisam ser atendidas antes da continuidade do pipeline.

Caso alguma condição não seja satisfeita, o processo deverá retornar à etapa responsável pela correção.

`Problema identificado → Correção → Nova verificação → Aprovação → Continuidade do pipeline`

## Condições que impedem a continuidade do pipeline

### G01 — Teste de segurança reprovado

Caso um teste de segurança apresente resultado diferente do comportamento seguro esperado, o pipeline deverá ser interrompido.

A continuidade somente poderá ocorrer após a correção do problema e uma nova execução do teste.

### G02 — Vulnerabilidade crítica ou alta sem tratamento

Caso uma vulnerabilidade crítica ou de alto impacto seja identificada durante as análises de código, dependências ou verificações dinâmicas, a implantação não deverá ocorrer enquanto o risco não for analisado.

A continuidade poderá ocorrer após correção, mitigação ou decisão formal de tratamento do risco.

### G03 — Falha no controle de acesso

Caso os testes demonstrem que um usuário consegue acessar informações ou executar operações sem possuir a autorização necessária, o pipeline deverá ser interrompido.

Essa condição está diretamente relacionada aos riscos R04 e R06 analisados anteriormente.

### G04 — Segredo encontrado no repositório

Caso sejam encontradas senhas, tokens, chaves ou outras credenciais armazenadas no código ou no repositório, a continuidade deverá ser bloqueada.

O segredo deverá ser removido e, quando necessário, substituído antes de uma nova verificação.

### G05 — Dependência com vulnerabilidade relevante

Caso uma dependência utilizada pelo sistema possua uma vulnerabilidade conhecida considerada relevante para o contexto da aplicação, ela deverá ser analisada antes da implantação.

Quando possível, deverá ser atualizada, substituída ou acompanhada de uma medida de mitigação.

## Relação com as etapas anteriores

A proposta DevSecOps utiliza os resultados produzidos durante todo o trabalho.

### Etapa 1 — Modelagem de ameaças

A modelagem STRIDE permitiu identificar possíveis ameaças relacionadas ao sistema antes de sua implementação.

Essas ameaças e os casos de abuso formaram a base para a análise de riscos.

### Etapa 2 — Análise de riscos

As ameaças foram transformadas nos riscos R01–R06, que foram avaliados, priorizados e relacionados às funções do NIST Cybersecurity Framework 2.0.

Também foram definidos controles e estratégias de tratamento.

### Etapa 3 — Arquitetura segura

Os riscos prioritários deram origem aos requisitos RS01–RS03 e às decisões de arquitetura relacionadas principalmente à autenticação, autorização e proteção de informações.

### Etapa 4 — Código seguro e testes

Dois dos controles foram detalhados por meio de pseudocódigo: controle de autorização e limitação de tentativas de autenticação.

Os testes TS01–TS04 foram definidos antes das soluções para estabelecer previamente os comportamentos seguros esperados.

### Etapa 5 — Verificação de vulnerabilidades

Foi realizada uma verificação real utilizando OWASP Juice Shop e OWASP ZAP em ambiente local e autorizado.

Os resultados da ferramenta foram utilizados para analisar alertas e propor correções, demonstrando como verificações automatizadas podem fazer parte do processo de segurança.

### Etapa 6 — Monitoramento e detecção

Foram definidos eventos importantes para registro e três regras de detecção relacionadas aos riscos prioritários.

Essas regras representam a fase de monitoramento após a implantação do sistema.

## Considerações finais

A proposta demonstra que segurança pode ser incorporada de forma contínua ao desenvolvimento de software.

A análise começa antes da implementação, por meio da identificação de ameaças e riscos, influencia os requisitos e a arquitetura, orienta práticas de implementação e testes e continua após a implantação por meio de monitoramento e resposta.

O pipeline também utiliza condições de bloqueio para impedir que problemas relevantes de segurança avancem para etapas posteriores sem análise ou tratamento.

Dessa forma, o DevSecOps conecta as atividades realizadas durante o trabalho e permite manter rastreabilidade entre ameaças, riscos, requisitos, controles, testes, verificações e monitoramento.

# Roteiro do vídeo final

## 1. Introdução

Apresentar o Sistema de Agendamento de Consultas Médicas e explicar que o trabalho analisou sua segurança ao longo de sete etapas.

## 2. Etapa 1 — STRIDE e casos de abuso

Mostrar a tabela STRIDE e destacar as principais ameaças identificadas.

Mostrar brevemente os casos de abuso e o diagrama de casos de uso.

## 3. Etapa 2 — Análise de riscos

Mostrar o registro R01–R06.

Destacar os riscos críticos e explicar brevemente a priorização e o relacionamento com o NIST Cybersecurity Framework 2.0.

## 4. Etapa 3 — Arquitetura segura

Mostrar os requisitos RS01–RS03.

Abrir o diagrama de arquitetura segura e explicar principalmente os controles de autenticação, autorização e monitoramento.

## 5. Etapa 4 — Código seguro e testes

Mostrar que os testes TS01–TS04 foram definidos antes dos pseudocódigos.

Explicar brevemente as práticas de controle de autorização e limitação de tentativas de autenticação.

## 6. Etapa 5 — Verificação de vulnerabilidades

Mostrar o OWASP Juice Shop, a evidência da execução do OWASP ZAP e o relatório produzido.

Apresentar brevemente os três alertas selecionados e explicar que resultados automatizados precisam ser analisados antes de serem considerados vulnerabilidades confirmadas.

## 7. Etapa 6 — Monitoramento e detecção

Mostrar as regras RD01–RD03.

Explicar que elas detectam tentativas excessivas de autenticação, acessos indevidos a recursos e tentativas de execução de operações administrativas sem permissão.

## 8. Etapa 7 — DevSecOps

Mostrar o pipeline proposto.

Explicar como as etapas anteriores passam a fazer parte de um processo contínuo de segurança.

Apresentar as principais condições que impedem a continuidade do pipeline.

## 9. Conclusão

Destacar como principal aprendizado que segurança não deve ser tratada apenas após a implementação.

Explicar que existe uma continuidade entre:

`Ameaça → Risco → Requisito → Arquitetura → Implementação → Teste → Verificação → Monitoramento`
