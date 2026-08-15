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