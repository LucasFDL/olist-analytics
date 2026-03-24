# Notas Dia 01 Semana 02 — Olist Analytics

## O que aprendi

- DuckDB cria um banco em memória a partir de CSVs com `read_csv_auto` — sem precisar definir schema na mão
- `COUNT(*)` é o padrão pra contar linhas; `COUNT(coluna)` usa quando quer ignorar NULLs explicitamente
- `../` sobe um nível no path — a partir de `notebooks/`, `../data/raw` resolve pra raiz do projeto
- Setup de conexão não precisa ser decorado — o que importa é entender o que cada parte faz

## O que foi feito no projeto

- Instalação e configuração do DuckDB no ambiente `.venv`
- Criação do notebook `02_sql_olist.ipynb`
- Carregamento das 5 tabelas Olist no DuckDB via `read_csv_auto`
- 5 queries SQL aplicadas ao dataset:
  - Volume de pedidos por estado (JOIN orders + customers)
  - Distribuição de pedidos por status
  - Ticket médio por estado
  - Top 10 produtos mais vendidos
  - Top 10 sellers por itens vendidos
- Atualização do `README.md` com seção SQL e DuckDB na stack

## Observações sobre os dados

- SP lidera em volume absoluto de pedidos com folga
- O seller mais ativo tem mais de 2000 itens vendidos — concentração relevante no topo
- O produto mais vendido tem 527 unidades — dataset tem produtos de nicho com volumes bem menores

## Próximos passos

- Criar `docs/sql_cheatsheet.md` com referência dos comandos usados
- HackerRank — 10 exercícios básicos de SQL
- Joins no SQL (próxima sessão)
