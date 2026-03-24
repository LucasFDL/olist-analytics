# Olist Analytics

Análise exploratória do dataset de e-commerce brasileiro da Olist,
cobrindo comportamento de pedidos, performance de entrega e padrões regionais.

## Objetivo

Identificar insights sobre volume de pedidos, ticket médio, eficiência
de entrega e atrasos nos estados brasileiros.

## Análises realizadas

### EDA — Pandas
- Volume de pedidos por estado
- Ticket médio por estado e por categoria de produto
- Pedidos por mês
- Média de itens por pedido
- Proporção do frete por estado
- Taxa de entrega no prazo
- Taxa de atraso por estado (percentual)
- Multi-join com 5 tabelas: orders, order_items, customers, products, sellers

### SQL — DuckDB
- Volume de pedidos por estado
- Distribuição de pedidos por status
- Ticket médio por estado
- Top 10 produtos mais vendidos
- Top 10 sellers por itens vendidos

## Estrutura do projeto
```
olist-analytics/
├── data/
│   ├── raw/          # CSVs originais do Kaggle
│   └── processed/    # Datasets limpos e unidos
├── docs/             # Notas de estudo e referências
├── notebooks/        # Jupyter notebooks (EDA, análises)
└── README.md
```

## Stack

- Python 3.11
- Pandas, NumPy
- Matplotlib, Seaborn
- DuckDB
- Jupyter Notebook

## Status

🟡 Em andamento — EDA e análises SQL concluídos. Próxima etapa: visualizações e análises avançadas.
