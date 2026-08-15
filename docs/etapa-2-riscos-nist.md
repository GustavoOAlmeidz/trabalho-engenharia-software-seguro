# Etapa 2 — Análise, Priorização e Tratamento de Riscos com o NIST CSF

## Critérios de avaliação dos riscos

Para avaliar os riscos identificados a partir das ameaças da Etapa 1, serão considerados dois critérios: probabilidade e impacto.

A combinação desses critérios permitirá calcular a pontuação de cada risco e classificá-lo de acordo com sua relevância para o Sistema de Agendamento de Consultas Médicas.

### Critérios de probabilidade

| Valor | Classificação | Critério |
|---|---|---|
| 1 | Baixa | O evento depende de condições incomuns, acesso muito específico ou grande capacidade técnica |
| 2 | Média-baixa | O evento é possível, mas depende de uma vulnerabilidade ou condição específica |
| 3 | Média-alta | O evento é plausível e pode ocorrer em situações comuns de uso ou ataque |
| 4 | Alta | O evento pode ocorrer com facilidade, frequência ou durante condições previsíveis do sistema |

A probabilidade será definida considerando as características do sistema, os usuários envolvidos, as condições necessárias para exploração e a facilidade com que cada ameaça pode ocorrer.

### Critérios de impacto

| Valor | Classificação | Critério |
|---|---|---|
| 1 | Baixo | Causa pequeno transtorno e pode ser corrigido rapidamente |
| 2 | Moderado | Causa interrupção ou inconsistência limitada, com possibilidade de recuperação |
| 3 | Alto | Causa prejuízo relevante aos usuários, ao funcionamento do sistema ou à privacidade |
| 4 | Muito alto | Pode afetar muitos usuários, comprometer operações importantes ou causar prejuízo grave |

Na avaliação do impacto serão considerados fatores como exposição de informações, indisponibilidade do serviço, alteração indevida de dados, comprometimento de operações importantes e dificuldade de recuperação.

### Cálculo e classificação

A pontuação de cada risco será calculada pela seguinte fórmula:

`Pontuação = Probabilidade × Impacto`

A classificação seguirá os intervalos abaixo:

| Pontuação | Nível do risco |
|---|---|
| 1 a 3 | Baixo |
| 4 a 7 | Médio |
| 8 a 11 | Alto |
| 12 a 16 | Crítico |

## Registro de riscos

As ameaças identificadas na Etapa 1 foram transformadas em eventos de risco para permitir sua avaliação e priorização.

| ID | Origem STRIDE | Evento de risco | Vulnerabilidade ou condição | Probabilidade | Impacto | Pontuação | Nível |
|---|---|---|---|---:|---:|---:|---|
| R01 | Spoofing | Um atacante acessa a conta de um paciente e realiza operações em seu nome | Comprometimento de credenciais e proteção insuficiente do processo de autenticação | 3 | 4 | 12 | Crítico |
| R02 | Tampering | Um usuário altera ou cancela um agendamento pertencente a outro paciente | Falha na validação de autorização e propriedade do agendamento | 3 | 3 | 9 | Alto |
| R03 | Repudiation | Um usuário realiza uma operação e posteriormente nega ter executado a ação | Ausência ou insuficiência de registros de auditoria das operações | 2 | 2 | 4 | Médio |
| R04 | Information Disclosure | Informações pessoais ou de consultas são acessadas por usuários sem autorização | Falha no controle de acesso aos dados e recursos do sistema | 3 | 4 | 12 | Crítico |
| R05 | Denial of Service | O serviço de agendamento torna-se indisponível devido ao excesso de requisições | Ausência de mecanismos suficientes para limitar ou controlar requisições excessivas | 3 | 3 | 9 | Alto |
| R06 | Elevation of Privilege | Um usuário comum consegue utilizar funções administrativas | Controle inadequado de perfis e permissões nas operações administrativas | 2 | 4 | 8 | Alto |

## Justificativa das avaliações

### R01 — Acesso indevido à conta de um paciente

**Probabilidade: 3 — Média-alta**

O comprometimento de credenciais é uma situação plausível em sistemas que utilizam autenticação por usuário e senha. Credenciais podem ser obtidas por reutilização de senhas, engenharia social ou outros meios.

**Impacto: 4 — Muito alto**

O atacante poderia visualizar informações pessoais e realizar operações em nome do paciente, incluindo alteração ou cancelamento de agendamentos. A situação compromete a privacidade e a integridade das operações realizadas pela conta.

Por essas razões, o risco recebeu pontuação 12 e foi classificado como crítico.

### R02 — Alteração indevida de agendamento

**Probabilidade: 3 — Média-alta**

