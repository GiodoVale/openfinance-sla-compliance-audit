# Análise de Conformidade Regulatória — APIs Open Finance

Auditoria de dados aplicada a métricas de performance de instituições financeiras (IFs) no ecossistema Open Finance, com foco em conformidade de SLA e identificação de padrões de risco.

> **Nota sobre os dados:** este projeto usa um **dataset sintético**, gerado para reproduzir de forma independente a metodologia de um case técnico de estudo sobre Open Finance. Nenhum dado real, confidencial ou de terceiros foi utilizado.

---

## 🎯 Objetivo

Auditar a conformidade de instituições financeiras participantes do Open Finance em relação a dois indicadores regulatórios:

- **Pareamento Diário** — % de chamadas de API processadas com sucesso
- **Desempenho (P95)** — tempo de resposta em que 95% das chamadas foram mais rápidas, comparado ao SLA definido por API

## 🔎 Principais Insights

**1. Risco Agudo (IF 1) — comprovado por outliers catastróficos**
Instituição geralmente estável (pareamento acima de 97% na maior parte dos dias), mas com dias isolados de P95 acima de **14.000ms** (SLA: 1.300–1.500ms) e quedas de pareamento a menos de **10%**, indicando fragilidade de infraestrutura em momentos de pico.

**2. Risco Crônico (IF 2) — falha estrutural, não pontual**
A API `Fixed Incomes` da IF 2 ficou em desconformidade de SLA por **24 dos 30 dias analisados** — um padrão persistente, não um evento isolado.

**3. A média do sistema mascara o risco real**
A performance da IF 1 eleva a média consolidada do ecossistema. Isoladamente, o pareamento médio da IF 2 na API `Fixed Incomes` (**≈77,8%**) fica bem abaixo da meta de 95%, revelando o "elo fraco" que compromete a confiança de todo o sistema.

**Conclusão:** os dois perfis de risco exigem respostas diferentes — um Plano de Mitigação focado em resiliência de infraestrutura para a IF 1, e um Plano de Ação Corretiva mais rigoroso e supervisionado para a IF 2.

## 📊 Visualizações

**Evolução do pareamento diário — IF 1 vs IF 2, com meta de 95%**
![Pareamento diário](images/01_pareamento_diario.png)

**Distribuição do desempenho (P95) por API — IF 1, com faixas de SLA**
![Boxplot desempenho IF1](images/02_boxplot_desempenho_if1.png)

**Heatmap de conformidade diária por instituição**
![Heatmap IF1](images/03_heatmap_if1.png)
![Heatmap IF2](images/03_heatmap_if2.png)

**Quadrante: Pareamento (%) vs. Desempenho (P95)**
![Quadrante de performance](images/04_quadrante_performance.png)

## 🛠️ Metodologia

1. Geração de dataset sintético simulando 30 dias de chamadas de API para 2 instituições e 2 APIs
2. Cálculo de métricas diárias agrupadas por data, instituição e API
3. Definição de regras de conformidade (SLA por API, limite de dias em desconformidade)
4. Visualização exploratória e classificação por quadrante de risco
5. Síntese de insights e recomendações

## 💻 Tecnologias

- Python (Pandas, NumPy)
- Visualização: Matplotlib, Seaborn

## 📁 Estrutura

```
├── OpenFinance_SLA_Compliance_Audit.ipynb   # notebook completo da análise
├── dados_financeiros_abertos_sinteticos.csv  # dataset sintético gerado
├── images/                                    # gráficos exportados
└── README.md
```

## 👤 Autora

**Giovanna do Vale Santos**
Analista de Dados | Analytics | BI | Data Quality & Governance
[LinkedIn](https://www.linkedin.com/in/giovanna-do-vale-santos/) · [GitHub](https://github.com/GiodoVale)
