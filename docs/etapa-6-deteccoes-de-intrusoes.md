# Etapa 6 — Monitoramento e Detecção de Intrusões

## Detecção de intrusões

A detecção de intrusões consiste em observar eventos e comportamentos do sistema com o objetivo de identificar atividades suspeitas, tentativas de acesso indevido ou possíveis incidentes de segurança.

Enquanto os controles preventivos buscam impedir que uma ação maliciosa tenha sucesso, os mecanismos de detecção procuram identificar quando uma tentativa ou comportamento suspeito está ocorrendo ou já ocorreu.

## Prevenção e detecção

A prevenção atua antes ou durante uma ação para impedir que ela seja concluída.

Um exemplo é a validação de autorização antes de permitir que um usuário acesse um agendamento.

A detecção, por outro lado, utiliza registros e eventos para identificar comportamentos que podem indicar uma tentativa de ataque ou incidente.

Um exemplo é identificar várias tentativas consecutivas de autenticação malsucedidas para a mesma conta.

As duas abordagens são complementares. Mesmo com mecanismos preventivos, eventos relevantes precisam ser registrados para permitir monitoramento e investigação.

## Eventos que deveriam ser registrados

Considerando os riscos identificados nas etapas anteriores, os seguintes eventos deveriam ser registrados:

* autenticações bem-sucedidas;
* tentativas de autenticação malsucedidas;
* bloqueios temporários de contas;
* tentativas de acesso negado;
* acesso a funções administrativas;
* tentativas de executar operações administrativas sem permissão;
* criação de agendamentos;
* alteração e cancelamento de agendamentos;
* acesso a informações protegidas;
* erros relacionados a autenticação ou autorização;
* volume anormal de requisições.

Os registros deveriam permitir identificar, quando aplicável:

* usuário envolvido;
* operação realizada;
* recurso acessado;
* data e horário;
* resultado da operação;
* origem da requisição.

## Regras de detecção

### RD01 — Múltiplas tentativas de autenticação malsucedidas

| Campo              | Descrição                                                                                                 |
| ------------------ | --------------------------------------------------------------------------------------------------------- |
| Risco observado    | R01 — Acesso indevido à conta de um paciente                                                              |
| Fonte de dados     | Logs de autenticação                                                                                      |
| Condição de alerta | Uma mesma conta apresenta várias tentativas consecutivas de autenticação malsucedidas em um curto período |
| Resposta inicial   | Registrar o alerta, aplicar o bloqueio temporário configurado e analisar as tentativas realizadas         |

Essa regra busca identificar possíveis ataques automatizados de tentativa de descoberta de credenciais.

### RD02 — Tentativa de acesso a recurso de outro usuário

| Campo              | Descrição                                                                                                   |
| ------------------ | ----------------------------------------------------------------------------------------------------------- |
| Risco observado    | R04 — Exposição indevida de informações                                                                     |
| Fonte de dados     | Logs de autorização e acesso a recursos                                                                     |
| Condição de alerta | Um usuário tenta repetidamente acessar consultas ou agendamentos para os quais não possui autorização       |
| Resposta inicial   | Negar o acesso, registrar as tentativas e avaliar se existe comportamento malicioso ou falha de autorização |

Essa regra permite identificar tentativas de acesso indevido a informações pertencentes a outros usuários.

### RD03 — Tentativa de operação administrativa sem permissão

| Campo              | Descrição                                                                               |
| ------------------ | --------------------------------------------------------------------------------------- |
| Risco observado    | R06 — Acesso indevido a funções administrativas                                         |
| Fonte de dados     | Logs de autorização e operações administrativas                                         |
| Condição de alerta | Um usuário sem perfil administrativo tenta executar uma ou mais funções administrativas |
| Resposta inicial   | Negar a operação, registrar o evento e analisar a conta e a origem da tentativa         |

Essa regra busca detectar tentativas de obtenção ou utilização indevida de privilégios.

## Ações após um alerta

Após a geração de um alerta, inicialmente deve-se confirmar se o evento representa um comportamento realmente suspeito ou apenas uma situação legítima.

Quando necessário, a resposta poderá envolver:

* análise dos registros relacionados;
* identificação do usuário e das operações envolvidas;
* bloqueio temporário de uma conta;
* limitação temporária de novas requisições;
* preservação dos registros utilizados como evidência;
* correção de uma possível falha identificada;
* acompanhamento do comportamento após a resposta.

A intensidade da resposta deverá considerar o risco envolvido e as evidências disponíveis.

## Considerações finais

A detecção complementa os controles preventivos definidos anteriormente, permitindo identificar comportamentos suspeitos que não foram completamente impedidos pelos mecanismos de segurança.

As três regras propostas foram diretamente relacionadas aos riscos prioritários R01, R04 e R06, mantendo a continuidade da análise realizada nas etapas anteriores.

O registro adequado dos eventos é essencial para que alertas possam ser investigados e para que decisões de resposta sejam tomadas com base em evidências.
