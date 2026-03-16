# Notas Dia 02 — Olist Analytics

## O que aprendi

- `np.logical_and()`, `np.logical_or()` são equivalentes a `&` e `|` em
  Series do Pandas — na prática usa-se `&` e `|` com parênteses obrigatórios
- `and` e `or` do Python não funcionam com arrays/Series — geram ValueError
- `.loc[]` acessa por label/índice, `.iloc[]` acessa por posição numérica
- `.map()` substitui todos os valores via dicionário — valores ausentes no
  dict viram NaN
- `.replace()` substitui valores específicos sem afetar o restante
- `groupby` + agregação (`mean`, `sum`, `count`) é o padrão pra análises
  por categoria
- `.sort_values(by=[...], ascending=[...])` aceita listas para ordenação
  múltipla com direções diferentes
- `.between()` é mais legível que dois filtros separados para faixas de valor
- `.value_counts(normalize=True) * 100` retorna percentual direto

## O que foi feito no projeto

- Merge de `orders` + `order_items` + `customers` em DataFrame unificado
- Merge de `orders` + `customers` para análise de entrega
- Volume de pedidos por estado
- Ticket médio por estado (groupby duplo: soma por pedido, média por estado)
- Pedidos por mês com conversão de timestamp para período
- Média de itens por pedido
- Freight ratio (frete / preço) como nova coluna
- Taxa de entrega no prazo com coluna booleana `is_on_time`
- Resumo de atrasos por estado com contagem e percentual

## Observações sobre os dados

- SP lidera em volume de pedidos e também em atraso absoluto — esperado
  pelo tamanho do estado
- RJ em segundo lugar em atrasos com 20,31% do total
- A análise de atraso por estado em valores absolutos é enviesada pelo
  volume — próximo passo é calcular taxa de atraso por estado

## Próximos passos

- Calcular taxa de atraso por estado (atrasos / total de pedidos por estado)
- Visualizações dos principais insights
- Análise de categorias de produtos