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
## Resultados da verificação

A execução do OWASP ZAP analisou 461 URLs da aplicação e identificou 13 alertas novos classificados como `WARN`, sem alertas classificados como `FAIL`.

Para esta etapa foram selecionados três achados relacionados à ausência de mecanismos de proteção presentes nos cabeçalhos HTTP da aplicação.

| ID | Alerta ou achado | Evidência | Possível impacto | Relação com OWASP ou CWE | Correção proposta |
|---|---|---|---|---|---|
| A01 | Missing Anti-clickjacking Header | ZAP [10020] | A aplicação pode permitir que suas páginas sejam carregadas dentro de frames de outros sites, possibilitando ataques de clickjacking e induzindo o usuário a executar ações sem perceber | CWE-1021 | Configurar `Content-Security-Policy` com a diretiva `frame-ancestors` ou utilizar `X-Frame-Options` de acordo com a necessidade da aplicação |
| A02 | X-Content-Type-Options Header Missing | ZAP [10021] | A ausência do cabeçalho pode permitir que o navegador interprete o conteúdo com um tipo MIME diferente daquele declarado, aumentando o risco de interpretação indevida de conteúdo | CWE-693 | Configurar corretamente o `Content-Type` das respostas e adicionar `X-Content-Type-Options: nosniff` |
| A03 | Content Security Policy (CSP) Header Not Set | ZAP [10038] | A ausência de CSP reduz a capacidade do navegador de restringir as origens de scripts, estilos e outros recursos, diminuindo a proteção adicional contra ataques como XSS e injeção de conteúdo | CWE-693 | Definir uma política `Content-Security-Policy` compatível com os recursos utilizados pela aplicação e restringir as origens permitidas |

### A01 — Missing Anti-clickjacking Header

O ZAP identificou ausência de proteção contra clickjacking em uma resposta da aplicação.

Nesse tipo de situação, uma página pode ser carregada dentro de um frame controlado por outro site. Um atacante poderia utilizar elementos visuais sobrepostos para induzir o usuário a interagir com a aplicação sem compreender exatamente a ação realizada.

O resultado não comprova que um ataque de clickjacking foi explorado, mas demonstra a ausência de uma proteção recomendada contra esse tipo de ameaça.

A correção consiste em impedir o enquadramento não autorizado das páginas por meio da diretiva `frame-ancestors` da Content Security Policy ou pelo cabeçalho `X-Frame-Options`.

### A02 — X-Content-Type-Options Header Missing

O ZAP identificou respostas que não possuem o cabeçalho `X-Content-Type-Options` configurado como `nosniff`.

Sem essa diretiva, determinados navegadores podem tentar inferir o tipo do conteúdo recebido em vez de respeitar exclusivamente o tipo declarado pelo servidor.

Embora o alerta tenha sido classificado com risco menor, a configuração do cabeçalho reduz comportamentos inesperados de interpretação de conteúdo e funciona como uma medida adicional de segurança.

A correção consiste em garantir que as respostas utilizem o `Content-Type` adequado e incluir:

`X-Content-Type-Options: nosniff`

### A03 — Content Security Policy (CSP) Header Not Set

O ZAP identificou diferentes recursos da aplicação sem o cabeçalho `Content-Security-Policy`.

A CSP permite que a aplicação determine quais origens podem fornecer scripts, estilos, imagens e outros recursos carregados pelo navegador.

Sua ausência não significa que a aplicação possua automaticamente uma vulnerabilidade XSS, mas reduz uma camada adicional de defesa caso uma falha de injeção esteja presente.

A correção consiste em definir uma política CSP adequada ao funcionamento da aplicação, permitindo somente as origens e tipos de conteúdo necessários.

## Limitações da verificação

A verificação realizada utilizou o ZAP Baseline Scan, baseado principalmente em análise passiva das respostas observadas durante a navegação automatizada.

Os alertas identificados não devem ser considerados automaticamente como vulnerabilidades exploráveis. Cada resultado precisa ser interpretado considerando o contexto da aplicação.

Também podem existir vulnerabilidades que não foram identificadas por essa execução, especialmente aquelas que dependem de autenticação, estados específicos da aplicação, lógica de negócio ou testes ativos.

Os resultados informativos, duplicados ou que não apresentaram relevância suficiente para o objetivo desta etapa não foram selecionados para análise detalhada.

## Considerações finais

A execução do OWASP ZAP sobre o OWASP Juice Shop permitiu observar, em um ambiente controlado e autorizado, como uma ferramenta automatizada pode auxiliar na identificação de configurações e comportamentos potencialmente inseguros.

Foram selecionados para análise três alertas relacionados a mecanismos de proteção do navegador: ausência de proteção contra clickjacking, ausência do cabeçalho `X-Content-Type-Options` e ausência de uma política Content Security Policy.

A análise demonstrou que os resultados produzidos por ferramentas automatizadas precisam ser interpretados antes que sejam tratados como vulnerabilidades confirmadas. Os alertas fornecem evidências importantes para orientar verificações posteriores e possíveis correções, mas não substituem análise manual, testes específicos e avaliação do contexto.

As correções propostas envolvem principalmente a configuração adequada de cabeçalhos HTTP de segurança e a definição explícita das políticas aplicadas pelo navegador.