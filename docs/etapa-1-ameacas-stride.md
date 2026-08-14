# Etapa 1 — Casos de Abuso e Modelagem de Ameaças com STRIDE

## Identificação do sistema

**Sistema:** Sistema de Agendamento de Consultas Médicas

**Integrantes:**
- Gustavo
- Álvaro
- Leonardo

**Repositório:** [https://github.com/GustavoOAlmeidz/trabalho-engenharia-software-seguro]

## Justificativa da escolha

O sistema foi escolhido por envolver diferentes perfis de usuários, troca de informações e operações relevantes para a segurança, como autenticação, acesso a informações pessoais, gerenciamento de consultas e controle de permissões.

Essas características permitem analisar diferentes tipos de ameaças e casos de abuso ao longo das etapas do trabalho.

## Descrição do sistema

O Sistema de Agendamento de Consultas Médicas permite que pacientes consultem médicos e horários disponíveis, realizem agendamentos e cancelem consultas.

Os médicos podem visualizar sua agenda e acompanhar as consultas marcadas.

Os administradores são responsáveis pelo gerenciamento de médicos, horários e agendamentos.

Durante essas operações, são utilizadas informações pessoais, credenciais de acesso e dados relacionados às consultas, que precisam ser considerados durante a análise de segurança.