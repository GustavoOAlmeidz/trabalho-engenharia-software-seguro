# Etapa 4 — Código Seguro e Testes de Segurança

## Práticas de código seguro selecionadas

Nesta etapa foram selecionadas duas práticas de código seguro relacionadas aos riscos, requisitos e decisões definidos nas etapas anteriores.

### Prática 1 — Controle de autorização

A primeira prática consiste em validar as permissões do usuário no servidor antes de permitir o acesso a recursos ou a execução de operações protegidas.

**Riscos relacionados:**

* R04 — Exposição indevida de informações;
* R06 — Acesso indevido a funções administrativas.

**Requisitos relacionados:**

* RS02 — Verificar se o usuário autenticado possui autorização para acessar cada informação de consulta ou agendamento solicitado;
* RS03 — Validar no servidor o perfil e as permissões do usuário antes da execução de operações administrativas.

### Prática 2 — Limitação de tentativas de autenticação

A segunda prática consiste em controlar tentativas consecutivas de autenticação e aplicar um bloqueio temporário quando o limite estabelecido for excedido.

**Risco relacionado:**

* R01 — Acesso indevido à conta de um paciente.

**Requisito relacionado:**

* RS01 — Limitar tentativas consecutivas de autenticação e bloquear temporariamente novas tentativas quando o limite definido for excedido.