Caso a autorização das operações não verifique corretamente a relação entre o usuário autenticado e o agendamento solicitado, um usuário poderá tentar manipular identificadores para acessar recursos pertencentes a outras pessoas.

**Impacto: 3 — Alto**

A exploração pode resultar em alteração ou cancelamento de consultas, causando inconsistência na agenda e prejuízo aos pacientes e profissionais envolvidos.

A pontuação resultante é 9, classificando o risco como alto.

### R03 — Repúdio de operações realizadas

**Probabilidade: 2 — Média-baixa**

A situação depende da ausência ou insuficiência de registros que permitam relacionar uma operação ao usuário responsável.

**Impacto: 2 — Moderado**

A falta de evidências não necessariamente compromete diretamente todo o sistema, mas dificulta a investigação de incidentes, a resolução de conflitos e a identificação de responsabilidades.

A pontuação resultante é 4, classificando o risco como médio.

### R04 — Exposição indevida de informações

**Probabilidade: 3 — Média-alta**

Falhas de autorização podem permitir que um usuário autenticado acesse informações associadas a outros usuários, principalmente quando recursos são identificados diretamente nas requisições.

**Impacto: 4 — Muito alto**

O risco envolve exposição de dados pessoais e informações relacionadas às consultas. Além de comprometer a privacidade dos pacientes, uma ocorrência pode afetar a confiança no sistema e gerar consequências administrativas ou legais.

A pontuação resultante é 12, classificando o risco como crítico.

### R05 — Indisponibilidade do serviço de agendamento

**Probabilidade: 3 — Média-alta**

Serviços acessíveis por rede podem receber grande volume de requisições, seja por comportamento malicioso ou uso excessivo. Sem mecanismos de limitação, esse volume pode afetar os recursos disponíveis.

**Impacto: 3 — Alto**

A indisponibilidade impede pacientes de realizar ou cancelar agendamentos e impede médicos de consultar normalmente suas agendas.

A pontuação resultante é 9, classificando o risco como alto.

### R06 — Acesso indevido a funções administrativas

**Probabilidade: 2 — Média-baixa**

A exploração depende da existência de falhas específicas no controle de autorização, como a validação inadequada do perfil do usuário antes da execução de operações administrativas.

**Impacto: 4 — Muito alto**

Caso seja explorada, a falha poderá permitir o gerenciamento indevido de médicos, horários e agendamentos. O atacante poderia realizar alterações com efeito sobre vários usuários e comprometer operações importantes do sistema.

A pontuação resultante é 8, classificando o risco como alto.

## Priorização dos riscos

A priorização considera não apenas a pontuação calculada, mas também a importância dos ativos afetados, a quantidade potencial de usuários impactados, a gravidade das consequências e a possibilidade de recuperação.

| Prioridade | Risco | Pontuação | Nível |
|---:|---|---:|---|
| 1 | R01 — Acesso indevido à conta de um paciente | 12 | Crítico |
| 2 | R04 — Exposição indevida de informações | 12 | Crítico |
| 3 | R06 — Acesso indevido a funções administrativas | 8 | Alto |
| 4 | R05 — Indisponibilidade do serviço de agendamento | 9 | Alto |
| 5 | R02 — Alteração indevida de agendamento | 9 | Alto |
| 6 | R03 — Repúdio de operações realizadas | 4 | Médio |

### Justificativa da priorização

O R01 recebeu a maior prioridade porque o comprometimento de uma conta permite que um atacante se passe por um usuário legítimo, acesse informações pessoais e realize operações em seu nome.

O R04 aparece em seguida porque envolve diretamente a exposição de informações pessoais e dados relacionados às consultas, apresentando impacto elevado sobre a privacidade dos usuários.

Embora o R06 tenha pontuação inferior a R05 e R02, foi colocado antes deles porque a obtenção de privilégios administrativos pode permitir alterações com alcance maior, afetando médicos, horários e diversos agendamentos.

O R05 possui alta prioridade devido ao impacto da indisponibilidade sobre pacientes e médicos que dependem do sistema.

O R02 também possui nível alto, porém normalmente afeta inicialmente agendamentos específicos, apresentando alcance menor do que os riscos anteriores.

O R03 foi classificado por último por possuir impacto mais limitado e não causar, isoladamente, comprometimento imediato da confidencialidade, integridade ou disponibilidade do serviço.

## Estratégias de tratamento

Para cada risco foi escolhida uma estratégia principal de tratamento.

