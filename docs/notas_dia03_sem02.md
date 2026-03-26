# Notas Dia 03 Semana 02 — Olist Analytics

## O que aprendi

- Subquery no WHERE com valor único: filtra com base num valor calculado
- Subquery no WHERE com lista: usa IN/NOT IN quando a subquery retorna várias linhas
- Subquery no FROM: cria tabela temporária — precisa de alias obrigatório
- Subquery no SELECT: executa uma vez por linha — usar com cuidado em datasets grandes
- Subquery correlacionada: a query interna referencia a query externa — custosa
- CTE é preferido no mercado quando a subquery no FROM fica complexa — vem mais pra frente
- Modelagem de dados é 100% teoria pra analista júnior — o banco já vem modelado
- PK identifica cada linha de forma única, FK aponta pra PK de outra tabela
- Relacionamentos: 1:1, 1:N (mais comum), N:N (precisa de tabela intermediária)
- No Olist, order_items é a tabela intermediária do N:N entre orders e products
- Normalização existe pra eliminar redundância — por isso o Olist exige JOINs pra tudo

## O que foi feito no projeto

- 2 análises novas com joins complexos no notebook 02_sql_olist.ipynb:
  - Receita por estado — cliente vs seller (4 tabelas)
  - Ticket médio por categoria e estado — top 10 por categoria (5 tabelas + subquery + window function)
- Markdowns e observações adicionados nas duas análises

## O que foi feito nos exercícios

- 12 exercícios HackerRank SQL concluídos (básico + basic join)
- Primeiro contato com window functions (ROW_NUMBER) em contexto prático
- 5 exercícios LeetCode SQL concluídos

## Observações sobre os dados

- SP comprando de SP domina em receita com R$3,6M — quase o triplo do segundo lugar
- agro_industry_and_commerce tem os tickets mais altos — AL lidera com R$1.476
