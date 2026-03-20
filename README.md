# Olist Analytics

Análise exploratória do dataset de e-commerce brasileiro da Olist,
cobrindo comportamento de pedidos, performance de entrega e padrões regionais.

## Objetivo

Identificar insights sobre volume de pedidos, ticket médio, eficiência
de entrega e atrasos nos estados brasileiros.

## Análises realizadas

- Volume de pedidos por estado
- Ticket médio por estado e por categoria de produto
- Pedidos por mês
- Média de itens por pedido
- Proporção do frete por estado
- Taxa de entrega no prazo
- Taxa de atraso por estado (percentual)
- Multi-join com 5 tabelas: orders, order_items, customers, products, sellers

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
- Jupyter Notebook

## Status

🟡 Em andamento — EDA completo. Visualizações e SQL na próxima etapa.
```

---
```