| Risco | Estratégia | Justificativa |
|---|---|---|
| R01 | Reduzir | Controles adicionais de autenticação podem diminuir a probabilidade de acesso indevido às contas |
| R02 | Reduzir | A validação de autorização e propriedade dos recursos pode impedir alterações indevidas |
| R03 | Reduzir | Registros de auditoria podem fornecer evidências sobre as operações realizadas |
| R04 | Reduzir | Controles de autorização e restrição de acesso podem limitar a exposição de informações |
| R05 | Reduzir | Limitação de requisições e monitoramento podem diminuir a possibilidade e o impacto da sobrecarga |
| R06 | Reduzir | Controle de acesso baseado em perfis e validação no servidor podem impedir o uso indevido de funções administrativas |

A estratégia de redução foi predominante porque os riscos identificados estão relacionados a funções necessárias ao sistema. Eliminar completamente essas operações impediria o funcionamento esperado do serviço, enquanto a adoção de controles permite reduzir sua probabilidade ou impacto.

## Funções do NIST Cybersecurity Framework 2.0

Os riscos e controles serão relacionados às seis funções do NIST Cybersecurity Framework 2.0.

| Função | Finalidade |
|---|---|
| Govern | Definir políticas, responsabilidades, prioridades e critérios de decisão |
| Identify | Conhecer ativos, dependências, vulnerabilidades e riscos |
| Protect | Implementar salvaguardas para reduzir a probabilidade ou o impacto |
| Detect | Identificar eventos suspeitos, falhas e possíveis incidentes |
| Respond | Conter, analisar, comunicar e tratar incidentes |
| Recover | Restaurar serviços e dados e reduzir os prejuízos causados |

As funções representam resultados de segurança esperados e não devem ser confundidas com controles específicos. Por exemplo, Protect representa uma função, enquanto a validação de autorização antes de uma operação é um controle que pode contribuir para essa função.

## Mapeamento dos riscos para o NIST CSF

| Risco | Govern | Identify | Protect | Detect | Respond | Recover |
|---|:---:|:---:|:---:|:---:|:---:|:---:|
| R01 | X |  | X | X | X |  |
| R02 |  |  | X | X | X | X |
| R03 | X |  |  | X | X |  |
| R04 | X | X | X | X | X |  |
| R05 |  | X | X | X | X | X |
| R06 | X |  | X | X | X |  |

### Justificativa do mapeamento

**R01:** exige políticas de autenticação e responsabilidades, mecanismos de proteção das contas, detecção de acessos suspeitos e resposta em caso de comprometimento.

**R02:** necessita de proteção das operações, detecção de alterações indevidas, resposta ao incidente e possibilidade de recuperação de informações ou agendamentos alterados.

**R03:** envolve definição de responsabilidades e registros capazes de detectar e permitir a investigação de operações realizadas.

**R04:** exige identificação dos dados que precisam ser protegidos, políticas de acesso, controles preventivos, detecção de acessos indevidos e resposta em caso de exposição.

**R05:** exige conhecimento dos recursos e dependências necessários ao funcionamento do serviço, mecanismos de proteção contra sobrecarga, detecção, resposta e recuperação da disponibilidade.

**R06:** exige regras de governança sobre privilégios, controles de autorização, detecção de tentativas indevidas e resposta a possíveis comprometimentos.

## Plano de tratamento dos riscos

| Risco | Estratégia | Controles propostos | Funções relacionadas | Responsáveis | Evidências e verificação |
|---|---|---|---|---|---|
| R01 | Reduzir | Limitar tentativas de autenticação; armazenar senhas de forma segura; encerrar sessões após período de inatividade; utilizar autenticação adicional em contas privilegiadas | Govern, Protect, Detect, Respond | Desenvolvimento e segurança | Testes de autenticação, registros de tentativas, testes de sessão e revisão das configurações |
| R02 | Reduzir | Validar no servidor se o usuário possui permissão sobre o agendamento antes de permitir alteração ou cancelamento; registrar alterações realizadas | Protect, Detect, Respond, Recover | Desenvolvimento | Testes com usuários tentando alterar agendamentos próprios e de terceiros; análise dos logs |
| R03 | Reduzir | Registrar usuário, operação, recurso afetado, data, horário e resultado das operações relevantes; proteger registros contra alteração indevida | Govern, Detect, Respond | Desenvolvimento e infraestrutura | Inspeção dos logs e simulação de operações para verificar a geração correta dos registros |
| R04 | Reduzir | Validar autorização em todas as consultas de dados; retornar apenas informações necessárias ao usuário; registrar acessos a informações sensíveis | Govern, Identify, Protect, Detect, Respond | Desenvolvimento e segurança | Testes de acesso entre usuários diferentes e revisão das respostas retornadas pelo sistema |
| R05 | Reduzir | Aplicar limitação de requisições; definir limites de tempo para operações; monitorar volume de requisições e disponibilidade do serviço | Identify, Protect, Detect, Respond, Recover | Desenvolvimento e infraestrutura | Testes de carga controlados, métricas de disponibilidade e registros de requisições |
| R06 | Reduzir | Implementar controle de acesso baseado em perfis; negar operações por padrão quando não houver permissão; validar autorização no servidor em todas as funções administrativas | Govern, Protect, Detect, Respond | Desenvolvimento e segurança | Testes de autorização com diferentes perfis e revisão dos registros de operações administrativas |

