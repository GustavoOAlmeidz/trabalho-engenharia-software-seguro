# Etapa 3 — Projeto de uma Arquitetura Segura

## Requisitos de segurança

Os requisitos de segurança foram derivados dos riscos prioritários identificados na Etapa 2.

Foram selecionados os riscos R01, R04 e R06 por apresentarem níveis crítico ou alto e estarem diretamente relacionados à autenticação, proteção de informações e controle de acesso.

| ID | Risco de origem | Requisito de segurança | Critério de verificação |
|---|---|---|---|
| RS01 | R01 | O sistema deverá limitar tentativas consecutivas de autenticação e bloquear temporariamente novas tentativas quando o limite definido for excedido | Após tentativas consecutivas malsucedidas acima do limite configurado, uma nova tentativa deverá ser temporariamente recusada e o evento deverá ser registrado |
| RS02 | R04 | O sistema deverá verificar se o usuário autenticado possui autorização para acessar cada informação de consulta ou agendamento solicitado | Uma tentativa de acessar informações pertencentes a outro usuário deverá ser recusada |
| RS03 | R06 | O sistema deverá validar no servidor o perfil e as permissões do usuário antes da execução de qualquer operação administrativa | Uma operação administrativa solicitada por um paciente ou médico sem permissão deverá ser recusada e registrada |