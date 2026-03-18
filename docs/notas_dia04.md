# Notas Dia 04 — Olist Analytics

## O que aprendi

- Inner Join retorna só o que casa nos dois lados — linhas sem correspondência
  somem das duas tabelas
- Left Join mantém tudo da tabela da esquerda, preenchendo com NaN onde não
  tem correspondência na direita — o mais usado no dia a dia
- Right Join é o inverso do Left — na prática pouco usado, dá pra substituir
  trocando a ordem das tabelas e usando Left
- Full/Outer Join mantém tudo dos dois lados, preenchendo com NaN onde não
  casa — útil pra encontrar registros que existem em uma tabela mas faltam
  na outra
- Cross Join combina cada linha de A com cada linha de B — produto cartesiano,
  cuidado com tabelas grandes
- `.merge()` no Pandas faz Inner Join por padrão
- `.head(n).T` transpõe o DataFrame — vira linhas em colunas e colunas em
  linhas — quando o DataFrame tem muitas colunas o Pandas resume e corta a
  visualização, ao transpor as colunas viram linhas e dá pra ver todas sem
  corte
- `.dtypes` mostra o tipo de cada coluna — útil pra confirmar como as colunas
  vieram após um merge
- `.shape` retorna (linhas, colunas) — segundo valor é a quantidade de colunas

## O que foi feito no projeto

- Joining Data with Pandas caps 1-2 (inner, left, right, outer, cross join
  e agregação)
- Merge de `order_completed` com `olist_products_dataset.csv` usando
  `product_id` como chave — DataFrame ficou com 27 colunas
- Identificação das 8 novas colunas vindas de products usando `.dtypes` e
  `.head().T`
- Análise de volume de pedidos por categoria de produto
- Kaggle Pandas lições 1-4

## Observações sobre os dados

- As categorias com maior volume dominam de forma clara — marketplace
  generalista com algumas categorias muito mais populares que outras
- Categorias de nicho têm volume baixo mas podem compensar com ticket médio
  mais alto — próximo passo é cruzar categoria com preço

## Próximos passos

- Calcular taxa de atraso por estado (atrasos / total de pedidos por estado)
- Cruzar categoria com ticket médio
- Visualizações dos principais insights
- Kaggle Pandas lições 1-4 ✅
- Pandas Puzzles 31-40 (ficou pendente)
