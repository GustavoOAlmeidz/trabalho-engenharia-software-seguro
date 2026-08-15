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

## Testes de segurança

Os testes foram definidos antes da proposta de implementação, de modo que o comportamento seguro esperado esteja estabelecido previamente.

### Testes da Prática 1 — Controle de autorização

| Teste | Entrada ou ação | Resultado esperado |
|---|---|---|
| TS01 | Um paciente autenticado solicita a visualização de um agendamento pertencente à própria conta | O acesso é permitido |
| TS02 | Um paciente autenticado tenta visualizar ou alterar um agendamento pertencente a outro paciente | A operação é recusada e a tentativa é registrada |

### Testes da Prática 2 — Limitação de tentativas de autenticação

| Teste | Entrada ou ação | Resultado esperado |
|---|---|---|
| TS03 | Um usuário informa credenciais válidas sem possuir bloqueio ativo | A autenticação é permitida e o contador de falhas é reiniciado |
| TS04 | Um usuário excede o limite configurado de tentativas consecutivas de autenticação malsucedidas | Novas tentativas são temporariamente recusadas e o bloqueio é registrado |

## Implementação/pseudocódigo

### Prática 1 — Controle de autorização

A autorização deverá ser verificada no servidor antes do acesso ao recurso solicitado. A simples autenticação do usuário não é suficiente para determinar se ele possui permissão sobre determinado agendamento.

O controle deverá adotar negação por padrão quando as condições necessárias de autorização não forem atendidas.

```text
FUNÇÃO visualizarAgendamento(usuario, idAgendamento)

    SE usuario NÃO estiver autenticado
        registrar tentativa negada
        NEGAR acesso
    FIM

    agendamento = buscarAgendamento(idAgendamento)

    SE agendamento NÃO existir
        RETORNAR recurso não encontrado
    FIM

    SE usuario.perfil == ADMINISTRADOR
        PERMITIR acesso
    FIM

    SE usuario.perfil == PACIENTE E
       agendamento.pacienteId == usuario.id
        PERMITIR acesso
    FIM

    SE usuario.perfil == MEDICO E
       agendamento.medicoId == usuario.id
        PERMITIR acesso
    FIM

    registrar tentativa de acesso não autorizado
    NEGAR acesso

FIM
```
Para operações administrativas, o mesmo princípio deverá ser aplicado

```text
FUNÇÃO executarOperacaoAdministrativa(usuario, operacao)

    SE usuario NÃO estiver autenticado
        NEGAR operação
    FIM

    SE usuario.perfil != ADMINISTRADOR
        registrar tentativa não autorizada
        NEGAR operação
    FIM

    executar operacao
    registrar operação realizada

FIM
```

Resultado esperado: somente usuários explicitamente autorizados poderão acessar recursos ou executar operações protegidas. 
Requisições sem permissão deverão ser recusadas independentemente das opções exibidas pela interface.

Referência utilizada: OWASP Cheat Sheet Series — Authorization Cheat Sheet.

### Prática 2 — Limitação de tentativas de autenticação

O processo de autenticação deverá controlar a quantidade de tentativas consecutivas malsucedidas associadas à conta do usuário.

Quando o limite configurado for excedido, novas tentativas deverão ser temporariamente bloqueadas. Falhas de autenticação e bloqueios deverão ser registrados para permitir monitoramento posterior.

```text
FUNÇÃO autenticar(identificador, senha)

    usuario = buscarUsuario(identificador)

    SE usuario NÃO existir
        registrar falha de autenticação
        RETORNAR credenciais inválidas
    FIM

    SE usuario.bloqueadoAte > horarioAtual
        registrar tentativa durante bloqueio
        NEGAR autenticação
    FIM

    SE senha estiver correta
        usuario.tentativasFalhas = 0
        registrar autenticação bem-sucedida
        PERMITIR autenticação
    FIM

    usuario.tentativasFalhas =
        usuario.tentativasFalhas + 1

    registrar falha de autenticação

    SE usuario.tentativasFalhas >= LIMITE_TENTATIVAS
        usuario.bloqueadoAte =
            horarioAtual + PERIODO_BLOQUEIO

        registrar bloqueio temporário
    FIM

    RETORNAR credenciais inválidas

FIM
```
O valor de LIMITE_TENTATIVAS e a duração de PERIODO_BLOQUEIO deverão ser definidos por configuração, permitindo ajustes sem alteração da lógica principal.

O contador de tentativas deverá estar associado à conta do usuário, evitando que a proteção dependa somente do endereço de origem da requisição.

Resultado esperado: sucessivas tentativas de autenticação malsucedidas não poderão continuar indefinidamente, reduzindo a possibilidade de ataques automatizados de adivinhação de credenciais.

Referência utilizada: OWASP Cheat Sheet Series — Authentication Cheat Sheet.

## Resultados esperados

A aplicação das duas práticas deverá contribuir diretamente para a redução dos riscos prioritários identificados nas etapas anteriores.

### Controle de autorização

Espera-se que:

- usuários não consigam acessar agendamentos pertencentes a outros usuários sem autorização;
- pacientes e médicos não consigam executar funções administrativas;
- operações sem autorização explícita sejam recusadas;
- tentativas de acesso indevido sejam registradas.

Esses resultados contribuem para reduzir principalmente os riscos R04 e R06 e atendem aos requisitos RS02 e RS03.

### Limitação de tentativas de autenticação

Espera-se que:

- autenticações válidas continuem funcionando normalmente;
- tentativas malsucedidas sejam contabilizadas;
- contas que excedam o limite configurado recebam bloqueio temporário;
- tentativas e bloqueios sejam registrados;
- uma autenticação válida após o término do bloqueio possa ocorrer normalmente.

Esses resultados contribuem para reduzir o risco R01 e atender ao requisito RS01.

## Referências utilizadas

- OWASP Cheat Sheet Series — Authorization Cheat Sheet.
- OWASP Cheat Sheet Series — Authentication Cheat Sheet.

## Considerações finais

As práticas selecionadas demonstram como os requisitos e decisões de segurança definidos nas etapas anteriores podem ser transformados em comportamentos concretos de implementação.

O controle de autorização busca impedir que um usuário autenticado utilize recursos ou funções para os quais não possui permissão. Já a limitação de tentativas de autenticação busca dificultar ataques automatizados contra contas de usuários.

Os testes foram definidos antes dos pseudocódigos para estabelecer previamente os comportamentos seguros esperados. Como o sistema analisado não está implementado, os resultados apresentados representam o comportamento que deverá ser verificado caso essas práticas sejam implementadas em uma aplicação real.

