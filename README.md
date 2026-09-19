Análise de Conformidade Regulatória — APIs Open Finance

Auditoria de dados aplicada a métricas de performance de instituições financeiras (IFs) no ecossistema Open Finance, com foco em conformidade de SLA e identificação de padrões de risco.

Nota: este é um case técnico de estudo, desenvolvido a partir de dados anonimizados (instituições identificadas apenas como "IF 1" e "IF 2"). Não representa um projeto de cliente real ou dados confidenciais.

🎯 Objetivo

Auditar a conformidade de instituições financeiras participantes do Open Finance em relação a dois indicadores regulatórios:

Pareamento Diário — % de chamadas de API processadas com sucesso
Desempenho (P95) — tempo de resposta em que 95% das chamadas foram mais rápidas, comparado ao SLA definido por API

O objetivo final é diagnosticar problemas de conformidade e fornecer base técnica para recomendações de ação corretiva.

🔎 Principais Insights

1. Risco Agudo (IF 1) — comprovado por outliers catastróficos Instituição geralmente estável, mas com dias de P95 acima de 15.000ms (SLA: 1.300–1.500ms) e quedas de pareamento a 0%, indicando perda total de registro em momentos de pico.

2. Risco Crônico (IF 2) — falha estrutural, não pontual A API Fixed Incomes da IF 2 ficou em desconformidade de SLA por 19 dias no mês — um padrão persistente, não um evento isolado.

3. A média do sistema mascara o risco real A performance superior da IF 1 eleva a média consolidada do ecossistema. Isoladamente, o pareamento médio da IF 2 (79,43%) fica bem abaixo da meta de 95%, revelando o "elo fraco" que compromete a confiança de todo o sistema.

Conclusão: os dois perfis de risco exigem respostas diferentes — um Plano de Mitigação focado em resiliência para a IF 1, e um Plano de Ação Corretiva mais rigoroso e supervisionado para a IF 2.

📊 Visualizações
Gráficos de linha de pareamento diário por instituição e API, com meta de 95%
Box plots de distribuição de desempenho (P95) por API, com faixas de SLA
Heatmap de conformidade diária (Conforme/Desconforme) por instituição
Gráfico de quadrantes: Pareamento (%) vs. Desempenho (P95), classificando cada dia em Ideal / Falha de Pareamento / Falha de Desempenho / Crítico


🛠️ Metodologia
Importação e limpeza dos dados (padronização de nomes de colunas e APIs)
Cálculo de métricas diárias agrupadas por data, instituição e API
Definição de regras de conformidade (limite de SLA por API, limite de dias em desconformidade)
Visualização exploratória e por quadrante de risco
Síntese de insights e recomendações
💻 Tecnologias
Python (Pandas, NumPy)
Visualização: Plotly, Matplotlib, Seaborn
📁 Estrutura
├── OpenFinance_SLA_Compliance_Audit_Giovanna_do_Vale.ipynb   # notebook completo da análise
├── /images                                   # prints dos gráficos principais
└── README.md
👤 Autora

Giovanna do Vale Santos Analista de Dados | Analytics | BI | Data Quality & Governance LinkedIn · GitHub
