# Notas Dia 02 Semana 02 — Olist Analytics

## O que aprendi

- Intermediate SQL completo: COUNT/LIMIT, WHERE/BETWEEN/AND/OR/LIKE/IS NULL, ROUND e funções de agregação, ORDER BY/GROUP BY/HAVING
- HAVING filtra depois do GROUP BY — WHERE filtra antes da agregação
- ROUND arredonda valores numéricos: ROUND(valor, casas_decimais)
- Subquery cria uma tabela temporária em memória — útil quando precisa referenciar um valor calculado na mesma query
- CASE funciona como if/else: define condições e retorna um valor para cada uma
- date_diff('day', data_inicio, data_fim) calcula diferença em dias entre duas datas
- Subquery desnecessária tem custo — usar só quando o resultado intermediário não dá pra obter direto
- Decompor o problema em partes menores antes de escrever a query facilita muito

## O que foi feito no projeto

- 5 análises novas no notebook 02_sql_olist.ipynb:
  - Top 10 categorias por receita (JOIN triplo + subquery)
  - Classificação de pedidos por atraso: No Prazo / Atraso Leve / Atraso Crítico (CASE + date_diff)
  - Meios de pagamento — volume e receita total
  - Detalhamento por tipo de pagamento: AOV, média e mediana de parcelas
  - Distribuição por número de parcelas (filtrado por credit_card)
- Visualização: gráfico de barras com distribuição de status de entrega
- Markdowns e observações adicionados em cada análise
- Células DESCRIBE agrupadas em seção Schema das Tabelas

## Observações sobre os dados

- Cartão de crédito domina: 76k transações e R$12,5M em receita
- Compras em 10x têm AOV de R$415 — quase 4x maior que compras à vista (R$95)
- health_beauty lidera em receita total entre as categorias
- A maioria dos pedidos foi entregue no prazo — atraso crítico é minoria

## Pendências para amanhã

- Cruzar top produtos com categoria (análise 4 ainda mostra só hash)
- Consolidar análises 8 e 9 numa query só
- Adicionar volume de pedidos por mês
- Criar docs/sql_cheatsheet.md
