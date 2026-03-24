# SQL Cheatsheet — Olist Analytics

Referência dos comandos SQL usados no projeto. Atualizado conforme novas técnicas são aplicadas.

---

## SELECT

```sql
SELECT coluna1, coluna2
FROM tabela;
```

Seleciona colunas específicas de uma tabela.

```sql
SELECT *
FROM tabela;
```

Seleciona todas as colunas.

---

## WHERE

```sql
SELECT *
FROM orders
WHERE order_status = 'delivered';
```

Filtra linhas com base em uma condição.

---

## GROUP BY

```sql
SELECT customer_state, COUNT(*) AS total_pedidos
FROM customers
GROUP BY customer_state;
```

Agrupa linhas por uma coluna e permite aplicar funções de agregação.

---

## Funções de agregação

| Função | O que faz |
|--------|-----------|
| `COUNT(*)` | Conta todas as linhas |
| `COUNT(coluna)` | Conta linhas onde a coluna não é NULL |
| `SUM(coluna)` | Soma os valores |
| `AVG(coluna)` | Média dos valores |
| `MIN(coluna)` | Valor mínimo |
| `MAX(coluna)` | Valor máximo |

---

## ORDER BY

```sql
SELECT customer_state, COUNT(*) AS total_pedidos
FROM customers
GROUP BY customer_state
ORDER BY total_pedidos DESC;
```

Ordena o resultado. `DESC` = maior pro menor, `ASC` = menor pro maior (padrão).

---

## LIMIT

```sql
SELECT product_id, COUNT(*) AS quantidade_vendida
FROM order_items
GROUP BY product_id
ORDER BY quantidade_vendida DESC
LIMIT 10;
```

Restringe o número de linhas retornadas.

---

## Ordem de execução SQL

```
FROM → WHERE → GROUP BY → HAVING → SELECT → ORDER BY → LIMIT
```

A ordem que você *escreve* é diferente da ordem que o banco *executa*.

---

## ROUND

```sql
SELECT customer_state, ROUND(AVG(price), 2) AS ticket_medio
FROM order_items
JOIN orders USING (order_id)
JOIN customers USING (customer_id)
GROUP BY customer_state;
```

Arredonda valores decimais. Útil em médias e proporções.

---

*Próximo: JOINs, subqueries, CTEs*
