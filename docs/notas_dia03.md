# Notas Dia 03 — Olist Analytics

## O que aprendi

- `.set_index("coluna")` define uma coluna como índice das linhas — ela sai
  das colunas normais e passa a ser o rótulo de cada linha
- `.reset_index()` volta o índice para números — com `drop=False` (padrão)
  o índice vira coluna normal, com `drop=True` ele some
- `.reset_index(drop=...)` só importa quando o índice tem conteúdo real —
  após `.set_index()` ou `groupby()`
- `.shift(n)` desloca os valores de uma coluna n posições — útil pra
  comparar cada linha com a anterior
- Ao combinar condições com `&`, cada condição precisa estar entre parênteses
  — sem isso o Python tenta aplicar `&` antes do `==` e gera TypeError
- `.loc[]` filtra por rótulo ou condição booleana
- `.iloc[]` filtra por posição numérica — funciona como fatiar uma lista
- `.isna().sum()` retorna a contagem de nulos por coluna
- `.isna().mean() * 100` retorna o percentual de nulos por coluna
- Nulos com significado real não devem ser preenchidos com valores fictícios
  — distorce análises futuras

## O que foi feito no projeto

- Completado Data Manipulation with Pandas caps 3 e 4 (indexação, fatiamento,
  visualizações, leitura e gravação de CSVs)
- Pandas Puzzles 21-25 (seção medium — combinação de métodos)
- Filtros com `.loc` no DataFrame mergeado: pedidos entregues por estado,
  combinação de condições com `&`
- Exploração com `.iloc`: primeiras 5 linhas, linhas 10 a 20, célula por posição
- Análise de missing data: contagem absoluta e percentual de nulos por coluna
- Decisão de manter nulos nas colunas de data como NaT — pedidos cancelados
  ou em andamento têm nulo com significado real

## Observações sobre os dados

- `order_approved_at`: 15 nulos — pedidos cancelados antes da aprovação
- `order_delivered_carrier_date`: 1194 nulos — pedidos não enviados
- `order_delivered_customer_date`: 2454 nulos — pedidos não entregues
- Os nulos são concentrados nas colunas de entrega, o que faz sentido dado
  que ~3% dos pedidos não foram entregues (cancelados, em andamento)

## Próximos passos

- Calcular taxa de atraso por estado (atrasos / total de pedidos por estado)
- Visualizações dos principais insights
- Análise de categorias de produtos
- Kaggle Pandas lições 1-2 (ficou pendente)