## Ordem inicial de implementação dos controles

A implementação dos controles deverá considerar a criticidade dos riscos, as dependências entre as medidas e a possibilidade de um mesmo controle reduzir mais de um risco.

### 1. Controle de autorização

A primeira prioridade será garantir que todas as operações protegidas validem as permissões do usuário no servidor.

Esse controle contribui principalmente para o tratamento de R02, R04 e R06, reduzindo alterações indevidas, exposição de informações e uso não autorizado de funções administrativas.

### 2. Proteção do processo de autenticação

Em seguida deverão ser implementados controles relacionados à autenticação, como proteção das credenciais, limitação de tentativas e gerenciamento adequado das sessões.

Essas medidas estão diretamente relacionadas ao R01.

### 3. Registro e auditoria de operações

Depois deverão ser implementados registros das operações relevantes, principalmente autenticações, alterações de agendamento, acessos administrativos e tentativas negadas.

Esse controle trata diretamente o R03 e também contribui para a detecção e investigação dos demais riscos.

### 4. Proteção contra exposição de informações

As respostas e consultas do sistema deverão ser revisadas para garantir que cada usuário receba apenas as informações necessárias e autorizadas.

Esse conjunto de controles está diretamente relacionado ao R04.

### 5. Proteção da disponibilidade

Por fim, deverão ser implementados mecanismos de limitação de requisições, monitoramento e recuperação do serviço para reduzir o R05.

Essa ordem poderá ser revista conforme os controles forem detalhados e verificados nas próximas etapas.

## Estimativa do risco residual

Os níveis abaixo representam uma estimativa do risco esperado após a implementação e validação dos controles propostos. Não representam uma redução já comprovada.

| Risco | Nível inicial | Nível residual esperado | Condição para aceitar o residual |
|---|---|---|---|
| R01 | Crítico | Médio | Controles de autenticação implementados, testados e tentativas suspeitas registradas |
| R02 | Alto | Médio | Autorização validada no servidor e testes impedindo alteração de agendamentos de terceiros |
| R03 | Médio | Baixo | Operações relevantes registradas de forma consistente e registros protegidos contra alterações indevidas |
| R04 | Crítico | Médio | Testes comprovando que usuários não conseguem acessar informações pertencentes a terceiros |
| R05 | Alto | Médio | Limitação de requisições, monitoramento e procedimentos de recuperação verificados |
| R06 | Alto | Médio | Controle de acesso por perfil aplicado e testes comprovando a negação de funções administrativas a usuários comuns |

Mesmo após a implementação dos controles, os riscos não serão considerados eliminados. O nível residual deverá ser reavaliado com base nos resultados de testes e nas evidências obtidas.

## Considerações finais

A análise demonstrou que os riscos de maior prioridade estão relacionados ao comprometimento de contas, à exposição de informações e ao acesso indevido a funções privilegiadas.

Os riscos R01 e R04 foram classificados como críticos devido à combinação entre probabilidade de ocorrência e impacto sobre os usuários e suas informações. O R06, apesar de possuir pontuação inferior a outros riscos classificados como altos, recebeu prioridade elevada devido ao alcance que permissões administrativas indevidas podem proporcionar.

A estratégia predominante foi a redução dos riscos por meio da aplicação de controles específicos de autenticação, autorização, auditoria, proteção de dados e disponibilidade.

Entre as funções do NIST CSF 2.0, Protect e Detect possuem presença relevante no plano definido, pois grande parte dos riscos exige tanto medidas preventivas quanto capacidade de identificação de comportamentos suspeitos. Govern, Identify, Respond e Recover também foram relacionados conforme as características de cada risco.

Os controles considerados mais importantes são a validação de autorização no servidor, a proteção do processo de autenticação, o registro de operações relevantes e a restrição do acesso às informações.

A principal limitação desta análise é que o sistema não está implementado. Dessa forma, os valores de probabilidade, impacto e risco residual representam estimativas baseadas no funcionamento definido para o sistema e deverão ser revisados caso existam novas informações ou evidências.

As próximas etapas deverão transformar os riscos prioritários e os controles propostos em requisitos de segurança e decisões de arquitetura.