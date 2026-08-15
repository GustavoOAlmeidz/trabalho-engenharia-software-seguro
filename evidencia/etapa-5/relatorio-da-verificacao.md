# Etapa 5 — Verificação de Vulnerabilidades

## Ambiente testado

A verificação será realizada sobre o OWASP Juice Shop executado localmente em ambiente controlado.

O Juice Shop é uma aplicação deliberadamente vulnerável utilizada para fins educacionais e treinamento em segurança de aplicações.

A aplicação utilizada nesta etapa não corresponde ao Sistema de Agendamento de Consultas Médicas analisado nas etapas anteriores. Como esse sistema é apenas objeto de análise e não foi implementado, foi utilizado o ambiente educacional permitido pelo enunciado do trabalho.

## Ferramenta utilizada

A ferramenta selecionada para a verificação foi o OWASP ZAP (Zed Attack Proxy).

O ZAP será utilizado para percorrer a aplicação e identificar possíveis alertas relacionados a configurações ou comportamentos inseguros.

## Configuração do teste

A aplicação e a ferramenta serão executadas localmente utilizando contêineres Docker em uma rede isolada.

Será utilizada inicialmente uma verificação do tipo Baseline Scan, permitindo que o ZAP percorra a aplicação e execute análises passivas sobre as respostas observadas.

### Ambiente

- Aplicação: OWASP Juice Shop
- Ferramenta: OWASP ZAP
- Execução: ambiente local
- Isolamento: contêineres Docker
- Tipo inicial de verificação: Baseline Scan
- Alvo: instância local do OWASP Juice Shop