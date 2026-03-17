# Notas Dia 01 — Olist Analytics

## O que aprendi

- Uso do `pathlib.Path` para construir caminhos de forma segura e independente de OS
- Diferença entre `head()`, `info()` e `describe()` e quando cada um é útil na EDA
- `info()` precisa de `print()` no Jupyter para renderizar corretamente
- `describe()` só exibe colunas numéricas por padrão — colunas string aparecem apenas se o DataFrame for todo texto
- Cada célula do Jupyter deve ter um propósito único — separar comandos melhora a leitura
- Aliases padrão do ecossistema: `pd`, `np`, `plt`, `sns`

---

## Observações sobre os dados

### orders (99.441 linhas | 8 colunas)
- Tabela central do dataset — todo pedido passa por aqui antes de se conectar com itens, clientes e pagamentos
- Todos os timestamps estão como `str`, não `datetime` — precisarão de conversão antes de qualquer análise temporal
- `order_approved_at`: 160 nulos — pedidos não aprovados
- `order_delivered_carrier_date`: 1.783 nulos — pedidos não enviados
- `order_delivered_customer_date`: 2.965 nulos — pedidos não entregues
- Os nulos são esperados para pedidos cancelados ou em andamento
- Com 5 colunas de timestamp será possível calcular tempo de aprovação, tempo de entrega e atraso em relação ao prazo estimado

### order_items (112.650 linhas | 7 colunas)
- 112.650 linhas vs 99.441 pedidos — a diferença indica pedidos com múltiplos itens
- `order_item_id` indica a posição do item dentro do pedido (1 = primeiro item)
- Nenhum valor nulo em nenhuma coluna
- `price` e `freight_value` já estão como `float64` — prontos para análise
- `shipping_limit_date` está como `str` — precisará de conversão
- Mediana de preço R$74,99 vs média R$120,65 — distribuição assimétrica, provável cauda de itens caros
- `order_item_id` máximo = 21 — existem pedidos com muitos itens, mas são exceção (75% dos pedidos têm apenas 1 item)
- `freight_value` mínimo = 0 — frete grátis existe no dataset

### customers (99.441 linhas | 5 colunas)
- Mesmo número de linhas que `orders` — 1 registro por pedido, não por cliente real
- `customer_id` é a chave de ligação com `orders` — é gerado por pedido
- `customer_unique_id` identifica o cliente real — um mesmo cliente pode ter vários `customer_id`s
- Sem nulos em nenhuma coluna
- `customer_zip_code_prefix` está como `int64` — é um identificador, não um valor numérico com significado estatístico
- Predominância de SP nas primeiras linhas — esperado pelo tamanho e densidade do estado

---

## Dúvidas

- Como converter múltiplas colunas de timestamp de uma vez de forma eficiente?
- Qual a melhor forma de investigar a distribuição assimétrica de preços (outliers)?
- O `customer_unique_id` pode ser usado para identificar clientes recorrentes?
